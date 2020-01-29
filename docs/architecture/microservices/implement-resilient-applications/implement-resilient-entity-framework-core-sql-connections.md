---
title: Implementazione di connessioni SQL resilienti di Entity Framework Core
description: Informazioni su come implementare connessioni SQL resilienti di Entity Framework Core. Questa tecnica è particolarmente importante quando si usa il database SQL di Azure nel cloud.
ms.date: 10/16/2018
ms.openlocfilehash: 7899fc263ab3cde6ac2410ca614a7e5fa285576b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732730"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="0f555-104">Implementazione di connessioni SQL resilienti di Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="0f555-104">Implement resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="0f555-105">Per il database SQL di Azure, Entity Framework (EF) Core fornisce già la logica per i tentativi e la resilienza della connessione di database interna.</span><span class="sxs-lookup"><span data-stu-id="0f555-105">For Azure SQL DB, Entity Framework (EF) Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="0f555-106">È tuttavia necessario abilitare la strategia di esecuzione di Entity Framework per ogni connessione <xref:Microsoft.EntityFrameworkCore.DbContext> al fine di ottenere [connessioni di EF Core resilienti](/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="0f555-106">But you need to enable the Entity Framework execution strategy for each <xref:Microsoft.EntityFrameworkCore.DbContext> connection if you want to have [resilient EF Core connections](/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="0f555-107">Ad esempio, il codice seguente a livello della connessione di EF Core consente connessioni SQL resilienti per le quali vengono effettuati ulteriori tentativi in caso di mancata connessione.</span><span class="sxs-lookup"><span data-stu-id="0f555-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="0f555-108">Strategie di esecuzione e transazioni esplicite usando BeginTransaction e più oggetti DbContext</span><span class="sxs-lookup"><span data-stu-id="0f555-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="0f555-109">Quando nelle connessioni di EF Core sono abilitati i tentativi, ogni operazione che viene eseguita con EF Core diventa un'unica operazione con possibilità di ritentare.</span><span class="sxs-lookup"><span data-stu-id="0f555-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="0f555-110">Per ogni query e per ogni chiamata a `SaveChanges` verranno eseguiti altri tentativi come una sola unità nel caso in cui si verifichi un errore temporaneo.</span><span class="sxs-lookup"><span data-stu-id="0f555-110">Each query and each call to `SaveChanges` will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="0f555-111">Se tuttavia nel codice una transazione inizia con `BeginTransaction`, si definisce un gruppo di operazioni personalizzato che va considerato come un'unità.</span><span class="sxs-lookup"><span data-stu-id="0f555-111">However, if your code initiates a transaction using `BeginTransaction`, you're defining your own group of operations that need to be treated as a unit.</span></span> <span data-ttu-id="0f555-112">In caso di errore, tutti gli elementi inclusi nella transazione dovranno essere sottoposti a rollback.</span><span class="sxs-lookup"><span data-stu-id="0f555-112">Everything inside the transaction has to be rolled back if a failure occurs.</span></span>

<span data-ttu-id="0f555-113">Se si prova a eseguire la transazione quando si usa una strategia di esecuzione EF (criteri di ripetizione) e si chiama `SaveChanges` da più oggetti DbContext, viene restituita un'eccezione simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="0f555-113">If you try to execute that transaction when using an EF execution strategy (retry policy) and you call `SaveChanges` from multiple DbContexts, you'll get an exception like this one:</span></span>

