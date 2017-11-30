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
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a>Implementa il livello di persistenza di infrastruttura con Entity Framework Core

Quando si utilizzano database relazionali, ad esempio SQL Server, Oracle o PostgreSQL, un approccio consigliato consiste nell'implementare il livello di persistenza basato su Entity Framework (EF). EF supporta LINQ e fornisce oggetti fortemente tipizzati per il modello, nonché semplificata persistenza nel database.

Entity Framework ha una lunga storia come parte di .NET Framework. Quando si utilizza .NET Core, è necessario utilizzare anche Entity Framework Core, che viene eseguito in Windows o Linux in modo analogo .NET Core. EF Core è una riscrittura completa di Entity Framework, implementato con un footprint molto più piccolo e importanti miglioramenti nelle prestazioni.

## <a name="introduction-to-entity-framework-core"></a>Introduzione a Entity Framework Core

Componenti di base di Entity Framework (EF) è un tipo semplice, estendibile e e tecnologia di accesso multipiattaforma versione dei dati di Entity Framework più diffusi. È stata introdotta con .NET Core in mid 2016.

Poiché un'introduzione a Entity Framework Core è già disponibile nella documentazione di Microsoft, in questo caso è sufficiente fornire collegamenti alle informazioni.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)

-   **Introduzione a Entity Framework Core con Visual Studio e di ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)

-   **Classe DbContext**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)

-   **Confrontare Core EF & EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a>Infrastruttura di Entity Framework Core da una prospettiva DDD

