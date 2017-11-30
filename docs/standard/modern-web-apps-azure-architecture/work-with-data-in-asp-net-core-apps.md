---
title: Utilizzare i dati in app di ASP.NET Core
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | utilizzo dei dati in asp
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: bcb8f7bbfa83db9c86cd1278a89750b9f02061d9
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="04b94-103">Utilizzo dei dati nelle applicazioni ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="04b94-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="04b94-104">"Dati un aspetto preziosi e durano più tempo rispetto a sistemi stessi".</span><span class="sxs-lookup"><span data-stu-id="04b94-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>

<span data-ttu-id="04b94-105">Tim Berners-Lee</span><span class="sxs-lookup"><span data-stu-id="04b94-105">Tim Berners-Lee</span></span>

## <a name="summary"></a><span data-ttu-id="04b94-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="04b94-106">Summary</span></span>

<span data-ttu-id="04b94-107">Accesso ai dati è una parte importante di quasi tutte le applicazioni software.</span><span class="sxs-lookup"><span data-stu-id="04b94-107">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="04b94-108">ASP.NET Core supporta un'ampia gamma di opzioni di accesso a dati, tra cui Entity Framework Core (e anche Entity Framework 6) e può funzionare con qualsiasi accesso ai dati di .NET framework.</span><span class="sxs-lookup"><span data-stu-id="04b94-108">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="04b94-109">La scelta dei quali accesso ai dati framework da utilizzare dipende dalle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="04b94-109">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="04b94-110">Fornire l'astrazione di tali scelte dai progetti ApplicationCore e l'interfaccia utente e incapsulare dettagli di implementazione nell'infrastruttura, consente di produrre verificabili regime di controllo software.</span><span class="sxs-lookup"><span data-stu-id="04b94-110">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="04b94-111">Entity Framework Core (per i database relazionali)</span><span class="sxs-lookup"><span data-stu-id="04b94-111">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="04b94-112">Se si sta scrivendo una nuova applicazione ASP.NET di base che deve essere utilizzato con dati relazionali, Entity Framework Core (Core EF) è il modo consigliato per l'applicazione di accedere ai relativi dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-112">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="04b94-113">EF Core è un mapping relazionale a oggetti (O/RM) che consente agli sviluppatori di .NET in modo permanente gli oggetti in e da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-113">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="04b94-114">Elimina la necessità per la maggior parte degli sviluppatori in genere necessario scrivere il codice di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-114">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="04b94-115">Ad esempio ASP.NET Core, EF Core è stato riscritto da zero per le applicazioni multipiattaforma modulare di supporto.</span><span class="sxs-lookup"><span data-stu-id="04b94-115">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="04b94-116">Aggiungerlo all'applicazione come pacchetto NuGet, configurarlo in avvio e richiesta tramite l'inserimento di dipendenze ovunque sia necessaria.</span><span class="sxs-lookup"><span data-stu-id="04b94-116">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="04b94-117">Per usare EF Core con un database di SQL Server, eseguire il comando CLI dotnet seguente:</span><span class="sxs-lookup"><span data-stu-id="04b94-117">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

<span data-ttu-id="04b94-118">dotnet aggiungere pacchetto Microsoft.EntityFrameworkCore.SqlServer</span><span class="sxs-lookup"><span data-stu-id="04b94-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span></span>

<span data-ttu-id="04b94-119">Per aggiungere il supporto per un'origine dati InMemory, per il test:</span><span class="sxs-lookup"><span data-stu-id="04b94-119">To add support for an InMemory data source, for testing:</span></span>

<span data-ttu-id="04b94-120">dotnet aggiungere pacchetto Microsoft.EntityFrameworkCore.InMemory</span><span class="sxs-lookup"><span data-stu-id="04b94-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span></span>

### <a name="the-dbcontext"></a><span data-ttu-id="04b94-121">L'elemento DbContext</span><span class="sxs-lookup"><span data-stu-id="04b94-121">The DbContext</span></span>