> <span data-ttu-id="0f555-114">System.InvalidOperationException: La strategia di esecuzione configurata 'SqlServerRetryingExecutionStrategy' non supporta le transazioni avviate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0f555-114">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="0f555-115">Usare la strategia di esecuzione restituita da 'DbContext.Database.CreateExecutionStrategy()' per eseguire tutte le operazioni nella transazione come un'unità con possibilità di ritentare.</span><span class="sxs-lookup"><span data-stu-id="0f555-115">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="0f555-116">La soluzione prevede di richiamare manualmente la strategia di esecuzione di EF con un delegato che rappresenta tutte le operazioni che devono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="0f555-116">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="0f555-117">Se si verifica un errore temporaneo, la strategia di esecuzione richiamerà nuovamente il delegato.</span><span class="sxs-lookup"><span data-stu-id="0f555-117">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="0f555-118">Ad esempio il codice seguente visualizza l'implementazione in eShopOnContainers con due DbContext multipli (\_catalogContext e IntegrationEventLogContext) durante l'aggiornamento di un prodotto e il successivo salvataggio dell'oggetto ProductPriceChangedIntegrationEvent, che deve usare un oggetto DbContext diverso.</span><span class="sxs-lookup"><span data-stu-id="0f555-118">For example, the following code show how it's implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

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

<span data-ttu-id="0f555-119">Il primo <xref:Microsoft.EntityFrameworkCore.DbContext> è `_catalogContext` e il secondo `DbContext` è incluso nell'oggetto `_catalogIntegrationEventService`.</span><span class="sxs-lookup"><span data-stu-id="0f555-119">The first <xref:Microsoft.EntityFrameworkCore.DbContext> is `_catalogContext` and the second `DbContext` is within the `_catalogIntegrationEventService` object.</span></span> <span data-ttu-id="0f555-120">L'azione Commit viene eseguita su tutti gli oggetti `DbContext` tramite una strategia di esecuzione di EF.</span><span class="sxs-lookup"><span data-stu-id="0f555-120">The Commit action is performed across all `DbContext` objects using an EF execution strategy.</span></span>

<span data-ttu-id="0f555-121">Per ottenere questo commit di più `DbContext`, `SaveEventAndCatalogContextChangesAsync` usa una classe `ResilientTransaction`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0f555-121">To achieve this multiple `DbContext` commit, the `SaveEventAndCatalogContextChangesAsync` uses a `ResilientTransaction` class, as shown in the following code:</span></span>

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

<span data-ttu-id="0f555-122">In pratica il metodo `ResilientTransaction.ExecuteAsync` inizia una transazione dal `DbContext` passato (`_catalogContext`) e quindi fa sì che `EventLogService` usi tale transazione per salvare le modifiche apportate da `IntegrationEventLogContext` e quindi esegua il commit dell'intera transazione.</span><span class="sxs-lookup"><span data-stu-id="0f555-122">The `ResilientTransaction.ExecuteAsync` method basically begins a transaction from the passed `DbContext` (`_catalogContext`) and then makes the `EventLogService` use that transaction to save changes from the `IntegrationEventLogContext` and then commits the whole transaction.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="0f555-123">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0f555-123">Additional resources</span></span>

- <span data-ttu-id="0f555-124">**Connection Resiliency and Command Interception with EF in an ASP.NET MVC Application (Resilienza della connessione e intercettazione dei comandi con EF in un'applicazione MVC ASP.NET)**  </span><span class="sxs-lookup"><span data-stu-id="0f555-124">**Connection Resiliency and Command Interception with EF in an ASP.NET MVC Application** </span></span>\
  [https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application)

- <span data-ttu-id="0f555-125">**Cesar de la Torre. Utilizzo di transazioni e connessioni SQL resilienti Entity Framework Core** </span><span class="sxs-lookup"><span data-stu-id="0f555-125">**Cesar de la Torre. Using Resilient Entity Framework Core SQL Connections and Transactions** </span></span>\
  <https://devblogs.microsoft.com/cesardelatorre/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>

>[!div class="step-by-step"]
><span data-ttu-id="0f555-126">[Precedente](implement-retries-exponential-backoff.md)
>[Successivo](explore-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="0f555-126">[Previous](implement-retries-exponential-backoff.md)
[Next](explore-custom-http-call-retries-exponential-backoff.md)</span></span>
