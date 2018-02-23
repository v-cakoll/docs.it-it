---
title: Implementazione di connessioni SQL resilienti di Entity Framework Core
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione di connessioni SQL resilienti di Entity Framework Core
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b37d2c5683aff44165d0330c8d42fc881effbb76
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>Implementazione di connessioni SQL resilienti di Entity Framework Core

Per il database SQL di Azure, Entity Framework Core fornisce già la logica per i tentativi e la resilienza della connessione di database interna. Tuttavia, è necessario abilitare la strategia di esecuzione di Entity Framework per ogni connessione DbContext per ottenere [connessioni di EF Core resilienti](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).

Ad esempio, il codice seguente a livello della connessione di EF Core consente connessioni SQL resilienti per le quali vengono effettuati ulteriori tentativi in caso di mancata connessione.

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Strategie di esecuzione e transazioni esplicite usando BeginTransaction e più oggetti DbContext

Quando nelle connessioni di EF Core sono abilitati i tentativi, ogni operazione che viene eseguita con EF Core diventa un'unica operazione con possibilità di ritentare. Per ogni query e per ogni chiamata a SaveChanges verranno eseguiti altri tentativi come una sola unità nel caso in cui si verifichi un errore temporaneo.

Tuttavia, se il codice avvia una transazione tramite BeginTransaction, viene definito un gruppo personalizzato di operazioni che deve essere considerato come un'unità. Se si verifica un errore, verrà eseguito il rollback di tutto ciò che si trova all'interno della transazione. Se si tenta di eseguire la transazione quando si usa una strategia di esecuzione (criteri di ripetizione) di EF e si includono numerose chiamate a SaveChanges da più oggetti DbContext nella transazione, verrà restituita un'eccezione simile alla seguente.

> System.InvalidOperationException: La strategia di esecuzione configurata 'SqlServerRetryingExecutionStrategy' non supporta le transazioni avviate dall'utente. Usare la strategia di esecuzione restituita da 'DbContext.Database.CreateExecutionStrategy()' per eseguire tutte le operazioni nella transazione come un'unità con possibilità di ritentare.

La soluzione prevede di richiamare manualmente la strategia di esecuzione di EF con un delegato che rappresenta tutte le operazioni che devono essere eseguite. Se si verifica un errore temporaneo, la strategia di esecuzione richiamerà nuovamente il delegato. Ad esempio, il codice seguente mostra l'implementazione in eShopOnContainers con due oggetti DbContext (\_catalogContext e IntegrationEventLogContext), durante l'aggiornamento di un prodotto e il successivo salvataggio dell'oggetto ProductPriceChangedIntegrationEvent, che deve usare un oggetto DbContext diverso.

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

Il primo oggetto DbContext è \_catalogContext e il secondo oggetto DbContext si trova all'interno dell'oggetto \_integrationEventLogService. L'azione Commit viene eseguita su più oggetti DbContext tramite una strategia di esecuzione di EF.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Resilienza della connessione e intercettazione dei comandi con Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions (Utilizzo di connessioni SQL resilienti di Entity Framework Core e transazioni) **
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[Indietro] (implement-retries-exponential-backoff.md) [Avanti] (implement-custom-http-call-retries-exponential-backoff.md)