<span data-ttu-id="04b94-122">Per utilizzare i componenti di base di Entity Framework, è necessario una sottoclasse di DbContext.</span><span class="sxs-lookup"><span data-stu-id="04b94-122">To work with EF Core, you need a subclass of DbContext.</span></span> <span data-ttu-id="04b94-123">Questa classe contiene proprietà che rappresentano raccolte di entità a cui che l'applicazione funzionerà con.</span><span class="sxs-lookup"><span data-stu-id="04b94-123">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="04b94-124">L'esempio eShopOnWeb include un CatalogContext con le raccolte per gli elementi, i marchi e i tipi:</span><span class="sxs-lookup"><span data-stu-id="04b94-124">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {

    }

    public DbSet<CatalogItem> CatalogItems { get; set; }

    public DbSet<CatalogBrand> CatalogBrands { get; set; }

    public DbSet<CatalogType> CatalogTypes { get; set; }
}
```

<span data-ttu-id="04b94-125">Il DbContext deve avere un costruttore che accetta DbContextOptions e passare il costruttore DbContext base di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="04b94-125">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="04b94-126">Si noti che se si dispone di un solo elemento DbContext nell'applicazione, è possibile passare un'istanza di DbContextOptions, ma se dispone di più di un è necessario utilizzare il generico DbContextOptions<T> tipo, passando il tipo DbContext come parametro generico.</span><span class="sxs-lookup"><span data-stu-id="04b94-126">Note that if you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="04b94-127">Configurazione di Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="04b94-127">Configuring EF Core</span></span>

<span data-ttu-id="04b94-128">Nell'applicazione ASP.NET di base, si configurerà in genere EF Core nel metodo ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="04b94-128">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="04b94-129">Componenti di base di Entity Framework Usa un DbContextOptionsBuilder, che supporta diversi metodi di estensione utili per semplificare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="04b94-129">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="04b94-130">Per configurare CatalogContext per utilizzare un database di SQL Server con una stringa di connessione definita nella configurazione, aggiungere il codice seguente per ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="04b94-130">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="04b94-131">Per usare il database in memoria:</span><span class="sxs-lookup"><span data-stu-id="04b94-131">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="04b94-132">Dopo aver installato EF Core, un tipo figlio DbContext creato e configurato nel ConfigureServices, si è pronti per utilizzare componenti di base di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="04b94-132">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="04b94-133">È possibile richiedere un'istanza del tipo DbContext in qualsiasi servizio che ha bisogno e iniziare a lavorare con le entità persistente utilizzando LINQ come se fossero semplicemente in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="04b94-133">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="04b94-134">Core EF esegue le operazioni di conversione di espressioni LINQ in query SQL per archiviare e recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-134">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="04b94-135">È possibile visualizzare le query è in esecuzione Core EF configurando un logger e garantire il livello è impostato su almeno informazioni, come illustrato nella figura 8-1.</span><span class="sxs-lookup"><span data-stu-id="04b94-135">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![](./media/image8-1.png)

<span data-ttu-id="04b94-136">Figura 8-1 query di registrazione EF Core nella console</span><span class="sxs-lookup"><span data-stu-id="04b94-136">Figure 8-1 Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="04b94-137">Recupero e l'archiviazione dei dati</span><span class="sxs-lookup"><span data-stu-id="04b94-137">Fetching and Storing Data</span></span>

<span data-ttu-id="04b94-138">Per recuperare dati da Entity Framework Core, accedere alla proprietà appropriata e utilizzare LINQ per filtrare il risultato.</span><span class="sxs-lookup"><span data-stu-id="04b94-138">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="04b94-139">È inoltre possibile utilizzare LINQ per eseguire proiezione, di trasformazione del risultato da un tipo a un altro.</span><span class="sxs-lookup"><span data-stu-id="04b94-139">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="04b94-140">Nell'esempio seguente si recupererebbe CatalogBrands, ordinati per nome e filtrati per la proprietà Enabled proiettato su un tipo SelectListItem:</span><span class="sxs-lookup"><span data-stu-id="04b94-140">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="04b94-141">È importante nell'esempio precedente per aggiungere la chiamata a ToListAsync per eseguire immediatamente la query.</span><span class="sxs-lookup"><span data-stu-id="04b94-141">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="04b94-142">In caso contrario, l'istruzione verrà assegnato un IQueryable<SelectListItem> a brandItems, che non verranno eseguiti finché viene enumerata.</span><span class="sxs-lookup"><span data-stu-id="04b94-142">Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="04b94-143">Esistono vantaggi e svantaggi nella restituzione di risultati IQueryable di metodi.</span><span class="sxs-lookup"><span data-stu-id="04b94-143">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="04b94-144">Consente la query che verrà costruito EF Core per essere ulteriormente modificata, ma vengono anche restituiti errori che si verificano solo in fase di esecuzione, se le operazioni vengono aggiunti alla query che non è possibile convertire EF Core.</span><span class="sxs-lookup"><span data-stu-id="04b94-144">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="04b94-145">È in genere preferibile passare tutti i filtri al metodo esegue l'accesso ai dati e restituire il backup di una raccolta in memoria (ad esempio, l'elenco<T>) come risultato.</span><span class="sxs-lookup"><span data-stu-id="04b94-145">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.</span></span>

<span data-ttu-id="04b94-146">Core EF tiene traccia delle modifiche alle entità che vengono recuperati dalla persistenza.</span><span class="sxs-lookup"><span data-stu-id="04b94-146">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="04b94-147">Per salvare le modifiche a un'entità rilevata, chiamare semplicemente il metodo SaveChanges su DbContext, assicurandosi che è la stessa istanza di DbContext che è stata usata per recuperare l'entità.</span><span class="sxs-lookup"><span data-stu-id="04b94-147">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="04b94-148">Aggiunta e rimozione di entità è direttamente sulla proprietà DbSet appropriata, con una chiamata al metodo SaveChanges per eseguire i comandi di database.</span><span class="sxs-lookup"><span data-stu-id="04b94-148">Adding and removing entities is directly on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="04b94-149">Nell'esempio seguente viene aggiunta, aggiornamento e rimozione di entità dalla persistenza.</span><span class="sxs-lookup"><span data-stu-id="04b94-149">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

```csharp
// create
var newBrand = new CatalogBrand() { Brand = "Acme" };
_context.Add(newBrand);
await _context.SaveChangesAsync();

// read and update
var existingBrand = _context.CatalogBrands.Find(1);
existingBrand.Brand = "Updated Brand";
await _context.SaveChangesAsync();

