---
title: Implementazione di connessioni SQL resilienti di Entity Framework Core
description: Informazioni su come implementare connessioni SQL resilienti di Entity Framework Core. Questa tecnica è particolarmente importante quando si usa il database SQL di Azure nel cloud.
ms.date: 10/16/2018
ms.openlocfilehash: 7a047edca21d63a451e90f407b23f3358d461330
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78241065"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a>Implementazione di connessioni SQL resilienti di Entity Framework Core

Per il database SQL di Azure, Entity Framework (EF) Core fornisce già la logica per i tentativi e la resilienza della connessione di database interna. È tuttavia necessario abilitare la strategia di esecuzione di Entity Framework per ogni connessione <xref:Microsoft.EntityFrameworkCore.DbContext> al fine di ottenere [connessioni di EF Core resilienti](/ef/core/miscellaneous/connection-resiliency).

Ad esempio, il codice seguente a livello della connessione di EF Core consente connessioni SQL resilienti per le quali vengono effettuati ulteriori tentativi in caso di mancata connessione.

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<CatalogContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 10,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Strategie di esecuzione e transazioni esplicite usando BeginTransaction e più oggetti DbContext

Quando nelle connessioni di EF Core sono abilitati i tentativi, ogni operazione che viene eseguita con EF Core diventa un'unica operazione con possibilità di ritentare. Per ogni query e per ogni chiamata a `SaveChanges` verranno eseguiti altri tentativi come una sola unità nel caso in cui si verifichi un errore temporaneo.

Se tuttavia nel codice una transazione inizia con `BeginTransaction`, si definisce un gruppo di operazioni personalizzato che va considerato come un'unità. In caso di errore, tutti gli elementi inclusi nella transazione dovranno essere sottoposti a rollback.

Se si prova a eseguire la transazione quando si usa una strategia di esecuzione EF (criteri di ripetizione) e si chiama `SaveChanges` da più oggetti DbContext, viene restituita un'eccezione simile alla seguente:

> System.InvalidOperationException: La strategia di esecuzione configurata 'SqlServerRetryingExecutionStrategy' non supporta le transazioni avviate dall'utente. Usare la strategia di esecuzione restituita da 'DbContext.Database.CreateExecutionStrategy()' per eseguire tutte le operazioni nella transazione come un'unità con possibilità di ritentare.

La soluzione prevede di richiamare manualmente la strategia di esecuzione di EF con un delegato che rappresenta tutte le operazioni che devono essere eseguite. Se si verifica un errore temporaneo, la strategia di esecuzione chiamerà nuovamente il delegato. Ad esempio il codice seguente visualizza l'implementazione in eShopOnContainers con due DbContext multipli (\_catalogContext e IntegrationEventLogContext) durante l'aggiornamento di un prodotto e il successivo salvataggio dell'oggetto ProductPriceChangedIntegrationEvent, che deve usare un oggetto DbContext diverso.

```csharp
public async Task<IActionResult> UpdateProduct(
    [FromBody]CatalogItem productToUpdate)
{
    // Other code ...

    var oldPrice = catalogItem.Price;
    var raiseProductPriceChangedEvent = oldPrice != productToUpdate.Price;

    // Update current product
    catalogItem = productToUpdate;

    // Save product's data and publish integration event through the Event Bus
    // if price has changed
    if (raiseProductPriceChangedEvent)
    {
        //Create Integration Event to be published through the Event Bus
        var priceChangedEvent = new ProductPriceChangedIntegrationEvent(
          catalogItem.Id, productToUpdate.Price, oldPrice);

       // Achieving atomicity between original Catalog database operation and the
       // IntegrationEventLog thanks to a local transaction
       await _catalogIntegrationEventService.SaveEventAndCatalogContextChangesAsync(
           priceChangedEvent);

       // Publish through the Event Bus and mark the saved event as published
       await _catalogIntegrationEventService.PublishThroughEventBusAsync(
           priceChangedEvent);
    }
    // Just save the updated product because the Product's Price hasn't changed.
    else
    {
        await _catalogContext.SaveChangesAsync();
    }
}
```

Il primo <xref:Microsoft.EntityFrameworkCore.DbContext> è `_catalogContext` e il secondo `DbContext` è incluso nell'oggetto `_catalogIntegrationEventService`. L'azione Commit viene eseguita su tutti gli oggetti `DbContext` tramite una strategia di esecuzione di EF.

Per ottenere questo commit di più `DbContext`, `SaveEventAndCatalogContextChangesAsync` usa una classe `ResilientTransaction`, come illustrato nel codice seguente:

```csharp
public class CatalogIntegrationEventService : ICatalogIntegrationEventService
{
    //…
    public async Task SaveEventAndCatalogContextChangesAsync(
        IntegrationEvent evt)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        await ResilientTransaction.New(_catalogContext).ExecuteAsync(async () =>
        {
            // Achieving atomicity between original catalog database
            // operation and the IntegrationEventLog thanks to a local transaction
            await _catalogContext.SaveChangesAsync();
            await _eventLogService.SaveEventAsync(evt,
                _catalogContext.Database.CurrentTransaction.GetDbTransaction());
        });
    }
}
```

In pratica il metodo `ResilientTransaction.ExecuteAsync` inizia una transazione dal `DbContext` passato (`_catalogContext`) e quindi fa sì che `EventLogService` usi tale transazione per salvare le modifiche apportate da `IntegrationEventLogContext` e quindi esegua il commit dell'intera transazione.

```csharp
public class ResilientTransaction
{
    private DbContext _context;
    private ResilientTransaction(DbContext context) =>
        _context = context ?? throw new ArgumentNullException(nameof(context));

    public static ResilientTransaction New (DbContext context) =>
        new ResilientTransaction(context);

    public async Task ExecuteAsync(Func<Task> action)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        var strategy = _context.Database.CreateExecutionStrategy();
        await strategy.ExecuteAsync(async () =>
        {
            using (var transaction = _context.Database.BeginTransaction())
            {
                await action();
                transaction.Commit();
            }
        });
    }
}
```

## <a name="additional-resources"></a>Risorse aggiuntive

- **Connection Resiliency and Command Interception with EF in an ASP.NET MVC Application (Resilienza della connessione e intercettazione dei comandi con EF in un'applicazione MVC ASP.NET)** \
  [https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application)

- **Cesar de la Torre. Utilizzo di transazioni e connessioni SQL resilienti Entity Framework Core** \
  <https://devblogs.microsoft.com/cesardelatorre/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>

>[!div class="step-by-step"]
>[Precedente](implement-retries-exponential-backoff.md)
>[Successivo](use-httpclientfactory-to-implement-resilient-http-requests.md)