Dal punto di vista DDD, un'importante funzionalità di Entity Framework è la possibilità di utilizzare l'entità di dominio POCO, nota anche nella terminologia EF come POCO *codice-first entità*. Se si utilizzano le entità di dominio POCO, le classi di modello di dominio sono persistenza, seguendo il [mancato riconoscimento della persistenza](http://deviq.com/persistence-ignorance/) e [mancato riconoscimento di infrastruttura](https://ayende.com/blog/3137/infrastructure-ignorance) principi.

Per ogni pattern DDD, è consigliabile incapsulare il comportamento di dominio e le regole all'interno della classe di entità, in modo che è possibile controllare invarianti, le convalide e regole quando si accede a una raccolta. È pertanto non buona norma in DDD per consentire l'accesso pubblico a raccolte di figlio entità o oggetti. Al contrario, si desidera esporre metodi che consentono di controllare come e quando è possibile aggiornare i campi e raccolte di proprietà, e il comportamento e le azioni devono essere eseguiti quando ciò si verifica.

In Entity Framework Core 1.1, per soddisfare tali requisiti DDD è possibile avere campi normale nelle entità anziché le proprietà con Setter pubbliche e private. Se non si desidera un campo dell'entità deve essere accessibile dall'esterno, è possibile creare solo l'attributo o un campo anziché una proprietà. Non è necessario per utilizzare i metodi di impostazione private se si preferisce l'approccio più chiara.

In modo analogo, è ora possibile avere accesso in sola lettura a raccolte tramite una proprietà pubblica tipizzata come IEnumerable&lt;T&gt;, supportato da un membro di campo privato per la raccolta (ad esempio un elenco&lt;&gt;) nei entità che si basa su Entity Framework per la persistenza. Le versioni precedenti di Entity Framework richiedono proprietà di raccolta per supportare l'ICollection&lt;T&gt;, la conseguenza che gli sviluppatori utilizzando la classe di entità padre può aggiungere o rimuovere elementi dalle relative raccolte di proprietà. Tale possibilità sarebbe con i criteri in DDD consigliati.

È possibile utilizzare una raccolta privata l'esposizione di un oggetto IEnumerable di sola lettura, come illustrato nell'esempio di codice seguente:

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

Si noti che la proprietà OrderItems solo è possibile accedere in sola lettura tramite elenco&lt;&gt;. AsReadOnly(). Questo metodo crea un wrapper di sola lettura per l'elenco privato in modo che è protetta con aggiornamenti esterni. È molto più economica rispetto all'utilizzo del metodo ToList, perché non è necessario copiare tutti gli elementi in una nuova raccolta. al contrario, esegue solo di un'operazione di allocazione di heap per l'istanza del wrapper.

Core di Entity Framework fornisce un modo per eseguire il mapping del modello di dominio per il database fisico senza che possono danneggiare il modello di dominio. È POCO .NET codice puro, perché l'operazione di mapping è implementata nel livello di persistenza. In tale azione di mapping, è necessario configurare il mapping di campi nel database. Nell'esempio seguente di un metodo OnModelCreating, il codice evidenziato indica EF Core per accedere alla proprietà OrderItems tramite il relativo campo.

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

Quando si utilizzano campi anziché le proprietà, l'entità OrderItem viene mantenuto come se avesse un elenco&lt;OrderItem&gt; proprietà. Tuttavia, espone una funzione di accesso singolo (il metodo AddOrderItem) per l'aggiunta di nuovi elementi all'ordine. Di conseguenza, comportamento e i dati sono collegati tra loro e saranno coerenti in tutto il codice di applicazione che utilizza il modello di dominio.

## <a name="implementing-custom-repositories-with-entity-framework-core"></a>Implementazione di repository personalizzati con Entity Framework Core

A livello di implementazione, un repository è semplicemente una classe con codice di persistenza di dati coordinata da un'unità di lavoro (DBContext principali EF) durante l'esecuzione di aggiornamenti, come illustrato nella classe seguente:

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

Si noti che l'interfaccia IBuyerRepository proviene dal livello del modello di dominio. Tuttavia, l'implementazione di repository viene effettuata alla persistenza e livello infrastruttura.

L'elemento DbContext EF viene fornito tramite il costruttore tramite l'inserimento di dipendenze. Viene condiviso tra più repository all'interno dello stesso ambito di richiesta HTTP, grazie alla sua durata predefinita (ServiceLifetime.Scoped) nel contenitore IoC (che può anche essere impostato esplicitamente con i servizi. AddDbContext&lt;&gt;).

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a>Metodi da implementare in un repository (aggiornamenti o le transazioni e le query)

All'interno di ogni classe di repository, è necessario inserire i metodi di persistenza che aggiorna lo stato delle entità contenute dall'aggregazione relativo correlati. Ricordare esiste una relazione tra una funzione di aggregazione e il relativo repository correlati. Prendere in considerazione che un oggetto entità radice di aggregazione sono incorporati entità figlio all'interno del grafico di Entity Framework. Ad esempio, un acquirente potrebbe essere più metodi di pagamento come entità figlio correlati.

Poiché l'approccio per l'ordinamento microservizio in eShopOnContainers si basa inoltre su CQS/CQRS, la maggior parte delle query non sono implementata in repository personalizzati. Gli sviluppatori hanno la possibilità di creare query e join che necessari per il livello di presentazione senza le restrizioni imposte dal repository personalizzati per ogni funzione di aggregazione e DDD, le aggregazioni in generale. La maggior parte degli archivi di personalizzato suggeriti da questa guida sono numerosi i aggiornamento o i metodi transazionali, ma i metodi di query necessario ottenere dati da aggiornare. Ad esempio, il repository BuyerRepository implementa un metodo di FindAsync, perché l'applicazione deve sapere se un particolare acquirente sia esistente prima di creare un nuovo acquirente correlato all'ordine.

Tuttavia, i metodi di query effettivo per ottenere dati da inviare per le app client o del livello di presentazione vengono implementati, come indicato, nelle query CQRS basate su query flessibile tramite Dapper.

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a>Utilizzo di un archivio personalizzato invece di EF DbContext direttamente

La classe DbContext di Entity Framework è in base agli schemi di unità di lavoro e del Repository e può essere utilizzata direttamente dal codice, ad esempio da un controller di ASP.NET MVC di base. Vale a dire la modalità è possibile creare il codice più semplice, come il microservizio catalogo CRUD in eShopOnContainers. In casi in cui si desidera che il codice più semplice possibile, si potrebbe desidera utilizzare direttamente la classe DbContext, come molti sviluppatori.

Tuttavia, l'implementazione di repository personalizzati offre diversi vantaggi quando si implementa più complessi microservizi o applicazioni. I modelli di unità di lavoro e del Repository sono utili per incapsulare il livello di persistenza di infrastruttura in modo che non è associato l'applicazione e i livelli del modello di dominio. Implementazione di questi modelli possono facilitare l'uso dei repository fittizio simulando l'accesso al database.

Nella figura 9-18. è possibile visualizzare le differenze tra l'utilizzo non repository (direttamente tramite l'elemento DbContext EF) invece di repository che rendono più semplice simulare i repository.

![](./media/image19.png)

**Figura 9-18**. Utilizzo di repository personalizzati e un semplice DbContext

Quando tali, sono disponibili più alternative. È possibile simulare repository sufficiente o è Impossibile simulare un'intera unità di lavoro. In genere solo il repository è sufficiente e la complessità astratta e simulare un'intera unità di lavoro in genere non è necessaria.

In un secondo momento, quando è lo stato attivo sul livello dell'applicazione, verrà visualizzato il funzionamento di Dependency Injection in ASP.NET Core e come viene implementato quando si utilizza repository.

In breve, repository personalizzati consentono di testare il codice più facilmente con gli unit test che non sono interessati dallo stato del livello dati. Se si eseguono test che anche accesso al database effettivo tramite Entity Framework, non sono unit test, ma i test di integrazione, sono molto più lenti.

