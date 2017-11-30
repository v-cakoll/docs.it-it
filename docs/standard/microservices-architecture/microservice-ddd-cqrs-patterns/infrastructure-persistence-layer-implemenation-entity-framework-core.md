---
title: Implementa il livello di persistenza di infrastruttura con Entity Framework Core
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementa il livello di persistenza di infrastruttura con Entity Framework Core
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 508d60d73eb7c0f0cc2cc909613cc4f8712b4aba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="47766-104">Implementa il livello di persistenza di infrastruttura con Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="47766-104">Implementing the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="47766-105">Quando si utilizzano database relazionali, ad esempio SQL Server, Oracle o PostgreSQL, un approccio consigliato consiste nell'implementare il livello di persistenza basato su Entity Framework (EF).</span><span class="sxs-lookup"><span data-stu-id="47766-105">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="47766-106">EF supporta LINQ e fornisce oggetti fortemente tipizzati per il modello, nonché semplificata persistenza nel database.</span><span class="sxs-lookup"><span data-stu-id="47766-106">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="47766-107">Entity Framework ha una lunga storia come parte di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47766-107">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="47766-108">Quando si utilizza .NET Core, è necessario utilizzare anche Entity Framework Core, che viene eseguito in Windows o Linux in modo analogo .NET Core.</span><span class="sxs-lookup"><span data-stu-id="47766-108">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="47766-109">EF Core è una riscrittura completa di Entity Framework, implementato con un footprint molto più piccolo e importanti miglioramenti nelle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="47766-109">EF Core is a complete rewrite of Entity Framework, implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="47766-110">Introduzione a Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="47766-110">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="47766-111">Componenti di base di Entity Framework (EF) è un tipo semplice, estendibile e e tecnologia di accesso multipiattaforma versione dei dati di Entity Framework più diffusi.</span><span class="sxs-lookup"><span data-stu-id="47766-111">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="47766-112">È stata introdotta con .NET Core in mid 2016.</span><span class="sxs-lookup"><span data-stu-id="47766-112">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="47766-113">Poiché un'introduzione a Entity Framework Core è già disponibile nella documentazione di Microsoft, in questo caso è sufficiente fornire collegamenti alle informazioni.</span><span class="sxs-lookup"><span data-stu-id="47766-113">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="47766-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="47766-114">Additional resources</span></span>