// read and delete (alternate Find syntax)
var brandToDelete = _context.Find<CatalogBrand>(2);
_context.CatalogBrands.Remove(brandToDelete);
await _context.SaveChangesAsync();
```

<span data-ttu-id="04b94-150">Core EF supporta sia sincrono e i metodi asincroni per il recupero e il salvataggio.</span><span class="sxs-lookup"><span data-stu-id="04b94-150">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="04b94-151">Nelle applicazioni web, si consiglia di utilizzare il modello async/await con i metodi asincroni, in modo che i thread del server web non vengono bloccati durante l'attesa di dati per completare le operazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="04b94-151">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="04b94-152">Recupero dei dati correlati</span><span class="sxs-lookup"><span data-stu-id="04b94-152">Fetching Related Data</span></span>

<span data-ttu-id="04b94-153">Quando EF Core recupera le entità, viene compilata tutte le proprietà che vengono archiviate direttamente con tale entità nel database.</span><span class="sxs-lookup"><span data-stu-id="04b94-153">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="04b94-154">Le proprietà di navigazione, quali gli elenchi di entità correlate, non vengono popolate e può avere il valore impostato su null.</span><span class="sxs-lookup"><span data-stu-id="04b94-154">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="04b94-155">In questo modo che core EF non recupera ulteriori dati superiore al necessario, che è particolarmente importante per applicazioni web, che rapidamente è necessario elaborare le richieste e restituire risposte in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="04b94-155">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="04b94-156">Per includere le relazioni con un'entità mediante *caricamento eager*, per specificare la proprietà utilizzando il metodo di estensione di includere nella query, come illustrato:</span><span class="sxs-lookup"><span data-stu-id="04b94-156">To include relationships with an entity using *eager loading*, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="04b94-157">È possibile includere più relazioni, ed è anche possibile includere relazioni secondario utilizzando ThenInclude.</span><span class="sxs-lookup"><span data-stu-id="04b94-157">You can include multiple relationships, and you can also include sub-relationships using ThenInclude.</span></span> <span data-ttu-id="04b94-158">Core EF eseguirà una singola query per recuperare il set di entità.</span><span class="sxs-lookup"><span data-stu-id="04b94-158">EF Core will execute a single query to retrieve the resulting set of entities.</span></span>

<span data-ttu-id="04b94-159">Per il caricamento dei dati correlati un'altra opzione consiste nell'utilizzare *caricamento esplicito*.</span><span class="sxs-lookup"><span data-stu-id="04b94-159">Another option for loading related data is to use *explicit loading*.</span></span> <span data-ttu-id="04b94-160">Caricamento esplicito consente di caricare dati aggiuntivi in un'entità che è già stata recuperata.</span><span class="sxs-lookup"><span data-stu-id="04b94-160">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="04b94-161">Poiché si prevede una richiesta separata al database, non è consigliabile per applicazioni web, che è consigliabile ridurre al minimo il numero di database eseguite per ogni richiesta di round trip.</span><span class="sxs-lookup"><span data-stu-id="04b94-161">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="04b94-162">*Caricamento lazy* è una funzionalità che consente di caricare automaticamente i dati correlati perché fa riferimento l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="04b94-162">*Lazy loading* is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="04b94-163">Attualmente non è supportata da Entity Framework Core, ma come con il caricamento esplicito deve in genere essere disattivato per le applicazioni web.</span><span class="sxs-lookup"><span data-stu-id="04b94-163">It's not currently supported by EF Core, but as with explicit loading it should typically be disabled for web applications.</span></span>

### <a name="resilient-connections"></a><span data-ttu-id="04b94-164">Connessioni resilienti</span><span class="sxs-lookup"><span data-stu-id="04b94-164">Resilient Connections</span></span>

<span data-ttu-id="04b94-165">Risorse esterne quali database SQL in alcuni casi potrebbero essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="04b94-165">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="04b94-166">In caso di indisponibilità temporanea, le applicazioni è possono utilizzare logica di riesecuzione per evitare la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="04b94-166">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="04b94-167">Questa tecnica è conosciuta come *resilienza delle connessioni*.</span><span class="sxs-lookup"><span data-stu-id="04b94-167">This technique is commonly referred to as *connection resiliency*.</span></span> <span data-ttu-id="04b94-168">È possibile implementare il [proprio tentativi con backoff esponenziale](https://docs.microsoft.com/azure/architecture/patterns/retry) tecnica mediante un tentativo di ripetizione con un tempo di attesa aumenta in modo esponenziale, fino a quando non è stato raggiunto un numero massimo di tentativi.</span><span class="sxs-lookup"><span data-stu-id="04b94-168">You can implement your [own retry with exponential backoff](https://docs.microsoft.com/azure/architecture/patterns/retry) technique by attempting to rety with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="04b94-169">Questa tecnica basata sul modello il fatto che le risorse cloud in modo intermittente siano disponibili per brevi periodi di tempo, causando un errore di alcune richieste.</span><span class="sxs-lookup"><span data-stu-id="04b94-169">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="04b94-170">Per il database di SQL Azure, Entity Framework Core fornisce già logica resilienza e tentativi di connessione database interno.</span><span class="sxs-lookup"><span data-stu-id="04b94-170">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="04b94-171">Ma è necessario abilitare la strategia di esecuzione di Entity Framework per ogni connessione DbContext se si desidera disporre di connessioni Core EF resiliente.</span><span class="sxs-lookup"><span data-stu-id="04b94-171">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="04b94-172">Ad esempio, il codice seguente a livello di connessione Entity Framework Core consente connessioni SQL resilienti che vengono ripetute nel caso di connessione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="04b94-172">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        //...
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
```

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="04b94-173">Strategie di esecuzione e le transazioni esplicite utilizzando BeginTransaction e più DbContexts</span><span class="sxs-lookup"><span data-stu-id="04b94-173">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span> 
  
  <span data-ttu-id="04b94-174">Quando i tentativi sono abilitati nelle connessioni di Entity Framework Core, ogni operazione effettuata usando EF Core diventa il proprio possibilità di ritentare.</span><span class="sxs-lookup"><span data-stu-id="04b94-174">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="04b94-175">Ogni query e ogni chiamata al metodo SaveChanges verrà ritentate come unità se si verifica un errore temporaneo.</span><span class="sxs-lookup"><span data-stu-id="04b94-175">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>
  
  <span data-ttu-id="04b94-176">Tuttavia, se il codice avvia una transazione utilizzando BeginTransaction, si definisce un proprio gruppo di operazioni che devono essere trattati come un'unità, ovvero tutti gli elementi all'interno della transazione è essere sottoposta a rollback se si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="04b94-176">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="04b94-177">Si verrà generata un'eccezione simile al seguente se si tenta di eseguire tale transazione quando si utilizza una strategia di esecuzione EF (criteri di ripetizione) e si includono più SaveChanges da più DbContexts in essa contenuti.</span><span class="sxs-lookup"><span data-stu-id="04b94-177">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="04b94-178">System. InvalidOperationException: La strategia di esecuzione configurata 'SqlServerRetryingExecutionStrategy' non supporta le transazioni avviate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="04b94-178">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="04b94-179">Utilizzare la strategia di esecuzione restituita da 'DbContext.Database.CreateExecutionStrategy()' per eseguire tutte le operazioni nella transazione come unità possibilità di ritentare.</span><span class="sxs-lookup"><span data-stu-id="04b94-179">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="04b94-180">La soluzione consiste nel richiamare manualmente la strategia di esecuzione EF con un delegato che rappresenta gli elementi che deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="04b94-180">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="04b94-181">Se si verifica un errore temporaneo, la strategia di esecuzione verrà nuovamente richiamare il delegato.</span><span class="sxs-lookup"><span data-stu-id="04b94-181">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="04b94-182">Il codice seguente viene illustrato come implementare questo approccio:</span><span class="sxs-lookup"><span data-stu-id="04b94-182">The following code shows how to implement this approach:</span></span>

```csharp
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
```