Se si utilizza direttamente DbContext, l'unica scelta che è possibile eseguire unit test con un Server SQL in memoria dei dati prevedibile per gli unit test. Non sarà in grado di controllare gli oggetti fittizi e dati falsi nello stesso modo a livello di repository. Naturalmente, è sempre possibile verificare i controller MVC.

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a>Durata dell'istanza DbContext EF e IUnitOfWork nel contenitore di inversione di controllo

L'oggetto DbContext (esposto come un oggetto IUnitOfWork) potrebbe essere necessario per la condivisione tra più repository all'interno dello stesso ambito della richiesta HTTP. Ad esempio, ciò si verifica quando è necessario gestire l'operazione in esecuzione con più funzioni di aggregazione o semplicemente perché si siano utilizzando più istanze di repository. È inoltre importante ricordare che l'interfaccia IUnitOfWork fa parte del dominio, non è un tipo di Entity Framework.

A tale scopo, l'istanza dell'oggetto DbContext deve impostare la durata del servizio per ServiceLifetime.Scoped. Questa è la durata predefinita quando si registra un elemento DbContext con servizi. AddDbContext nel contenitore IoC dal metodo ConfigureServices del file nel progetto API Web di ASP.NET Core Startup.cs. Questa condizione è illustrata nel codice che segue.

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

La modalità di creazione di un'istanza di DbContext non deve essere configurata come ServiceLifetime.Transient o ServiceLifetime.Singleton.

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a>La durata dell'istanza del repository nel contenitore di inversione di controllo

In modo analogo, la durata del repository in genere deve essere impostata come ambito (InstancePerLifetimeScope in Autofac). La causa potrebbe essere temporaneo (InstancePerDependency in Autofac), ma il servizio sarà più efficiente in quanto riguarda la memoria quando si utilizza la durata con ambita.

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

Si noti che potrebbe causare è concorrenza gravi problemi quando l'elemento DbContext è impostata su utilizzando la durata singleton per il repository con ambito di durata (InstancePerLifetimeScope) (le durate predefinite per un elemento DBContext).

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Implementare il Repository e l'unità di lavoro modelli in un'applicazione MVC ASP.NET**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-repository-and-unit-of-Work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)

-   **Allen Lorenzo. Strategie di implementazione per il Repository con Entity Framework, Dapper, di schema e concatenare**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)

-   **Cesar de la Torre. Confronto tra la durata di servizio contenitore di ASP.NET Core IoC con ambiti di istanza contenitore IoC Autofac**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-core-IoC-Service-Life-Times-and-autofac-IoC-Instance-Scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="table-mapping"></a>Mapping di tabella