-   <span data-ttu-id="47766-115">**Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span><span class="sxs-lookup"><span data-stu-id="47766-115">**Entity Framework Core**
[*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span></span>

-   <span data-ttu-id="47766-116">**Introduzione a Entity Framework Core con Visual Studio e di ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span><span class="sxs-lookup"><span data-stu-id="47766-116">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio**
[*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span></span>

-   <span data-ttu-id="47766-117">**Classe DbContext**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span><span class="sxs-lookup"><span data-stu-id="47766-117">**DbContext Class**
[*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span></span>

-   <span data-ttu-id="47766-118">**Confrontare Core EF & EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span><span class="sxs-lookup"><span data-stu-id="47766-118">**Compare EF Core & EF6.x**
[*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span></span>

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="47766-119">Infrastruttura di Entity Framework Core da una prospettiva DDD</span><span class="sxs-lookup"><span data-stu-id="47766-119">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="47766-120">Dal punto di vista DDD, un'importante funzionalità di Entity Framework è la possibilità di utilizzare l'entità di dominio POCO, nota anche nella terminologia EF come POCO *codice-first entità*.</span><span class="sxs-lookup"><span data-stu-id="47766-120">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="47766-121">Se si utilizzano le entità di dominio POCO, le classi di modello di dominio sono persistenza, seguendo il [mancato riconoscimento della persistenza](http://deviq.com/persistence-ignorance/) e [mancato riconoscimento di infrastruttura](https://ayende.com/blog/3137/infrastructure-ignorance) principi.</span><span class="sxs-lookup"><span data-stu-id="47766-121">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="47766-122">Per ogni pattern DDD, è consigliabile incapsulare il comportamento di dominio e le regole all'interno della classe di entità, in modo che è possibile controllare invarianti, le convalide e regole quando si accede a una raccolta.</span><span class="sxs-lookup"><span data-stu-id="47766-122">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="47766-123">È pertanto non buona norma in DDD per consentire l'accesso pubblico a raccolte di figlio entità o oggetti.</span><span class="sxs-lookup"><span data-stu-id="47766-123">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="47766-124">Al contrario, si desidera esporre metodi che consentono di controllare come e quando è possibile aggiornare i campi e raccolte di proprietà, e il comportamento e le azioni devono essere eseguiti quando ciò si verifica.</span><span class="sxs-lookup"><span data-stu-id="47766-124">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="47766-125">In Entity Framework Core 1.1, per soddisfare tali requisiti DDD è possibile avere campi normale nelle entità anziché le proprietà con Setter pubbliche e private.</span><span class="sxs-lookup"><span data-stu-id="47766-125">In EF Core 1.1, to satisfy those DDD requirements you can have plain fields in your entities instead of properties with public and private setters.</span></span> <span data-ttu-id="47766-126">Se non si desidera un campo dell'entità deve essere accessibile dall'esterno, è possibile creare solo l'attributo o un campo anziché una proprietà.</span><span class="sxs-lookup"><span data-stu-id="47766-126">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="47766-127">Non è necessario per utilizzare i metodi di impostazione private se si preferisce l'approccio più chiara.</span><span class="sxs-lookup"><span data-stu-id="47766-127">There is no need to use private setters if you prefer this cleaner approach.</span></span>

<span data-ttu-id="47766-128">In modo analogo, è ora possibile avere accesso in sola lettura a raccolte tramite una proprietà pubblica tipizzata come IEnumerable&lt;T&gt;, supportato da un membro di campo privato per la raccolta (ad esempio un elenco&lt;&gt;) nei entità che si basa su Entity Framework per la persistenza.</span><span class="sxs-lookup"><span data-stu-id="47766-128">In a similar way, you can now have read-only access to collections by using a public property typed as IEnumerable&lt;T&gt;, which is backed by a private field member for the collection (like a List&lt;&gt;) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="47766-129">Le versioni precedenti di Entity Framework richiedono proprietà di raccolta per supportare l'ICollection&lt;T&gt;, la conseguenza che gli sviluppatori utilizzando la classe di entità padre può aggiungere o rimuovere elementi dalle relative raccolte di proprietà.</span><span class="sxs-lookup"><span data-stu-id="47766-129">Previous versions of Entity Framework required collection properties to support ICollection&lt;T&gt;, which meant that any developer using the parent entity class could add or remove items from its property collections.</span></span> <span data-ttu-id="47766-130">Tale possibilità sarebbe con i criteri in DDD consigliati.</span><span class="sxs-lookup"><span data-stu-id="47766-130">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="47766-131">È possibile utilizzare una raccolta privata l'esposizione di un oggetto IEnumerable di sola lettura, come illustrato nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="47766-131">You can use a private collection while exposing a read-only IEnumerable object, as shown in the following code example:</span></span>

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...
    private readonly List<OrderItem> _orderItems;

    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        // Initializations ...
    }

    public void AddOrderItem(int productId, string productName,
        decimal unitPrice, decimal discount,
        string pictureUrl, int units = 1)
    {
        // Validation logic...
        var orderItem = new OrderItem(productId, productName, unitPrice, discount,
            pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

<span data-ttu-id="47766-132">Si noti che la proprietà OrderItems solo è possibile accedere in sola lettura tramite elenco&lt;&gt;. AsReadOnly().</span><span class="sxs-lookup"><span data-stu-id="47766-132">Note that the OrderItems property can only be accessed as read-only using List&lt;&gt;.AsReadOnly().</span></span> <span data-ttu-id="47766-133">Questo metodo crea un wrapper di sola lettura per l'elenco privato in modo che è protetta con aggiornamenti esterni.</span><span class="sxs-lookup"><span data-stu-id="47766-133">This method creates a read-only wrapper around the private list so that it is protected against external updates.</span></span> <span data-ttu-id="47766-134">È molto più economica rispetto all'utilizzo del metodo ToList, perché non è necessario copiare tutti gli elementi in una nuova raccolta. al contrario, esegue solo di un'operazione di allocazione di heap per l'istanza del wrapper.</span><span class="sxs-lookup"><span data-stu-id="47766-134">It is much cheaper than using the ToList method, because it does not have to copy all the items in a new collection; instead, it performs just one heap alloc operation for the wrapper instance.</span></span>

<span data-ttu-id="47766-135">Core di Entity Framework fornisce un modo per eseguire il mapping del modello di dominio per il database fisico senza che possono danneggiare il modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="47766-135">EF Core provides a way to map the domain model to the physical database without contaminating the domain model.</span></span> <span data-ttu-id="47766-136">È POCO .NET codice puro, perché l'operazione di mapping è implementata nel livello di persistenza.</span><span class="sxs-lookup"><span data-stu-id="47766-136">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="47766-137">In tale azione di mapping, è necessario configurare il mapping di campi nel database.</span><span class="sxs-lookup"><span data-stu-id="47766-137">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="47766-138">Nell'esempio seguente di un metodo OnModelCreating, il codice evidenziato indica EF Core per accedere alla proprietà OrderItems tramite il relativo campo.</span><span class="sxs-lookup"><span data-stu-id="47766-138">In the following example of an OnModelCreating method, the highlighted code tells EF Core to access the OrderItems property through its field.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    // ...
    modelBuilder.Entity<Order>(ConfigureOrder);
    // Other entities ...
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    // Other configuration ...
    var navigation = orderConfiguration.Metadata.
    FindNavigation(nameof(Order.OrderItems));
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);
    // Other configuration ...
}
```

<span data-ttu-id="47766-139">Quando si utilizzano campi anziché le proprietà, l'entità OrderItem viene mantenuto come se avesse un elenco&lt;OrderItem&gt; proprietà.</span><span class="sxs-lookup"><span data-stu-id="47766-139">When you use fields instead of properties, the OrderItem entity is persisted just as if it had a List&lt;OrderItem&gt; property.</span></span> <span data-ttu-id="47766-140">Tuttavia, espone una funzione di accesso singolo (il metodo AddOrderItem) per l'aggiunta di nuovi elementi all'ordine.</span><span class="sxs-lookup"><span data-stu-id="47766-140">However, it exposes a single accessor (the AddOrderItem method) for adding new items to the order.</span></span> <span data-ttu-id="47766-141">Di conseguenza, comportamento e i dati sono collegati tra loro e saranno coerenti in tutto il codice di applicazione che utilizza il modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="47766-141">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implementing-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="47766-142">Implementazione di repository personalizzati con Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="47766-142">Implementing custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="47766-143">A livello di implementazione, un repository è semplicemente una classe con codice di persistenza di dati coordinata da un'unità di lavoro (DBContext principali EF) durante l'esecuzione di aggiornamenti, come illustrato nella classe seguente:</span><span class="sxs-lookup"><span data-stu-id="47766-143">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

```csharp
// using statements...
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class BuyerRepository : IBuyerRepository
    {
        private readonly OrderingContext _context;

        public IUnitOfWork UnitOfWork
        {
            get
            {
                return _context;
            }
        }
    }

    public BuyerRepository(OrderingContext context)
    {
        if (context == null)
        {
            throw new ArgumentNullException(
                nameof(context));
        }
        _context = context;
    }

    public Buyer Add(Buyer buyer)
    {
        return _context.Buyers.Add(buyer).Entity;
    }

    public async Task<Buyer> FindAsync(string BuyerIdentityGuid)
    {
        var buyer = await _context.Buyers.Include(b => b.Payments)
            .Where(b => b.FullName == BuyerIdentityGuid)
            .SingleOrDefaultAsync();
        return buyer;
    }
}
```

<span data-ttu-id="47766-144">Si noti che l'interfaccia IBuyerRepository proviene dal livello del modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="47766-144">Note that the IBuyerRepository interface comes from the domain model layer.</span></span> <span data-ttu-id="47766-145">Tuttavia, l'implementazione di repository viene effettuata alla persistenza e livello infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="47766-145">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="47766-146">L'elemento DbContext EF viene fornito tramite il costruttore tramite l'inserimento di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="47766-146">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="47766-147">Viene condiviso tra più repository all'interno dello stesso ambito di richiesta HTTP, grazie alla sua durata predefinita (ServiceLifetime.Scoped) nel contenitore IoC (che può anche essere impostato esplicitamente con i servizi. AddDbContext&lt;&gt;).</span><span class="sxs-lookup"><span data-stu-id="47766-147">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (ServiceLifetime.Scoped) in the IoC container (which can also be explicitly set with services.AddDbContext&lt;&gt;).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="47766-148">Metodi da implementare in un repository (aggiornamenti o le transazioni e le query)</span><span class="sxs-lookup"><span data-stu-id="47766-148">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="47766-149">All'interno di ogni classe di repository, è necessario inserire i metodi di persistenza che aggiorna lo stato delle entità contenute dall'aggregazione relativo correlati.</span><span class="sxs-lookup"><span data-stu-id="47766-149">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="47766-150">Ricordare esiste una relazione tra una funzione di aggregazione e il relativo repository correlati.</span><span class="sxs-lookup"><span data-stu-id="47766-150">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="47766-151">Prendere in considerazione che un oggetto entità radice di aggregazione sono incorporati entità figlio all'interno del grafico di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="47766-151">Take into account that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="47766-152">Ad esempio, un acquirente potrebbe essere più metodi di pagamento come entità figlio correlati.</span><span class="sxs-lookup"><span data-stu-id="47766-152">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="47766-153">Poiché l'approccio per l'ordinamento microservizio in eShopOnContainers si basa inoltre su CQS/CQRS, la maggior parte delle query non sono implementata in repository personalizzati.</span><span class="sxs-lookup"><span data-stu-id="47766-153">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="47766-154">Gli sviluppatori hanno la possibilità di creare query e join che necessari per il livello di presentazione senza le restrizioni imposte dal repository personalizzati per ogni funzione di aggregazione e DDD, le aggregazioni in generale.</span><span class="sxs-lookup"><span data-stu-id="47766-154">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="47766-155">La maggior parte degli archivi di personalizzato suggeriti da questa guida sono numerosi i aggiornamento o i metodi transazionali, ma i metodi di query necessario ottenere dati da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="47766-155">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="47766-156">Ad esempio, il repository BuyerRepository implementa un metodo di FindAsync, perché l'applicazione deve sapere se un particolare acquirente sia esistente prima di creare un nuovo acquirente correlato all'ordine.</span><span class="sxs-lookup"><span data-stu-id="47766-156">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="47766-157">Tuttavia, i metodi di query effettivo per ottenere dati da inviare per le app client o del livello di presentazione vengono implementati, come indicato, nelle query CQRS basate su query flessibile tramite Dapper.</span><span class="sxs-lookup"><span data-stu-id="47766-157">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="47766-158">Utilizzo di un archivio personalizzato invece di EF DbContext direttamente</span><span class="sxs-lookup"><span data-stu-id="47766-158">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="47766-159">La classe DbContext di Entity Framework è in base agli schemi di unità di lavoro e del Repository e può essere utilizzata direttamente dal codice, ad esempio da un controller di ASP.NET MVC di base.</span><span class="sxs-lookup"><span data-stu-id="47766-159">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns, and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="47766-160">Vale a dire la modalità è possibile creare il codice più semplice, come il microservizio catalogo CRUD in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="47766-160">That is the way you can create the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="47766-161">In casi in cui si desidera che il codice più semplice possibile, si potrebbe desidera utilizzare direttamente la classe DbContext, come molti sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="47766-161">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="47766-162">Tuttavia, l'implementazione di repository personalizzati offre diversi vantaggi quando si implementa più complessi microservizi o applicazioni.</span><span class="sxs-lookup"><span data-stu-id="47766-162">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="47766-163">I modelli di unità di lavoro e del Repository sono utili per incapsulare il livello di persistenza di infrastruttura in modo che non è associato l'applicazione e i livelli del modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="47766-163">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain model layers.</span></span> <span data-ttu-id="47766-164">Implementazione di questi modelli possono facilitare l'uso dei repository fittizio simulando l'accesso al database.</span><span class="sxs-lookup"><span data-stu-id="47766-164">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="47766-165">Nella figura 9-18. è possibile visualizzare le differenze tra l'utilizzo non repository (direttamente tramite l'elemento DbContext EF) invece di repository che rendono più semplice simulare i repository.</span><span class="sxs-lookup"><span data-stu-id="47766-165">In Figure 9-18 you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories which make it easier to mock those repositories.</span></span>

![](./media/image19.png)

<span data-ttu-id="47766-166">**Figura 9-18**.</span><span class="sxs-lookup"><span data-stu-id="47766-166">**Figure 9-18**.</span></span> <span data-ttu-id="47766-167">Utilizzo di repository personalizzati e un semplice DbContext</span><span class="sxs-lookup"><span data-stu-id="47766-167">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="47766-168">Quando tali, sono disponibili più alternative.</span><span class="sxs-lookup"><span data-stu-id="47766-168">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="47766-169">È possibile simulare repository sufficiente o è Impossibile simulare un'intera unità di lavoro.</span><span class="sxs-lookup"><span data-stu-id="47766-169">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="47766-170">In genere solo il repository è sufficiente e la complessità astratta e simulare un'intera unità di lavoro in genere non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="47766-170">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="47766-171">In un secondo momento, quando è lo stato attivo sul livello dell'applicazione, verrà visualizzato il funzionamento di Dependency Injection in ASP.NET Core e come viene implementato quando si utilizza repository.</span><span class="sxs-lookup"><span data-stu-id="47766-171">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="47766-172">In breve, repository personalizzati consentono di testare il codice più facilmente con gli unit test che non sono interessati dallo stato del livello dati.</span><span class="sxs-lookup"><span data-stu-id="47766-172">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="47766-173">Se si eseguono test che anche accesso al database effettivo tramite Entity Framework, non sono unit test, ma i test di integrazione, sono molto più lenti.</span><span class="sxs-lookup"><span data-stu-id="47766-173">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="47766-174">Se si utilizza direttamente DbContext, l'unica scelta che è possibile eseguire unit test con un Server SQL in memoria dei dati prevedibile per gli unit test.</span><span class="sxs-lookup"><span data-stu-id="47766-174">If you were using DbContext directly, the only choice you would have would be to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="47766-175">Non sarà in grado di controllare gli oggetti fittizi e dati falsi nello stesso modo a livello di repository.</span><span class="sxs-lookup"><span data-stu-id="47766-175">You would not be able to control mock objects and fake data in the same way at the repository level.</span></span> <span data-ttu-id="47766-176">Naturalmente, è sempre possibile verificare i controller MVC.</span><span class="sxs-lookup"><span data-stu-id="47766-176">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="47766-177">Durata dell'istanza DbContext EF e IUnitOfWork nel contenitore di inversione di controllo</span><span class="sxs-lookup"><span data-stu-id="47766-177">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="47766-178">L'oggetto DbContext (esposto come un oggetto IUnitOfWork) potrebbe essere necessario per la condivisione tra più repository all'interno dello stesso ambito della richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="47766-178">The DbContext object (exposed as an IUnitOfWork object) might need to be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="47766-179">Ad esempio, ciò si verifica quando è necessario gestire l'operazione in esecuzione con più funzioni di aggregazione o semplicemente perché si siano utilizzando più istanze di repository.</span><span class="sxs-lookup"><span data-stu-id="47766-179">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="47766-180">È inoltre importante ricordare che l'interfaccia IUnitOfWork fa parte del dominio, non è un tipo di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="47766-180">It is also important to mention that the IUnitOfWork interface is part of the domain, not an EF type.</span></span>

<span data-ttu-id="47766-181">A tale scopo, l'istanza dell'oggetto DbContext deve impostare la durata del servizio per ServiceLifetime.Scoped.</span><span class="sxs-lookup"><span data-stu-id="47766-181">In order to do that, the instance of the DbContext object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="47766-182">Questa è la durata predefinita quando si registra un elemento DbContext con servizi. AddDbContext nel contenitore IoC dal metodo ConfigureServices del file nel progetto API Web di ASP.NET Core Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="47766-182">This is the default lifetime when registering a DbContext with services.AddDbContext in your IoC container from the ConfigureServices method of the Startup.cs file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="47766-183">Questa condizione è illustrata nel codice che segue.</span><span class="sxs-lookup"><span data-stu-id="47766-183">The following code illustrates this.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddMvc(options =>
    {
        options.Filters.Add(typeof(HttpGlobalExceptionFilter));
    }).AddControllersAsServices();

    services.AddEntityFrameworkSqlServer()
    .AddDbContext<OrderingContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlop => sqlop.MigrationsAssembly(typeof(Startup).GetTypeInfo().
        Assembly.GetName().Name));
    },
    ServiceLifetime.Scoped // Note that Scoped is the default choice
    // in AddDbContext. It is shown here only for
    // pedagogic purposes.
    );
}
```

<span data-ttu-id="47766-184">La modalità di creazione di un'istanza di DbContext non deve essere configurata come ServiceLifetime.Transient o ServiceLifetime.Singleton.</span><span class="sxs-lookup"><span data-stu-id="47766-184">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="47766-185">La durata dell'istanza del repository nel contenitore di inversione di controllo</span><span class="sxs-lookup"><span data-stu-id="47766-185">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="47766-186">In modo analogo, la durata del repository in genere deve essere impostata come ambito (InstancePerLifetimeScope in Autofac).</span><span class="sxs-lookup"><span data-stu-id="47766-186">In a similar way, repository’s lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="47766-187">La causa potrebbe essere temporaneo (InstancePerDependency in Autofac), ma il servizio sarà più efficiente in quanto riguarda la memoria quando si utilizza la durata con ambita.</span><span class="sxs-lookup"><span data-stu-id="47766-187">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="47766-188">Si noti che potrebbe causare è concorrenza gravi problemi quando l'elemento DbContext è impostata su utilizzando la durata singleton per il repository con ambito di durata (InstancePerLifetimeScope) (le durate predefinite per un elemento DBContext).</span><span class="sxs-lookup"><span data-stu-id="47766-188">Note that using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="47766-189">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="47766-189">Additional resources</span></span>

-   <span data-ttu-id="47766-190">**Implementare il Repository e l'unità di lavoro modelli in un'applicazione MVC ASP.NET**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-repository-and-unit-of-Work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="47766-190">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

-   <span data-ttu-id="47766-191">**Allen Lorenzo. Strategie di implementazione per il Repository con Entity Framework, Dapper, di schema e concatenare**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span><span class="sxs-lookup"><span data-stu-id="47766-191">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain**
[*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span></span>

-   <span data-ttu-id="47766-192">**Cesar de la Torre. Confronto tra la durata di servizio contenitore di ASP.NET Core IoC con ambiti di istanza contenitore IoC Autofac**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-core-IoC-Service-Life-Times-and-autofac-IoC-Instance-Scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="47766-192">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="table-mapping"></a><span data-ttu-id="47766-193">Mapping di tabella</span><span class="sxs-lookup"><span data-stu-id="47766-193">Table mapping</span></span>

<span data-ttu-id="47766-194">Mapping della tabella identifica i dati della tabella per effettuare una query e salvato nel database.</span><span class="sxs-lookup"><span data-stu-id="47766-194">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="47766-195">In precedenza si è visto come entità di dominio (ad esempio, un dominio di prodotto o l'ordine) utilizzabile per generare uno schema di database correlati.</span><span class="sxs-lookup"><span data-stu-id="47766-195">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="47766-196">Entity Framework è progettato fortemente sul concetto di *convenzioni*.</span><span class="sxs-lookup"><span data-stu-id="47766-196">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="47766-197">Domande di indirizzo convenzioni quali "Quali il nome di una tabella sarà?"</span><span class="sxs-lookup"><span data-stu-id="47766-197">Conventions address questions like “What will the name of a table be?”</span></span> <span data-ttu-id="47766-198">oppure "la proprietà è la chiave primaria?"</span><span class="sxs-lookup"><span data-stu-id="47766-198">or “What property is the primary key?”</span></span> <span data-ttu-id="47766-199">Convenzioni sono solitamente basate sui nomi tradizionali, ad esempio, è tipico per la chiave primaria sia una proprietà che termina con l'ID.</span><span class="sxs-lookup"><span data-stu-id="47766-199">Conventions are typically based on conventional names—for example, it is typical for the primary key to be a property that ends with Id.</span></span>

<span data-ttu-id="47766-200">Per convenzione, ogni entità verranno configurata per eseguire il mapping a una tabella con lo stesso nome di DbSet&lt;TEntity&gt; proprietà che espone l'entità al contesto derivata.</span><span class="sxs-lookup"><span data-stu-id="47766-200">By convention, each entity will be set up to map to a table with the same name as the DbSet&lt;TEntity&gt; property that exposes the entity on the derived context.</span></span> <span data-ttu-id="47766-201">Se nessun DbSet&lt;TEntity&gt; valore viene fornito per l'entità specificata, viene utilizzato il nome della classe.</span><span class="sxs-lookup"><span data-stu-id="47766-201">If no DbSet&lt;TEntity&gt; value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="47766-202">Annotazioni dei dati e l'API Fluent</span><span class="sxs-lookup"><span data-stu-id="47766-202">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="47766-203">Esistono numerose convenzioni EF Core aggiuntive e la maggior parte di essi può essere modificata tramite API Fluent, implementato nel metodo OnModelCreating o le annotazioni dei dati.</span><span class="sxs-lookup"><span data-stu-id="47766-203">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="47766-204">Le annotazioni dei dati devono essere utilizzate sulle classi del modello di entità, che è un modo più intrusivo dal punto di vista DDD.</span><span class="sxs-lookup"><span data-stu-id="47766-204">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="47766-205">In questo modo vengono che possono danneggiare il modello con le annotazioni dei dati correlate al database di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="47766-205">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="47766-206">D'altra parte, Microsoft Office Fluent API è un modo pratico per modificare la maggior parte delle convenzioni e il mapping all'interno del livello di infrastruttura di persistenza dei dati, in modo che il modello di entità sia pulito e separata dall'infrastruttura di persistenza.</span><span class="sxs-lookup"><span data-stu-id="47766-206">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="47766-207">API intuitiva e il metodo OnModelCreating</span><span class="sxs-lookup"><span data-stu-id="47766-207">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="47766-208">Come accennato, per modificare le convenzioni e i mapping, è possibile utilizzare il metodo OnModelCreating nella classe DbContext.</span><span class="sxs-lookup"><span data-stu-id="47766-208">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span> <span data-ttu-id="47766-209">Nell'esempio seguente viene descritto come eseguire tale nell'ordinamento microservizio in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="47766-209">The following example shows how we do this in the ordering microservice in eShopOnContainers.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    //Other entities
    modelBuilder.Entity<OrderStatus>(ConfigureOrderStatus);
    //Other entities
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Property(o => o.Id).ForSqlServerUseSequenceHiLo("orderseq", DEFAULT_SCHEMA);
    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
    orderConfiguration.Property<string>("Street").IsRequired();
    orderConfiguration.Property<string>("State").IsRequired();
    orderConfiguration.Property<string>("City").IsRequired();
    orderConfiguration.Property<string>("ZipCode").IsRequired();
    orderConfiguration.Property<string>("Country").IsRequired();
    orderConfiguration.Property<int>("BuyerId").IsRequired();
    orderConfiguration.Property<int>("OrderStatusId").IsRequired();
    orderConfiguration.Property<int>("PaymentMethodId").IsRequired();

    var navigation =
    orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));
    // DDD Patterns comment:
    // Set as Field (new since EF 1.1) to access
    // the OrderItem collection property as a field
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

    orderConfiguration.HasOne(o => o.PaymentMethod)
        .WithMany()
        .HasForeignKey("PaymentMethodId")
        .OnDelete(DeleteBehavior.Restrict);
        orderConfiguration.HasOne(o => o.Buyer)
        .WithMany()
        .HasForeignKey("BuyerId");
        orderConfiguration.HasOne(o => o.OrderStatus)
        .WithMany()
        .HasForeignKey("OrderStatusId");
}
```

<span data-ttu-id="47766-210">È possibile impostare tutti i mapping di Microsoft Office Fluent API all'interno del metodo OnModelCreating stesso, ma è consigliabile eseguire la partizione che il codice e avere più submethods, uno per ogni entità, come illustrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="47766-210">You could set all the Fluent API mappings within the same OnModelCreating method, but it is advisable to partition that code and have multiple submethods, one per entity, as shown in the example.</span></span> <span data-ttu-id="47766-211">Per i modelli di dimensioni particolarmente grandi, può anche essere consigliabile disporre di file di origine distinti (le classi statiche) per la configurazione dei tipi di entità diversi.</span><span class="sxs-lookup"><span data-stu-id="47766-211">For particularly large models, it can even be advisable to have separate source files (static classes) for configuring different entity types.</span></span>

<span data-ttu-id="47766-212">Nell'esempio di codice è esplicito.</span><span class="sxs-lookup"><span data-stu-id="47766-212">The code in the example is explicit.</span></span> <span data-ttu-id="47766-213">Convenzioni Entity Framework Core, tuttavia, eseguire la maggior parte di questo automaticamente, pertanto il codice effettivo, che è necessario scrivere ottenere lo stesso risultato sarebbe molto più piccolo.</span><span class="sxs-lookup"><span data-stu-id="47766-213">However, EF Core conventions do most of this automatically, so the actual code you would need to write to achieve the same thing would be much smaller.</span></span>

### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="47766-214">L'algoritmo di Hi/Giussani in EF Core</span><span class="sxs-lookup"><span data-stu-id="47766-214">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="47766-215">Un aspetto interessante di codice nell'esempio precedente è che utilizza il [Hi/Giussani algoritmo](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) come strategia di generazione delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="47766-215">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="47766-216">L'algoritmo di Hi/Giussani è utile quando è necessario chiavi univoche.</span><span class="sxs-lookup"><span data-stu-id="47766-216">The Hi/Lo algorithm is useful when you need unique keys.</span></span> <span data-ttu-id="47766-217">Come un riepilogo, l'algoritmo Hi-Lo assegna identificatori univoci per le righe della tabella mentre non a seconda della memorizzazione immediatamente la riga nel database.</span><span class="sxs-lookup"><span data-stu-id="47766-217">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="47766-218">Ciò consente di iniziare a utilizzare gli identificatori immediatamente, come accade con ID di database sequenziale normale.</span><span class="sxs-lookup"><span data-stu-id="47766-218">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="47766-219">L'algoritmo di Hi/Giussani descrive un meccanismo per la generazione di sicuro ID sul lato client, anziché nel database.</span><span class="sxs-lookup"><span data-stu-id="47766-219">The Hi/Lo algorithm describes a mechanism for generating safe IDs on the client side rather than in the database.</span></span> <span data-ttu-id="47766-220">*Sicuro* in questo contesto indica senza conflitti.</span><span class="sxs-lookup"><span data-stu-id="47766-220">*Safe* in this context means without collisions.</span></span> <span data-ttu-id="47766-221">Questo algoritmo è interessante per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="47766-221">This algorithm is interesting for these reasons:</span></span>

-   <span data-ttu-id="47766-222">Questo gestore non interrompe il modello di unità di lavoro.</span><span class="sxs-lookup"><span data-stu-id="47766-222">It does not break the Unit of Work pattern.</span></span>

-   <span data-ttu-id="47766-223">Non richiede round trip dei generatori di sequenza modo eseguire in altro DBMS.</span><span class="sxs-lookup"><span data-stu-id="47766-223">It does not require round trips the way sequence generators do in other DBMSs.</span></span>

-   <span data-ttu-id="47766-224">Genera un identificatore leggibile, a differenza delle tecniche che utilizzano GUID.</span><span class="sxs-lookup"><span data-stu-id="47766-224">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="47766-225">Core EF supporta [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) con il metodo ForSqlServerUseSequenceHiLo, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="47766-225">EF Core supports [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the ForSqlServerUseSequenceHiLo method, as shown in the preceding example.</span></span>

### <a name="mapping-fields-instead-of-properties"></a><span data-ttu-id="47766-226">Mapping dei campi anziché le proprietà</span><span class="sxs-lookup"><span data-stu-id="47766-226">Mapping fields instead of properties</span></span>

<span data-ttu-id="47766-227">Con la funzionalità di Entity Framework Core 1.1 che esegue il mapping di colonne a campi, è possibile per non utilizzare le proprietà nella classe di entità e solo per eseguire il mapping di colonne di una tabella ai campi.</span><span class="sxs-lookup"><span data-stu-id="47766-227">With the feature of EF Core 1.1 that maps columns to fields, it is possible to not use any properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="47766-228">Un utilizzo comune per cui sarebbe campi privati per uno stato interno che non devono essere accessibili all'esterno dell'entità.</span><span class="sxs-lookup"><span data-stu-id="47766-228">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="47766-229">Entity Framework 1.1 supporta un modo per eseguire il mapping di un campo senza una proprietà correlata a una colonna nel database.</span><span class="sxs-lookup"><span data-stu-id="47766-229">EF 1.1 supports a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="47766-230">È possibile farlo con singoli campi o anche con le raccolte, ad esempio un elenco&lt; &gt; campo.</span><span class="sxs-lookup"><span data-stu-id="47766-230">You can do this with single fields or also with collections, like a List&lt;&gt; field.</span></span> <span data-ttu-id="47766-231">Questo punto è stato indicato in precedenza, quando abbiamo parlato modellazione classi del modello di dominio, ma è possibile visualizzare come tale mapping viene eseguita con la configurazione di PropertyAccessMode.Field evidenziata nel codice precedente.</span><span class="sxs-lookup"><span data-stu-id="47766-231">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the PropertyAccessMode.Field configuration highlighted in the previous code.</span></span>

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a><span data-ttu-id="47766-232">Utilizzando le proprietà di ombreggiatura negli oggetti valore di ID nascosto a livello di infrastruttura</span><span class="sxs-lookup"><span data-stu-id="47766-232">Using shadow properties in value objects for hidden IDs at the infrastructure level</span></span>

<span data-ttu-id="47766-233">Nascondere le proprietà principali di Entity Framework sono di proprietà che non esistono nel modello di classe di entità.</span><span class="sxs-lookup"><span data-stu-id="47766-233">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="47766-234">I valori e stati di queste proprietà vengono mantenuti in esclusivamente il [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) classe a livello di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="47766-234">The values and states of these properties are maintained purely in the [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>

<span data-ttu-id="47766-235">Dal punto di vista DDD, nascondere le proprietà sono un modo pratico per implementare gli oggetti valore nascondendo l'ID come chiave primaria proprietà shadow.</span><span class="sxs-lookup"><span data-stu-id="47766-235">From a DDD point of view, shadow properties are a convenient way to implement value objects by hiding the ID as a shadow property primary key.</span></span> <span data-ttu-id="47766-236">Questo è importante, perché un oggetto di valore non deve avere identità (almeno, non è necessario l'ID nel livello del modello di dominio quando gli oggetti valore di data shaping).</span><span class="sxs-lookup"><span data-stu-id="47766-236">This is important, because a value object should not have identity (at least, you should not have the ID in the domain model layer when shaping value objects).</span></span> <span data-ttu-id="47766-237">Il punto è che a partire dalla versione corrente di Entity Framework Core, EF Core non dispone di una soluzione per implementare gli oggetti di valore come [tipi complessi](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), come è possibile in Entity Framework 6. x.</span><span class="sxs-lookup"><span data-stu-id="47766-237">The point here is that as of the current version of EF Core, EF Core does not have a way to implement value objects as [complex types](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), as is possible in EF 6.x.</span></span> <span data-ttu-id="47766-238">Che è attualmente necessario implementare un oggetto di valore come un set di entità con un ID nascosto (chiave primaria) come proprietà shadow.</span><span class="sxs-lookup"><span data-stu-id="47766-238">That is why you currently need to implement a value object as an entity with a hidden ID (primary key) set as a shadow property.</span></span>

<span data-ttu-id="47766-239">Come si può notare nel [oggetto valore indirizzo](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, nel modello di indirizzo non è presente un ID:</span><span class="sxs-lookup"><span data-stu-id="47766-239">As you can see in the [Address value object](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, in the Address model you do not see an ID:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }
    //Constructor initializing, etc
}
```

<span data-ttu-id="47766-240">Ma dietro le quinte, è necessario fornire un ID in modo che sia in grado di rendere persistenti i dati nelle tabelle del database principale di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="47766-240">But under the covers, we need to provide an ID so that EF Core is able to persist this data in the database tables.</span></span> <span data-ttu-id="47766-241">Facciamo nel metodo ConfigureAddress il [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) classe a livello di infrastruttura, in modo non è eseguire il modello di dominio con il codice dell'infrastruttura di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="47766-241">We do that in the ConfigureAddress method of the [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) class at the infrastructure level, so we do not pollute the domain model with EF infrastructure code.</span></span>

```csharp
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    // DDD pattern comment:
    // Implementing the Address ID as a shadow property, because the
    // address is a value object and an identity is not required for a
    // value object
    // EF Core just needs the ID so it can store it in a database table
    // See: https://docs.microsoft.com/ef/core/modeling/shadow-properties
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

#### <a name="additional-resources"></a><span data-ttu-id="47766-242">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="47766-242">Additional resources</span></span>

-   <span data-ttu-id="47766-243">**Tabella Mapping**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span><span class="sxs-lookup"><span data-stu-id="47766-243">**Table Mapping**
[*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span></span>

-   <span data-ttu-id="47766-244">**Consente di generare le chiavi di Entity Framework Core HiLo**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span><span class="sxs-lookup"><span data-stu-id="47766-244">**Use HiLo to generate keys with Entity Framework Core**
[*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span></span>

-   <span data-ttu-id="47766-245">**Il backup di campi**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span><span class="sxs-lookup"><span data-stu-id="47766-245">**Backing Fields**
[*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span></span>

-   <span data-ttu-id="47766-246">**Steve Smith. Le raccolte in Entity Framework Core incapsulato**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span><span class="sxs-lookup"><span data-stu-id="47766-246">**Steve Smith. Encapsulated Collections in Entity Framework Core**
[*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span></span>

-   <span data-ttu-id="47766-247">**Nascondere le proprietà**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="47766-247">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="47766-248">[Precedente] (infrastruttura-persistenza-layer-design.md) [Avanti] (nosql-database-persistenza-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="47766-248">[Previous] (infrastructure-persistence-layer-design.md) [Next] (nosql-database-persistence-infrastructure.md)</span></span>