<span data-ttu-id="04b94-183">Il primo elemento DbContext è il \_catalogContext e il secondo elemento DbContext è all'interno di \_integrationEventLogService oggetto.</span><span class="sxs-lookup"><span data-stu-id="04b94-183">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="04b94-184">Infine, il Commit di azione da eseguita più DbContexts e l'utilizzo di una strategia di esecuzione di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="04b94-184">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="04b94-185">Riferimenti: Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="04b94-185">References – Entity Framework Core</span></span>
> - <span data-ttu-id="04b94-186">**Documenti principali di Entity Framework**</span><span class="sxs-lookup"><span data-stu-id="04b94-186">**EF Core Docs**</span></span>  
> <span data-ttu-id="04b94-187"><https://docs.microsoft.com/EF/></span><span class="sxs-lookup"><span data-stu-id="04b94-187"><https://docs.microsoft.com/ef/></span></span>
> - <span data-ttu-id="04b94-188">**EF principale: Dati correlati**</span><span class="sxs-lookup"><span data-stu-id="04b94-188">**EF Core: Related Data**</span></span>  
> <span data-ttu-id="04b94-189"><https://docs.microsoft.com/EF/core/Querying/Related-Data></span><span class="sxs-lookup"><span data-stu-id="04b94-189"><https://docs.microsoft.com/ef/core/querying/related-data></span></span>
> - <span data-ttu-id="04b94-190">**Evitare il caricamento Lazy entità nelle applicazioni ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="04b94-190">**Avoid Lazy Loading Entities in ASPNET Applications**</span></span>  
> <span data-ttu-id="04b94-191"><http://ardalis.com/Avoid-lazy-Loading-Entities-in-ASP-NET-Applications></span><span class="sxs-lookup"><span data-stu-id="04b94-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span></span>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="04b94-192">Componenti di base EF o prodotto ORM micro?</span><span class="sxs-lookup"><span data-stu-id="04b94-192">EF Core or micro-ORM?</span></span>