Mapping della tabella identifica i dati della tabella per effettuare una query e salvato nel database. In precedenza si è visto come entità di dominio (ad esempio, un dominio di prodotto o l'ordine) utilizzabile per generare uno schema di database correlati. Entity Framework è progettato fortemente sul concetto di *convenzioni*. Domande di indirizzo convenzioni quali "Quali il nome di una tabella sarà?" oppure "la proprietà è la chiave primaria?" Convenzioni sono solitamente basate sui nomi tradizionali, ad esempio, è tipico per la chiave primaria sia una proprietà che termina con l'ID.

Per convenzione, ogni entità verranno configurata per eseguire il mapping a una tabella con lo stesso nome di DbSet&lt;TEntity&gt; proprietà che espone l'entità al contesto derivata. Se nessun DbSet&lt;TEntity&gt; valore viene fornito per l'entità specificata, viene utilizzato il nome della classe.

### <a name="data-annotations-versus-fluent-api"></a>Annotazioni dei dati e l'API Fluent

Esistono numerose convenzioni EF Core aggiuntive e la maggior parte di essi può essere modificata tramite API Fluent, implementato nel metodo OnModelCreating o le annotazioni dei dati.

Le annotazioni dei dati devono essere utilizzate sulle classi del modello di entità, che è un modo più intrusivo dal punto di vista DDD. In questo modo vengono che possono danneggiare il modello con le annotazioni dei dati correlate al database di infrastruttura. D'altra parte, Microsoft Office Fluent API è un modo pratico per modificare la maggior parte delle convenzioni e il mapping all'interno del livello di infrastruttura di persistenza dei dati, in modo che il modello di entità sia pulito e separata dall'infrastruttura di persistenza.

### <a name="fluent-api-and-the-onmodelcreating-method"></a>API intuitiva e il metodo OnModelCreating

Come accennato, per modificare le convenzioni e i mapping, è possibile utilizzare il metodo OnModelCreating nella classe DbContext. Nell'esempio seguente viene descritto come eseguire tale nell'ordinamento microservizio in eShopOnContainers.

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

È possibile impostare tutti i mapping di Microsoft Office Fluent API all'interno del metodo OnModelCreating stesso, ma è consigliabile eseguire la partizione che il codice e avere più submethods, uno per ogni entità, come illustrato nell'esempio. Per i modelli di dimensioni particolarmente grandi, può anche essere consigliabile disporre di file di origine distinti (le classi statiche) per la configurazione dei tipi di entità diversi.

Nell'esempio di codice è esplicito. Convenzioni Entity Framework Core, tuttavia, eseguire la maggior parte di questo automaticamente, pertanto il codice effettivo, che è necessario scrivere ottenere lo stesso risultato sarebbe molto più piccolo.

### <a name="the-hilo-algorithm-in-ef-core"></a>L'algoritmo di Hi/Giussani in EF Core

Un aspetto interessante di codice nell'esempio precedente è che utilizza il [Hi/Giussani algoritmo](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) come strategia di generazione delle chiavi.

L'algoritmo di Hi/Giussani è utile quando è necessario chiavi univoche. Come un riepilogo, l'algoritmo Hi-Lo assegna identificatori univoci per le righe della tabella mentre non a seconda della memorizzazione immediatamente la riga nel database. Ciò consente di iniziare a utilizzare gli identificatori immediatamente, come accade con ID di database sequenziale normale.

L'algoritmo di Hi/Giussani descrive un meccanismo per la generazione di sicuro ID sul lato client, anziché nel database. *Sicuro* in questo contesto indica senza conflitti. Questo algoritmo è interessante per i motivi seguenti:

-   Questo gestore non interrompe il modello di unità di lavoro.

-   Non richiede round trip dei generatori di sequenza modo eseguire in altro DBMS.

-   Genera un identificatore leggibile, a differenza delle tecniche che utilizzano GUID.

Core EF supporta [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) con il metodo ForSqlServerUseSequenceHiLo, come illustrato nell'esempio precedente.

### <a name="mapping-fields-instead-of-properties"></a>Mapping dei campi anziché le proprietà

Con la funzionalità di Entity Framework Core 1.1 che esegue il mapping di colonne a campi, è possibile per non utilizzare le proprietà nella classe di entità e solo per eseguire il mapping di colonne di una tabella ai campi. Un utilizzo comune per cui sarebbe campi privati per uno stato interno che non devono essere accessibili all'esterno dell'entità.

Entity Framework 1.1 supporta un modo per eseguire il mapping di un campo senza una proprietà correlata a una colonna nel database. È possibile farlo con singoli campi o anche con le raccolte, ad esempio un elenco&lt; &gt; campo. Questo punto è stato indicato in precedenza, quando abbiamo parlato modellazione classi del modello di dominio, ma è possibile visualizzare come tale mapping viene eseguita con la configurazione di PropertyAccessMode.Field evidenziata nel codice precedente.

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a>Utilizzando le proprietà di ombreggiatura negli oggetti valore di ID nascosto a livello di infrastruttura

Nascondere le proprietà principali di Entity Framework sono di proprietà che non esistono nel modello di classe di entità. I valori e stati di queste proprietà vengono mantenuti in esclusivamente il [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) classe a livello di infrastruttura.

Dal punto di vista DDD, nascondere le proprietà sono un modo pratico per implementare gli oggetti valore nascondendo l'ID come chiave primaria proprietà shadow. Questo è importante, perché un oggetto di valore non deve avere identità (almeno, non è necessario l'ID nel livello del modello di dominio quando gli oggetti valore di data shaping). Il punto è che a partire dalla versione corrente di Entity Framework Core, EF Core non dispone di una soluzione per implementare gli oggetti di valore come [tipi complessi](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), come è possibile in Entity Framework 6. x. Che è attualmente necessario implementare un oggetto di valore come un set di entità con un ID nascosto (chiave primaria) come proprietà shadow.

Come si può notare nel [oggetto valore indirizzo](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, nel modello di indirizzo non è presente un ID:

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

Ma dietro le quinte, è necessario fornire un ID in modo che sia in grado di rendere persistenti i dati nelle tabelle del database principale di Entity Framework. Facciamo nel metodo ConfigureAddress il [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) classe a livello di infrastruttura, in modo non è eseguire il modello di dominio con il codice dell'infrastruttura di Entity Framework.

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

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Tabella Mapping**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)

-   **Consente di generare le chiavi di Entity Framework Core HiLo**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)

-   **Il backup di campi**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)

-   **Steve Smith. Le raccolte in Entity Framework Core incapsulato**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)

-   **Nascondere le proprietà**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)


>[!div class="step-by-step"]
[Precedente] (infrastruttura-persistenza-layer-design.md) [Avanti] (nosql-database-persistenza-infrastructure.md)
