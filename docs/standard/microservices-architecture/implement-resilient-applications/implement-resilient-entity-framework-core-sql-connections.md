---
title: Implementazione di connessioni di Entity Framework Core SQL resilienti
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione di connessioni di Entity Framework Core SQL resilienti
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8600625c2022d69ebaa2645c2a8159a848b12ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>Implementazione di connessioni di Entity Framework Core SQL resilienti

Per il database di SQL Azure, Entity Framework Core fornisce già logica resilienza e tentativi di connessione database interno. Ma è necessario abilitare la strategia di esecuzione di Entity Framework per ogni connessione DbContext se si desidera disporre [resilienti connessioni Core EF](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).

Ad esempio, il codice seguente a livello di connessione Entity Framework Core consente connessioni SQL resilienti che vengono ripetute nel caso di connessione ha esito negativo.

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<OrderingContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 5,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Strategie di esecuzione e le transazioni esplicite utilizzando BeginTransaction e più DbContexts

Quando i tentativi sono abilitati nelle connessioni di Entity Framework Core, ogni operazione effettuata usando EF Core diventa il proprio possibilità di ritentare. Ogni query e ogni chiamata al metodo SaveChanges verrà ritentate come unità se si verifica un errore temporaneo.

Tuttavia, se il codice avvia una transazione utilizzando BeginTransaction, si definisce un proprio gruppo di operazioni che devono essere trattati come un'unità, ovvero tutti gli elementi all'interno della transazione è essere sottoposta a rollback se si verifica un errore. Si verifica un'eccezione simile al seguente se si tenta di eseguire tale transazione quando si utilizza una strategia di esecuzione EF (criteri di ripetizione) e si includono più chiamate SaveChanges da più DbContexts nella transazione.

> System. InvalidOperationException: La strategia di esecuzione configurata 'SqlServerRetryingExecutionStrategy' non supporta le transazioni avviate dall'utente. Utilizzare la strategia di esecuzione restituita da 'DbContext.Database.CreateExecutionStrategy()' per eseguire tutte le operazioni nella transazione come unità possibilità di ritentare.

La soluzione consiste nel richiamare manualmente la strategia di esecuzione EF con un delegato che rappresenta gli elementi che deve essere eseguito. Se si verifica un errore temporaneo, la strategia di esecuzione verrà nuovamente richiamare il delegato. Ad esempio, il codice seguente mostra come viene implementato in eShopOnContainers con due più DbContexts (\_catalogContext e il IntegrationEventLogContext) durante l'aggiornamento di un prodotto e quindi salvare il Oggetto ProductPriceChangedIntegrationEvent, che richiede l'utilizzo di un elemento DbContext diversi.

```csharp
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem
    productToUpdate)
{
    // Other code ...
    // Update current product
    catalogItem = productToUpdate;

    // Use of an EF Core resiliency strategy when using multiple DbContexts
    // within an explicit transaction
    // See:
    // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
    var strategy = _catalogContext.Database.CreateExecutionStrategy();
    await strategy.ExecuteAsync(async () =>
    {
        // Achieving atomicity between original Catalog database operation and the
        // IntegrationEventLog thanks to a local transaction
        using (var transaction = _catalogContext.Database.BeginTransaction())
        {
            _catalogContext.CatalogItems.Update(catalogItem);
            await _catalogContext.SaveChangesAsync();
            // Save to EventLog only if product price changed
            if (raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
            transaction.Commit();
        }
    });
}
```

Il primo elemento DbContext è \_catalogContext e il secondo elemento DbContext è all'interno di \_integrationEventLogService oggetto. L'operazione di Commit viene eseguita in più DbContexts utilizzando una strategia di esecuzione di Entity Framework.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Resilienza di connessione e comando di intercettazione con Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Cesar de la Torre. Utilizzo di connessioni a Sql resilienti Entity Framework Core e transazioni**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[Precedente] (implementa-tentativi-esponenziale-backoff.md) [Avanti] (implement-custom-http-call-retries-exponential-backoff.md)