<span data-ttu-id="04b94-193">EF Core è un'ottima scelta per la gestione di persistenza, mentre per la maggior parte incapsula i dettagli del database da parte degli sviluppatori dell'applicazione, non è l'unica scelta.</span><span class="sxs-lookup"><span data-stu-id="04b94-193">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it is not the only choice.</span></span> <span data-ttu-id="04b94-194">È un'alternativa open source comuni [Dapper](https://github.com/StackExchange/Dapper), un cosiddetto prodotto ORM micro.</span><span class="sxs-lookup"><span data-stu-id="04b94-194">Another popular open source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="04b94-195">Un prodotto ORM micro è un tipo semplice, meno strumento completo per il mapping di oggetti di strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-195">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="04b94-196">Nel caso di Dapper, la progettazione degli obiettivi di concentrarsi sulle prestazioni, anziché completamente incapsulamento sottostante sottoposto a query viene utilizzato per recuperare e aggiornare i dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-196">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="04b94-197">Poiché non astratto SQL da parte dello sviluppatore, Dapper "più vicino a metallo" e consente agli sviluppatori di scrivere la query da utilizzare per i dati di un determinata operazione di accedere.</span><span class="sxs-lookup"><span data-stu-id="04b94-197">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="04b94-198">Core EF dispone di due importanti funzionalità che fornisce che lo separano dal Dapper ma è aggiungere anche il relativo overhead delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="04b94-198">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="04b94-199">Il primo è una conversione da LINQ. expressions in SQL.</span><span class="sxs-lookup"><span data-stu-id="04b94-199">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="04b94-200">Queste conversioni vengono memorizzati nella cache, ma anche in questo caso è overhead durante la prima volta.</span><span class="sxs-lookup"><span data-stu-id="04b94-200">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="04b94-201">Il secondo è rilevamento delle modifiche per le entità (in modo che le istruzioni update efficiente possono essere generate).</span><span class="sxs-lookup"><span data-stu-id="04b94-201">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="04b94-202">Questo comportamento può essere disattivato per query specifiche tramite l'estensione AsNotTracking.</span><span class="sxs-lookup"><span data-stu-id="04b94-202">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="04b94-203">Core EF genera anche le query SQL che in genere sono molto efficienti e in ogni caso è perfettamente accettabile dal punto di vista delle prestazioni, ma se è necessario maggiore controllo sulla query precisa deve essere eseguito, è possibile passare in SQL personalizzato (o eseguire una stored procedure) mediante EF Troppo Core.</span><span class="sxs-lookup"><span data-stu-id="04b94-203">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="04b94-204">In questo caso, ancora Dapper supera EF Core, ma solo leggermente.</span><span class="sxs-lookup"><span data-stu-id="04b94-204">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="04b94-205">Julie Lerman presenta alcuni dati sulle prestazioni nel proprio potrebbero articolo MSDN 2016 [Dapper, Entity Framework e App ibride](https://msdn.microsoft.com/magazine/mt703432.aspx).</span><span class="sxs-lookup"><span data-stu-id="04b94-205">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span></span> <span data-ttu-id="04b94-206">Dati aggiuntivi delle prestazioni benchmark per un'ampia gamma di metodi di accesso ai dati possono trovarsi in [il sito Dapper](https://github.com/StackExchange/Dapper).</span><span class="sxs-lookup"><span data-stu-id="04b94-206">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="04b94-207">Per vedere come la sintassi per Dapper varia da Entity Framework Core, tenere presenti queste due versioni dello stesso metodo per recuperare un elenco di elementi:</span><span class="sxs-lookup"><span data-stu-id="04b94-207">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

```csharp
// EF Core
private readonly CatalogContext _context;
public async Task<IEnumerable<CatalogType>> GetCatalogTypes()
{
    return await _context.CatalogTypes.ToListAsync();
}

// Dapper
private readonly SqlConnection _conn;
public async Task<IEnumerable<CatalogType>> GetCatalogTypesWithDapper()
{
    return await _conn.QueryAsync<CatalogType>("SELECT * FROM CatalogType");
}
```

<span data-ttu-id="04b94-208">Se è necessario compilare oggetti grafici più complessi con Dapper, è necessario scrivere la query associata (a differenza di aggiunta di un'inclusione esattamente come si farebbe Core EF).</span><span class="sxs-lookup"><span data-stu-id="04b94-208">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="04b94-209">Questa è supportata tramite una varietà di sintassi, tra cui la funzione di Mapping che consente di eseguire il mapping di singole righe a più oggetti con mapping più.</span><span class="sxs-lookup"><span data-stu-id="04b94-209">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="04b94-210">Ad esempio, specifica una classe Post con una proprietà del proprietario del tipo di utente, l'istruzione SQL seguente restituisce tutti i dati necessari:</span><span class="sxs-lookup"><span data-stu-id="04b94-210">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="04b94-211">Ogni riga restituita include dati utente e di Post.</span><span class="sxs-lookup"><span data-stu-id="04b94-211">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="04b94-212">Poiché i dati utente dovrebbero essere collegati ai dati tramite la proprietà Owner Post, viene utilizzata la funzione seguente:</span><span class="sxs-lookup"><span data-stu-id="04b94-212">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="04b94-213">Il listato di codice completo per restituire una raccolta di annunci con la proprietà Owner popolata con i dati utente associati sarebbe:</span><span class="sxs-lookup"><span data-stu-id="04b94-213">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="04b94-214">In quanto offre meno incapsulamento, Dapper richiede gli sviluppatori saperne di più sull'archiviazione dei dati, come eseguire una query in modo efficiente e scrivere codice più per recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="04b94-214">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="04b94-215">Quando viene modificato il modello, anziché semplicemente la creazione di una nuova migrazione (un'altra funzionalità di base di Entity Framework) e/o l'aggiornamento delle informazioni di mapping in un'unica posizione in un elemento DbContext, è necessario aggiornare ogni query che è interessata.</span><span class="sxs-lookup"><span data-stu-id="04b94-215">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="04b94-216">Queste query sono non compilazione ora garanzie, in modo che è possibile interrompere in runtime in risposta alle modifiche al modello o il database, rendendo più difficile rilevare rapidamente gli errori.</span><span class="sxs-lookup"><span data-stu-id="04b94-216">These queries have not compile time guarantees, so they may break at runtime in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="04b94-217">In cambio di questi compromessi, Dapper offre prestazioni molto elevate.</span><span class="sxs-lookup"><span data-stu-id="04b94-217">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="04b94-218">Per la maggior parte delle applicazioni e la maggior parte delle parti di quasi tutte le applicazioni, componenti di base di Entity Framework offre prestazioni accettabili.</span><span class="sxs-lookup"><span data-stu-id="04b94-218">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="04b94-219">Di conseguenza, i vantaggi di produttività per sviluppatori intendono genere superano il relativo overhead delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="04b94-219">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="04b94-220">Per le query che possono trarre vantaggio dalla memorizzazione nella cache, l'effettiva query può essere eseguita solo una piccola percentuale di tempo, rendendo relativamente ridotto di query impostato HDR differenze di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="04b94-220">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="04b94-221">SQL o NoSQL</span><span class="sxs-lookup"><span data-stu-id="04b94-221">SQL or NoSQL</span></span>

<span data-ttu-id="04b94-222">In genere, i database relazionali, ad esempio SQL Server sono dominato marketplace per l'archiviazione dei dati persistenti, ma non sono l'unica soluzione disponibile.</span><span class="sxs-lookup"><span data-stu-id="04b94-222">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="04b94-223">Nei database NoSQL come [MongoDB](https://www.mongodb.com/what-is-mongodb) offrono un approccio diverso per l'archiviazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="04b94-223">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="04b94-224">Anziché oggetti il mapping a tabelle e righe, un'altra opzione è per la serializzazione dell'intero oggetto grafico e memorizza il risultato.</span><span class="sxs-lookup"><span data-stu-id="04b94-224">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="04b94-225">I vantaggi di questo approccio, almeno inizialmente, sono le prestazioni e alla semplicità.</span><span class="sxs-lookup"><span data-stu-id="04b94-225">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="04b94-226">È certamente più semplice archiviare un singolo oggetto serializzato con una chiave rispetto al scomporre l'oggetto in molte tabelle con relazioni e aggiornamento e le righe che potrebbero essere modificate dall'ultima volta l'oggetto recupero dal database.</span><span class="sxs-lookup"><span data-stu-id="04b94-226">It's certainly simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="04b94-227">Analogamente, il recupero e la deserializzazione di un singolo oggetto da un archivio basato su chiavi è in genere molto più veloce e più semplice che complesso join o più query di database necessarie per comporre completamente lo stesso oggetto da un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="04b94-227">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="04b94-228">La mancanza di blocchi o le transazioni o uno schema fisso rende inoltre database NoSQL molto adatti per la scalabilità su molti computer, che supporta i set di dati molto grandi.</span><span class="sxs-lookup"><span data-stu-id="04b94-228">The lack of locks or transactions or a fixed schema also makes NoSQL databases very amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="04b94-229">D'altra parte, nei database NoSQL (come in genere vengono definite) hanno svantaggi.</span><span class="sxs-lookup"><span data-stu-id="04b94-229">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="04b94-230">Database relazionali Usa la normalizzazione per garantire la coerenza ed evitare la duplicazione di dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-230">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="04b94-231">Ciò riduce le dimensioni totali del database e si assicura che gli aggiornamenti ai dati condivisi sono disponibili immediatamente in tutto il database.</span><span class="sxs-lookup"><span data-stu-id="04b94-231">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="04b94-232">In un database relazionale, una tabella di indirizzi potrebbe fare riferimento una tabella paese dall'ID, in modo che se il nome di un paese sono stato modificato, i record degli indirizzi può costituire un vantaggio rispetto all'aggiornamento di non dover essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="04b94-232">In a relational database, an Address table might reference a Country table by ID, such that if a country's name were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="04b94-233">Tuttavia, in un database NoSQL, indirizzo e il paese associato potrebbe essere serializzato come parte di molti degli oggetti archiviati.</span><span class="sxs-lookup"><span data-stu-id="04b94-233">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="04b94-234">Tali oggetti da aggiornare, anziché una singola riga richiede un aggiornamento di un nome di paese.</span><span class="sxs-lookup"><span data-stu-id="04b94-234">An update to a country name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="04b94-235">Database relazionali possono inoltre garantire l'integrità relazionale tramite l'applicazione delle regole, come chiavi esterne.</span><span class="sxs-lookup"><span data-stu-id="04b94-235">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="04b94-236">Nei database NoSQL non offrono in genere i vincoli per i propri dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-236">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="04b94-237">Complessità di un altro NoSQL devono gestire i database è il controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="04b94-237">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="04b94-238">Quando modificare proprietà di un oggetto, potrebbe non essere in grado di deserializzare dalle versioni precedenti che sono state archiviate.</span><span class="sxs-lookup"><span data-stu-id="04b94-238">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="04b94-239">Di conseguenza, è necessario aggiornare tutti gli oggetti esistenti con una versione (precedente) serializzata dell'oggetto per rispettare il nuovo schema.</span><span class="sxs-lookup"><span data-stu-id="04b94-239">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="04b94-240">Questo non è concettualmente diverso da un database relazionale, in cui modifiche dello schema talvolta richiedono script di aggiornamento o il mapping degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="04b94-240">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="04b94-241">Tuttavia, il numero di voci che deve essere modificato è spesso molto maggiore nell'approccio NoSQL, poiché non esiste più di duplicazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-241">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="04b94-242">È possibile nei database NoSQL di archiviare più versioni di oggetti, database relazionali di uno schema fisso che non è in genere supportano.</span><span class="sxs-lookup"><span data-stu-id="04b94-242">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="04b94-243">Tuttavia, in questo caso il codice dell'applicazione sarà necessario tenere conto per l'esistenza delle versioni precedenti di oggetti, l'aggiunta di complessità.</span><span class="sxs-lookup"><span data-stu-id="04b94-243">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="04b94-244">In genere nei database NoSQL non applicano [ACID](http://en.wikipedia.org/wiki/ACID), ovvero presentano vantaggi di prestazioni e scalabilità su database relazionali.</span><span class="sxs-lookup"><span data-stu-id="04b94-244">NoSQL databases typically do not enforce [ACID](http://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="04b94-245">Si tratta di ideale per grandi set di dati e gli oggetti che non sono particolarmente adatti per l'archiviazione nelle strutture tabella normalizzata.</span><span class="sxs-lookup"><span data-stu-id="04b94-245">They're well-suited to extremely large datasets and objects that are not well-suited to storage in normalized table structures.</span></span> <span data-ttu-id="04b94-246">Non è necessario perché una singola applicazione non è possibile trarre vantaggio da entrambi relazionale e nei database NoSQL, con ogni in cui è preferibile adatto.</span><span class="sxs-lookup"><span data-stu-id="04b94-246">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-documentdb"></a><span data-ttu-id="04b94-247">Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="04b94-247">Azure DocumentDB</span></span>

<span data-ttu-id="04b94-248">Azure DocumentDB è un servizio di database NoSQL completamente gestito che offre l'archiviazione di dati privi di schema basato su cloud.</span><span class="sxs-lookup"><span data-stu-id="04b94-248">Azure DocumentDB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="04b94-249">DocumentDB è stato compilato per prestazioni rapida e prevedibile, la disponibilità elevata, scalabilità elastica e distribuzione globale.</span><span class="sxs-lookup"><span data-stu-id="04b94-249">DocumentDB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="04b94-250">Nonostante sia un database NoSQL, gli sviluppatori possono utilizzare rich e familiare funzionalità di query SQL sui dati JSON.</span><span class="sxs-lookup"><span data-stu-id="04b94-250">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="04b94-251">Tutte le risorse in DocumentDB vengono archiviate come documenti JSON.</span><span class="sxs-lookup"><span data-stu-id="04b94-251">All resources in DocumentDB are stored as JSON documents.</span></span> <span data-ttu-id="04b94-252">Le risorse vengono gestite come *elementi*, che sono documenti che contengono i metadati, e *feed*, che sono raccolte di elementi.</span><span class="sxs-lookup"><span data-stu-id="04b94-252">Resources are managed as *items*, which are documents containing metadata, and *feeds*, which are collections of items.</span></span> <span data-ttu-id="04b94-253">Figura 8-2 viene illustrata la relazione tra le diverse risorse di DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="04b94-253">Figure 8-2 shows the relationship between different DocumentDB resources.</span></span>


![La relazione gerarchica tra le risorse di DocumentDB, un database NoSQL JSON](./media/image8-2.png)

<span data-ttu-id="04b94-255">**Figura 8-2.**</span><span class="sxs-lookup"><span data-stu-id="04b94-255">**Figure 8-2.**</span></span> <span data-ttu-id="04b94-256">Organizzazione di risorse di DocumentDB.</span><span class="sxs-lookup"><span data-stu-id="04b94-256">DocumentDB resource organization.</span></span>

<span data-ttu-id="04b94-257">Il linguaggio di query di DocumentDB è un'interfaccia semplice e potente per eseguire query sui documenti JSON.</span><span class="sxs-lookup"><span data-stu-id="04b94-257">The DocumentDB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="04b94-258">Il linguaggio supporta un sottoinsieme di grammatica SQL ANSI e aggiunge l'integrazione di oggetti, matrici, la costruzione di oggetti e chiamata di funzione JavaScript.</span><span class="sxs-lookup"><span data-stu-id="04b94-258">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="04b94-259">**Riferimenti: DocumentDB**</span><span class="sxs-lookup"><span data-stu-id="04b94-259">**References – DocumentDB**</span></span>

-   <span data-ttu-id="04b94-260">DocumentDB Introduction\\</span><span class="sxs-lookup"><span data-stu-id="04b94-260">DocumentDB Introduction\\</span></span>
    <span data-ttu-id="04b94-261"><https://docs.microsoft.com/Azure/documentdb/documentdb-Introduction></span><span class="sxs-lookup"><span data-stu-id="04b94-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span></span>

## <a name="other-persistence-options"></a><span data-ttu-id="04b94-262">Altre opzioni di persistenza</span><span class="sxs-lookup"><span data-stu-id="04b94-262">Other Persistence Options</span></span>

<span data-ttu-id="04b94-263">Oltre ai dati relazionali e le opzioni di archiviazione di database NoSQL, applicazioni ASP.NET Core consente di archiviazione di Azure per archiviare una varietà di formati di dati e i file in modo scalabile e basate su cloud.</span><span class="sxs-lookup"><span data-stu-id="04b94-263">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="04b94-264">Archiviazione di Azure è altamente scalabile, pertanto è possibile avviare out archiviare piccole quantità di dati e la scala fino a archiviazione centinaia di terabyte, se richiesto dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="04b94-264">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="04b94-265">Archiviazione di Azure supporta quattro tipi di dati:</span><span class="sxs-lookup"><span data-stu-id="04b94-265">Azure Storage supports four kinds of data:</span></span>

-   <span data-ttu-id="04b94-266">Archiviazione BLOB di testo non strutturato o archiviazione binario, detta anche archiviazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="04b94-266">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

-   <span data-ttu-id="04b94-267">Archiviazione tabelle per set di dati strutturati, accessibile tramite chiavi di riga.</span><span class="sxs-lookup"><span data-stu-id="04b94-267">Table Storage for structured datasets, accessible via row keys.</span></span>

-   <span data-ttu-id="04b94-268">Archiviazione delle code di messaggistica affidabile basata su coda.</span><span class="sxs-lookup"><span data-stu-id="04b94-268">Queue Storage for reliable queue-based messaging.</span></span>

-   <span data-ttu-id="04b94-269">L'archiviazione dei file per l'accesso a file condivisi tra macchine virtuali di Azure e applicazioni locali.</span><span class="sxs-lookup"><span data-stu-id="04b94-269">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="04b94-270">**Riferimenti: archiviazione di Azure**</span><span class="sxs-lookup"><span data-stu-id="04b94-270">**References – Azure Storage**</span></span>

-   <span data-ttu-id="04b94-271">Introduction\ di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="04b94-271">Azure Storage Introduction\\</span></span>
    <span data-ttu-id="04b94-272"><https://docs.microsoft.com/Azure/Storage/Storage-Introduction></span><span class="sxs-lookup"><span data-stu-id="04b94-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span></span>

## <a name="caching"></a><span data-ttu-id="04b94-273">Memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="04b94-273">Caching</span></span>

<span data-ttu-id="04b94-274">Nelle applicazioni web, ogni richiesta web deve essere completata in minor tempo possibile.</span><span class="sxs-lookup"><span data-stu-id="04b94-274">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="04b94-275">Un modo per ottenere questo risultato consiste nel limitare il numero di chiamate esterne, che il server è necessario apportare per completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="04b94-275">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="04b94-276">La memorizzazione nella cache comporta l'archiviazione di una copia dei dati nel server o un altro archivio dati che è più facilmente sottoposti a query di origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-276">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="04b94-277">Applicazioni Web e soprattutto le applicazioni web tradizionali non SPA, necessario compilare l'intera interfaccia utente per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="04b94-277">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="04b94-278">Questo comporta spesso l'esecuzione di molte delle stesse query di database ripetutamente da una richiesta di un utente al successivo.</span><span class="sxs-lookup"><span data-stu-id="04b94-278">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="04b94-279">Nella maggior parte dei casi, questo dati vengono modificati raramente, pertanto non c'è motivo di richiederla costantemente dal database.</span><span class="sxs-lookup"><span data-stu-id="04b94-279">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="04b94-280">ASP.NET Core supporta la memorizzazione nella cache risposta, per la memorizzazione nella cache intere pagine e la memorizzazione nella cache di dati, che supporta il comportamento di memorizzazione nella cache più granulare.</span><span class="sxs-lookup"><span data-stu-id="04b94-280">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="04b94-281">Quando si implementa la memorizzazione nella cache, è importante tenere separazione presente delle problematiche.</span><span class="sxs-lookup"><span data-stu-id="04b94-281">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="04b94-282">Evitare di implementazione della logica di memorizzazione nella cache della logica di accesso ai dati o in un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="04b94-282">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="04b94-283">Incapsulare la memorizzazione nella cache nelle proprie classi e utilizzare una configurazione per gestire il comportamento.</span><span class="sxs-lookup"><span data-stu-id="04b94-283">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="04b94-284">Si attiene ai aperto o chiuso e i principi unica responsabilità e renderà più facile per gestire l'utilizzo di memorizzazione nella cache nell'applicazione di si sviluppa.</span><span class="sxs-lookup"><span data-stu-id="04b94-284">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="04b94-285">La memorizzazione nella cache di ASP.NET Core risposta</span><span class="sxs-lookup"><span data-stu-id="04b94-285">ASP.NET Core Response Caching</span></span>

<span data-ttu-id="04b94-286">ASP.NET Core supporta due livelli di memorizzazione nella cache di risposta.</span><span class="sxs-lookup"><span data-stu-id="04b94-286">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="04b94-287">Il primo livello non memorizzare nella cache qualsiasi elemento nel server, ma aggiunge le intestazioni HTTP che indicano i client e server proxy per memorizzare risposte.</span><span class="sxs-lookup"><span data-stu-id="04b94-287">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="04b94-288">Ciò viene implementato, aggiungere l'attributo ResponseCache ai singoli controller o azioni:</span><span class="sxs-lookup"><span data-stu-id="04b94-288">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }
    
    ViewData["Message"] = "Your contact page.";
    return View();
}

The above example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.

Cache-Control: public,max-age=60

In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware. This middleware is configured in both ConfigureServices and Configure in Startup:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddResponseCaching();
}

