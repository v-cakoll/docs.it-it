---
title: Implementazione di connessioni SQL resilienti di Entity Framework Core
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione di connessioni SQL resilienti di Entity Framework Core. Questa tecnica è particolarmente importante quando si usa il database SQL di Azure nel cloud.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: 0df375737c0e079baba426f3c97b95edcb9aca75
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127186"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="a9a8b-104">Implementazione di connessioni SQL resilienti di Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="a9a8b-104">Implement resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="a9a8b-105">Per il database SQL di Azure, Entity Framework Core fornisce già la logica per i tentativi e la resilienza della connessione di database interna.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="a9a8b-106">Tuttavia, è necessario abilitare la strategia di esecuzione di Entity Framework per ogni connessione DbContext per ottenere [connessioni di EF Core resilienti](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="a9a8b-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="a9a8b-107">Ad esempio, il codice seguente a livello della connessione di EF Core consente connessioni SQL resilienti per le quali vengono effettuati ulteriori tentativi in caso di mancata connessione.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="a9a8b-108">Strategie di esecuzione e transazioni esplicite usando BeginTransaction e più oggetti DbContext</span><span class="sxs-lookup"><span data-stu-id="a9a8b-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="a9a8b-109">Quando nelle connessioni di EF Core sono abilitati i tentativi, ogni operazione che viene eseguita con EF Core diventa un'unica operazione con possibilità di ritentare.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retryable operation.</span></span> <span data-ttu-id="a9a8b-110">Per ogni query e per ogni chiamata a SaveChanges verranno eseguiti altri tentativi come una sola unità nel caso in cui si verifichi un errore temporaneo.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="a9a8b-111">Tuttavia, se il codice avvia una transazione tramite BeginTransaction, viene definito un gruppo personalizzato di operazioni che deve essere considerato come un'unità. Se si verifica un errore, verrà eseguito il rollback di tutto ciò che si trova all'interno della transazione.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="a9a8b-112">Se si tenta di eseguire la transazione quando si usa una strategia di esecuzione (criteri di ripetizione) di EF e si includono numerose chiamate a SaveChanges da più oggetti DbContext nella transazione, verrà restituita un'eccezione simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="a9a8b-113">System.InvalidOperationException: La strategia di esecuzione configurata 'SqlServerRetryingExecutionStrategy' non supporta le transazioni avviate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="a9a8b-114">Usare la strategia di esecuzione restituita da 'DbContext.Database.CreateExecutionStrategy()' per eseguire tutte le operazioni nella transazione come un'unità con possibilità di ritentare.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="a9a8b-115">La soluzione prevede di richiamare manualmente la strategia di esecuzione di EF con un delegato che rappresenta tutte le operazioni che devono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="a9a8b-116">Se si verifica un errore temporaneo, la strategia di esecuzione richiamerà nuovamente il delegato.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="a9a8b-117">Ad esempio, il codice seguente mostra l'implementazione in eShopOnContainers con due oggetti DbContext (\_catalogContext e IntegrationEventLogContext), durante l'aggiornamento di un prodotto e il successivo salvataggio dell'oggetto ProductPriceChangedIntegrationEvent, che deve usare un oggetto DbContext diverso.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

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

<span data-ttu-id="a9a8b-118">Il primo oggetto DbContext è \_catalogContext e il secondo oggetto DbContext si trova all'interno dell'oggetto \_integrationEventLogService.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="a9a8b-119">L'azione Commit viene eseguita su più oggetti DbContext tramite una strategia di esecuzione di EF.</span><span class="sxs-lookup"><span data-stu-id="a9a8b-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9a8b-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a9a8b-120">Additional resources</span></span>

-   <span data-ttu-id="a9a8b-121">**EF Connection Resiliency** (Resilienza della connessione EF) (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="a9a8b-121">**EF Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="a9a8b-122">**Connection Resiliency and Command Interception with the Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency) (Resilienza della connessione e intercettazione dei comandi con Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="a9a8b-122">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="a9a8b-123">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/> (Utilizzo di connessioni e transazioni SQL resilienti di Entity Framework Core)</span><span class="sxs-lookup"><span data-stu-id="a9a8b-123">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a9a8b-124">[Precedente](implement-retries-exponential-backoff.md)
>[Successivo](explore-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="a9a8b-124">[Previous](implement-retries-exponential-backoff.md)
[Next](explore-custom-http-call-retries-exponential-backoff.md)</span></span>