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
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="25e28-104">Implementazione di connessioni di Entity Framework Core SQL resilienti</span><span class="sxs-lookup"><span data-stu-id="25e28-104">Implementing resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="25e28-105">Per il database di SQL Azure, Entity Framework Core fornisce già logica resilienza e tentativi di connessione database interno.</span><span class="sxs-lookup"><span data-stu-id="25e28-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="25e28-106">Ma è necessario abilitare la strategia di esecuzione di Entity Framework per ogni connessione DbContext se si desidera disporre [resilienti connessioni Core EF](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="25e28-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="25e28-107">Ad esempio, il codice seguente a livello di connessione Entity Framework Core consente connessioni SQL resilienti che vengono ripetute nel caso di connessione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="25e28-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="25e28-108">Strategie di esecuzione e le transazioni esplicite utilizzando BeginTransaction e più DbContexts</span><span class="sxs-lookup"><span data-stu-id="25e28-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="25e28-109">Quando i tentativi sono abilitati nelle connessioni di Entity Framework Core, ogni operazione effettuata usando EF Core diventa il proprio possibilità di ritentare.</span><span class="sxs-lookup"><span data-stu-id="25e28-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="25e28-110">Ogni query e ogni chiamata al metodo SaveChanges verrà ritentate come unità se si verifica un errore temporaneo.</span><span class="sxs-lookup"><span data-stu-id="25e28-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="25e28-111">Tuttavia, se il codice avvia una transazione utilizzando BeginTransaction, si definisce un proprio gruppo di operazioni che devono essere trattati come un'unità, ovvero tutti gli elementi all'interno della transazione è essere sottoposta a rollback se si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="25e28-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="25e28-112">Si verifica un'eccezione simile al seguente se si tenta di eseguire tale transazione quando si utilizza una strategia di esecuzione EF (criteri di ripetizione) e si includono più chiamate SaveChanges da più DbContexts nella transazione.</span><span class="sxs-lookup"><span data-stu-id="25e28-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="25e28-113">System. InvalidOperationException: La strategia di esecuzione configurata 'SqlServerRetryingExecutionStrategy' non supporta le transazioni avviate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="25e28-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="25e28-114">Utilizzare la strategia di esecuzione restituita da 'DbContext.Database.CreateExecutionStrategy()' per eseguire tutte le operazioni nella transazione come unità possibilità di ritentare.</span><span class="sxs-lookup"><span data-stu-id="25e28-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="25e28-115">La soluzione consiste nel richiamare manualmente la strategia di esecuzione EF con un delegato che rappresenta gli elementi che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="25e28-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="25e28-116">Se si verifica un errore temporaneo, la strategia di esecuzione verrà nuovamente richiamare il delegato.</span><span class="sxs-lookup"><span data-stu-id="25e28-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="25e28-117">Ad esempio, il codice seguente mostra come viene implementato in eShopOnContainers con due più DbContexts (\_catalogContext e il IntegrationEventLogContext) durante l'aggiornamento di un prodotto e quindi salvare il Oggetto ProductPriceChangedIntegrationEvent, che richiede l'utilizzo di un elemento DbContext diversi.</span><span class="sxs-lookup"><span data-stu-id="25e28-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

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

<span data-ttu-id="25e28-118">Il primo elemento DbContext è \_catalogContext e il secondo elemento DbContext è all'interno di \_integrationEventLogService oggetto.</span><span class="sxs-lookup"><span data-stu-id="25e28-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="25e28-119">L'operazione di Commit viene eseguita in più DbContexts utilizzando una strategia di esecuzione di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="25e28-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25e28-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="25e28-120">Additional resources</span></span>

-   <span data-ttu-id="25e28-121">**Resilienza di connessione e comando di intercettazione con Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="25e28-121">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="25e28-122">**Cesar de la Torre. Utilizzo di connessioni a Sql resilienti Entity Framework Core e transazioni**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="25e28-122">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="25e28-123">[Precedente] (implementa-tentativi-esponenziale-backoff.md) [Avanti] (implement-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="25e28-123">[Previous] (implement-retries-exponential-backoff.md) [Next] (implement-custom-http-call-retries-exponential-backoff.md)</span></span>