public void Configure(IApplicationBuilder app)
{
    app.UseResponseCaching();
}
```

<span data-ttu-id="04b94-289">Il Middleware di memorizzazione nella cache della risposta verrà automaticamente nella cache le risposte in base a un set di condizioni, che è possibile personalizzare.</span><span class="sxs-lookup"><span data-stu-id="04b94-289">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="04b94-290">Per impostazione predefinita, vengono memorizzati nella cache le risposte solo 200 (OK), richieste tramite i metodi GET o HEAD.</span><span class="sxs-lookup"><span data-stu-id="04b94-290">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="04b94-291">Inoltre, le richieste devono avere una risposta con una Cache-Control: intestazione pubblica e non può includere le intestazioni per l'autorizzazione o Set-Cookie.</span><span class="sxs-lookup"><span data-stu-id="04b94-291">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="04b94-292">Vedere un [elenco completo delle condizioni memorizzazione nella cache utilizzato dalla risposta la memorizzazione nella cache middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span><span class="sxs-lookup"><span data-stu-id="04b94-292">See a [complete list of the caching conditions used by the response caching middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="04b94-293">Memorizzazione di dati</span><span class="sxs-lookup"><span data-stu-id="04b94-293">Data Caching</span></span>

<span data-ttu-id="04b94-294">Anziché (o in aggiunta a) la memorizzazione nella cache le risposte dei web completo, è possibile memorizzare nella cache i risultati delle query di dati singoli.</span><span class="sxs-lookup"><span data-stu-id="04b94-294">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="04b94-295">A tale scopo, è possibile utilizzare la memorizzazione nella cache sul server web o usare [una cache distribuita](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span><span class="sxs-lookup"><span data-stu-id="04b94-295">For this, you can use in memory caching on the web server, or use [a distributed cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="04b94-296">In questa sezione verrà illustrato come implementare in memoria la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="04b94-296">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="04b94-297">Aggiungere il supporto per la memoria (o distribuita) la memorizzazione nella cache in ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="04b94-297">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="04b94-298">Assicurarsi di aggiungere anche il pacchetto Microsoft.Extensions.Caching.Memory NuGet.</span><span class="sxs-lookup"><span data-stu-id="04b94-298">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="04b94-299">Dopo aver aggiunto il servizio, richiesta IMemoryCache tramite l'inserimento di dipendenze ogni volta che è necessario accedere alla cache.</span><span class="sxs-lookup"><span data-stu-id="04b94-299">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="04b94-300">In questo esempio, il CachedCatalogService viene usato il modello di progettazione Proxy (o un elemento Decorator), fornendo un'implementazione alternativa del ICatalogService che controlla l'accesso a (o comportamento aggiunge) l'implementazione di CatalogService sottostante.</span><span class="sxs-lookup"><span data-stu-id="04b94-300">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
    private static readonly string _itemsKeyTemplate = "items-{0}-{1}-{2}-{3}";
    private static readonly TimeSpan _defaultCacheDuration = TimeSpan.FromSeconds(30);
    public CachedCatalogService(IMemoryCache cache,
    CatalogService catalogService)
    {
        _cache = cache;
        _catalogService = catalogService;
    }
    
    public async Task<IEnumerable<SelectListItem>> GetBrands()
    {
        return await _cache.GetOrCreateAsync(_brandsKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetBrands();
        });
    }
    
    public async Task<Catalog> GetCatalogItems(int pageIndex, int itemsPage, int? brandID, int? typeId)
    {
        string cacheKey = String.Format(_itemsKeyTemplate, pageIndex, itemsPage, brandID, typeId);
        return await _cache.GetOrCreateAsync(cacheKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetCatalogItems(pageIndex, itemsPage, brandID, typeId);
        });
    }
    
    public async Task<IEnumerable<SelectListItem>> GetTypes()
    {
        return await _cache.GetOrCreateAsync(_typesKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetTypes();
        });
    }
}
```

<span data-ttu-id="04b94-301">Per configurare l'applicazione di utilizzare la versione memorizzata nella cache del servizio, ma consentono ancora il servizio per l'istanza di CatalogService necessarie nel relativo costruttore, è necessario aggiungere quanto segue in ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="04b94-301">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="04b94-302">A questo punto, le chiamate del database per recuperare i dati del catalogo verranno effettuate solo una volta al minuto, piuttosto che a ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="04b94-302">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="04b94-303">In base al traffico al sito, questo può avere un impatto significativo sul numero di query eseguite per il database e il tempo medio di caricamento per la home page che attualmente dipende tutte e tre le query esposti da questo servizio.</span><span class="sxs-lookup"><span data-stu-id="04b94-303">Depending on the traffic to the site, this can have a very significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="04b94-304">È un problema che si verifica quando viene implementata la memorizzazione nella cache *dati non aggiornati* –, ovvero i dati modificati in una versione aggiornata, ma l'origine rimangono nella cache.</span><span class="sxs-lookup"><span data-stu-id="04b94-304">An issue that arises when caching is implemented is *stale data* – that is, data that has changed at the source but an out of date version remains in the cache.</span></span> <span data-ttu-id="04b94-305">Un modo semplice per risolvere questo problema è utilizzare la durata della cache piccola, poiché per un'applicazione occupata è limitato benefici per estendere la lunghezza dei dati viene memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="04b94-305">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="04b94-306">Si consideri ad esempio una pagina che esegue una query di singolo database, e viene richiesto di 10 volte al secondo.</span><span class="sxs-lookup"><span data-stu-id="04b94-306">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="04b94-307">Se questa pagina viene memorizzato nella cache per un minuto, si verificherà il numero di query di database eseguite al minuto per eliminare da 600 a una riduzione 99,8% 1.</span><span class="sxs-lookup"><span data-stu-id="04b94-307">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="04b94-308">Se invece la durata della cache sono stata apportata a un'ora, la riduzione complessiva sarebbe 99.997%, ma ora l'età di probabilità e il potenziale di dati non aggiornati sono entrambi aumenta notevolmente.</span><span class="sxs-lookup"><span data-stu-id="04b94-308">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="04b94-309">Un altro approccio consiste nel rimuovere in modo proattivo le voci della cache quando vengono aggiornati i dati in che essi contenuti.</span><span class="sxs-lookup"><span data-stu-id="04b94-309">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="04b94-310">Qualsiasi singola voce può essere rimossa se si conosce la chiave:</span><span class="sxs-lookup"><span data-stu-id="04b94-310">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="04b94-311">Se l'applicazione espone la funzionalità per l'aggiornamento delle voci che memorizza nella cache, è possibile rimuovere le voci della cache corrispondente nel codice che esegue gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="04b94-311">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="04b94-312">In alcuni casi potrebbero essere presenti numerose voci diverse che dipendono da un particolare set di dati.</span><span class="sxs-lookup"><span data-stu-id="04b94-312">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="04b94-313">In tal caso, può essere utile creare dipendenze tra le voci della cache, utilizzando un CancellationChangeToken.</span><span class="sxs-lookup"><span data-stu-id="04b94-313">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="04b94-314">Con un CancellationChangeToken, è possibile far scadere più voci nella cache in una sola volta per il token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="04b94-314">With a CancellationChangeToken, you can expire multiple cache entries at once by cancelling the token.</span></span>

```csharp
// configure CancellationToken and add entry to cache
var cts = new CancellationTokenSource();
_cache.Set("cts", cts);
_cache.Set(cacheKey,
itemToCache,
new CancellationChangeToken(cts.Token));

// elsewhere, expire the cache by cancelling the token\
_cache.Get<CancellationTokenSource>("cts").Cancel();
```

>[!div class="step-by-step"]
<span data-ttu-id="04b94-315">[Precedente] [Avanti] (test-asp-net-core-mvc-apps.md) (develop-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="04b94-315">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span></span>
