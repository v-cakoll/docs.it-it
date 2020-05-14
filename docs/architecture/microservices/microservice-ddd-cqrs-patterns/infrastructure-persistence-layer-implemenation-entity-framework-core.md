---
title: Implementazione del livello di persistenza dell'infrastruttura con Entity Framework Core
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Esplorare i dettagli di implementazione per il livello di persistenza dell'infrastruttura usando Entity Framework Core.
ms.date: 01/30/2020
ms.openlocfilehash: c91980504b0f9de859c6d211f3a1f47435b2d3cc
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396262"
---
# <a name="implement-the-infrastructure-persistence-layer-with-entity-framework-core"></a>Implementare il livello di persistenza dell'infrastruttura con Entity Framework Core

Quando si usano database relazionali come SQL Server, Oracle o PostgreSQL, uno degli approcci consigliati consiste nell'implementare il livello di persistenza basato su Entity Framework. Entity Framework supporta LINQ e fornisce oggetti fortemente tipizzati per il modello, oltre alla persistenza semplificata nel database.

Entity Framework è da tempo incluso in .NET Framework. Quando si usa .NET Core, è necessario usare anche Entity Framework Core, che viene eseguito in Windows o Linux in modo analogo a .NET Core. EF Core è una riscrittura completa di Entity Framework implementata con un footprint molto più piccolo e importanti miglioramenti delle prestazioni.

## <a name="introduction-to-entity-framework-core"></a>Introduzione a Entity Framework Core

Entity Framework (EF) Core è una versione semplice, estendibile e multipiattaforma della tecnologia di accesso dati Entity Framework più diffusa. È stato introdotto con .NET Core a metà del 2016.

Dal momento che nella documentazione Microsoft è già disponibile un'introduzione a Entity Framework Core, in questa sede verranno forniti solo i collegamenti a tali informazioni.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Entity Framework Core** \
  [https://docs.microsoft.com/ef/core/](/ef/core/)

- **Introduzione a ASP.NET Core e Entity Framework Core con Visual Studio** \
  [https://docs.microsoft.com/aspnet/core/data/ef-mvc/](/aspnet/core/data/ef-mvc/)

- **Classe DbContext** \
  [https://docs.microsoft.com/dotnet/api/microsoft.entityframeworkcore.dbcontext](xref:Microsoft.EntityFrameworkCore.DbContext)

- **Confrontare EF Core & EF6. x** \
  [https://docs.microsoft.com/ef/efcore-and-ef6/index](/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a>Infrastruttura in Entity Framework Core dal punto di vista della progettazione basata su dominio

Dal punto di vista della progettazione basata su dominio, un'importante funzionalità di Entity Framework è data dalla possibilità di usare le entità di dominio POCO, note nella terminologia di Entity Framework come *entità Code First* POCO. Se si usano le entità di dominio POCO, le classi del modello di dominio non riconoscono la persistenza, risultando conformi ai principi di [Persistence Ignorance](https://deviq.com/persistence-ignorance/) e [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance).

Per ogni schema di progettazione basata su dominio è consigliabile incapsulare le regole e il comportamento del dominio regole all'interno della classe di entità stessa, in modo che possa controllare invarianti, convalide e regole durante l'accesso a qualsiasi raccolta. Nella progettazione basata su dominio non è quindi buona norma consentire l'accesso pubblico a raccolte di oggetti valore o entità figlio. È invece opportuno esporre metodi che consentano di controllare come e quando è possibile aggiornare i campi e le raccolte di proprietà, nonché il comportamento e le azioni che devono essere eseguite in tale circostanza.

A partire da Entity Framework Core 1.1, per soddisfare tali requisiti di progettazione basata su dominio, nelle entità è possibile includere campi normali invece di proprietà pubbliche. Se non si vuole che un campo di entità sia accessibile dall'esterno, è sufficiente creare solo l'attributo o il campo invece di una proprietà. È anche possibile usare setter di proprietà private.

In modo analogo, è ora possibile accedere in sola lettura alle raccolte usando una proprietà pubblica tipizzata come `IReadOnlyCollection<T>`, che è supportata da un membro di campo privato per la raccolta (ad esempio `List<T>`) nell'entità che si basa su Entity Framework per la persistenza. Nelle versioni precedenti di Entity Framework le proprietà della raccolta dovevano supportare `ICollection<T>`, di conseguenza gli sviluppatori che usavano la classe di entità padre potevano aggiungere o rimuovere elementi tramite le relative raccolte di proprietà. Tale possibilità era però in conflitto con i criteri consigliati per la progettazione basata su dominio.

È possibile usare una raccolta privata esponendo al contempo un oggetto `IReadOnlyCollection<T>` di sola lettura, come illustrato nell'esempio di codice seguente:

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...

    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

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

        var orderItem = new OrderItem(productId, productName,
                                      unitPrice, discount,
                                      pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

`OrderItems`È possibile accedere alla proprietà solo in modalità di sola lettura tramite `IReadOnlyCollection<OrderItem>` . Questo tipo è di sola lettura ed è quindi protetto dai normali aggiornamenti esterni.

Entity Framework Core offre un modo per eseguire il mapping del modello di dominio al database fisico senza "contaminare" il modello di dominio. Si tratta di codice .NET POCO puro, dal momento che l'azione di mapping viene implementata nel livello di persistenza. In tale azione di mapping è necessario configurare il mapping tra campi e database. Nell'esempio seguente del metodo `OnModelCreating` della classe `OrderingContext` e `OrderEntityTypeConfiguration`, la chiamata a `SetPropertyAccessMode` indica a Entity Framework Core di accedere alla proprietà `OrderItems` tramite il relativo campo.

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities' configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
        // Other configuration

        var navigation =
              orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        //EF access the OrderItem collection property through its backing field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        // Other configuration
    }
}
```

Quando si utilizzano campi anziché proprietà, l' `OrderItem` entità viene mantenute come se disponesse di una `List<OrderItem>` Proprietà. Tale entità espone comunque una singola funzione di accesso, ovvero il metodo `AddOrderItem` per aggiungere nuovi elementi all'ordine. Di conseguenza, il comportamento e i dati sono strettamente legati tra loro e saranno coerenti in tutto il codice dell'applicazione che usa il modello di dominio.

## <a name="implement-custom-repositories-with-entity-framework-core"></a>Implementare repository personalizzati con Entity Framework Core

A livello di implementazione, un repository è semplicemente una classe che contiene codice per la persistenza dei dati coordinato da un'unità di lavoro (DBContext in Entity Framework Core) durante l'esecuzione degli aggiornamenti, come illustrato nella classe seguente:

```csharp
// using directives...
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

        public BuyerRepository(OrderingContext context)
        {
            _context = context ?? throw new ArgumentNullException(nameof(context));
        }

        public Buyer Add(Buyer buyer)
        {
            return _context.Buyers.Add(buyer).Entity;
        }

        public async Task<Buyer> FindAsync(string buyerIdentityGuid)
        {
            var buyer = await _context.Buyers
                .Include(b => b.Payments)
                .Where(b => b.FullName == buyerIdentityGuid)
                .SingleOrDefaultAsync();

            return buyer;
        }
    }
}
```

L' `IBuyerRepository` interfaccia deriva dal livello del modello di dominio sotto forma di contratto. L'implementazione del repository viene però effettuata a livello di persistenza e infrastruttura.

L'elemento DbContext di Entity Framework attraversa il costruttore tramite il modello di inserimento delle dipendenze. È condiviso tra più repository nello stesso ambito della richiesta HTTP, grazie alla relativa durata predefinita (`ServiceLifetime.Scoped`) nel contenitore IoC (che può essere anche impostato in modo esplicito con `services.AddDbContext<>`).

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a>Metodi da implementare in un repository (aggiornamenti o transazioni e query)

All'interno di ogni classe di repository, è necessario inserire i metodi di persistenza che aggiornano lo stato delle entità contenute dall'aggregato correlato. Tenere presente che esiste una relazione uno a uno tra un aggregato e il repository correlato. Considerare che un oggetto entità radice aggregato potrebbe contenere entità figlio incorporate nel relativo grafo di Entity Framework. Un acquirente potrebbe ad esempio usare più metodi di pagamento come entità figlio correlate.

Dal momento che l'approccio per il microservizio Ordering in eShopOnContainers si basa anche su CQS/CQRS, la maggior parte delle query non viene implementata in repository personalizzati. Gli sviluppatori possono scegliere di creare le query e i join necessari per il livello di presentazione senza le restrizioni imposte dagli aggregati, dai repository personalizzati per aggregato e, più in generale dalla progettazione basata su dominio. La maggior parte degli repository personalizzati suggeriti da questa guida include numerosi metodi transazionali o di aggiornamento, ma solo i metodi di query devono ottenere i dati da aggiornare. Il repository BuyerRepository implementa ad esempio un metodo FindAsync, perché l'applicazione deve sapere se un particolare acquirente esiste già prima di creare un nuovo acquirente correlato all'ordine.

I metodi di query effettivi per ottenere i dati da inviare al livello di presentazione o alle app client vengono però implementati, come già detto, nelle query CQRS basate su query flessibili usando Dapper.

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a>Uso di un repository personalizzato invece di usare direttamente DbContext di Entity Framework

La classe Entity Framework DbContext è basata sull'unità di modelli di lavoro e di repository e può essere usata direttamente dal codice, ad esempio da un controller MVC ASP.NET Core. I modelli di unità di lavoro e di repository generano il codice più semplice, come nel microservizio Catalogo CRUD in eShopOnContainers. Nei casi in cui si vuole che il codice sia il più semplice possibile è consigliabile usare direttamente la classe DbContext, come fanno molti sviluppatori.

L'implementazione di repository personalizzati offre però diversi vantaggi quando si implementano microservizi o applicazioni più complesse. I modelli di unità di lavoro e di repository sono progettati per incapsulare il livello di persistenza dell'infrastruttura in modo che sia separato dai livelli dell'applicazione e del modello di dominio. L'implementazione di questi schemi può facilitare l'uso di repository fittizi che simulano l'accesso al database.

Nella figura 7-18 è possibile vedere le differenze tra l'uso di repository (usando direttamente EF DbContext) e i repository, che semplificano la simulazione di questi repository.

![Diagramma che mostra i componenti e il flusso di Dataflow nei due repository.](./media/infrastructure-persistence-layer-implemenation-entity-framework-core/custom-repo-versus-db-context.png)

**Figura 7-18**. Uso di repository personalizzati anziché una semplice classe DbContext

La figura 7-18 Mostra che l'uso di un repository personalizzato aggiunge un livello di astrazione che può essere usato per semplificare il test simulando il repository. Per il comportamento fittizio è possibile scegliere tra diverse alternative. È possibile applicare il comportamento fittizio solo ai repository oppure a un'intera unità di lavoro. In genere è sufficiente applicare il comportamento fittizio solo ai repository e non è necessario ricorrere alle tecniche complesse per astrarre e applicare il comportamento fittizio a un'intera unità di lavoro.

Più avanti, quando verrà trattato il livello dell'applicazione, verrà illustrato il funzionamento del modello di inserimento delle dipendenze in ASP.NET Core e verrà spiegato come implementarlo quando si usano i repository.

In poche parole, i repository personalizzati consentono di testare il codice più facilmente con gli unit test che non sono interessati dallo stato del livello dati. Se si eseguono test che accedono anche al database effettivo tramite Entity Framework, non si tratta di unit test, ma di test di integrazione, sono molto più lenti.

Se si usa direttamente DbContext, è necessario rendere la classe fittizia oppure eseguire gli unit test con un'istanza in memoria di SQL Server contenente dati prevedibili per gli unit test. Una classe DbContext fittizia o il controllo di dati finti richiede tuttavia un intervento maggiore rispetto a un comportamento fittizio a livello di repository. Naturalmente, sarebbe sempre possibile testare i controller MVC.

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a>Durata dell'istanza di DbContext di Entity Framework e IUnitOfWork nel contenitore IoC

Potrebbe essere necessario condividere l'oggetto `DbContext` (esposto come oggetto `IUnitOfWork`) tra più repository all'interno dello stesso ambito della richiesta HTTP. Questa condizione si verifica, ad esempio, quando l'operazione in esecuzione deve gestire più aggregati o semplicemente quando si usano più istanze di repository. È anche importante ricordare che l'interfaccia `IUnitOfWork` fa parte del livello di dominio e non è un tipo di Entity Framework Core.

A questo scopo, è necessario impostare su ServiceLifetime.Scoped la durata del servizio per l'istanza dell'oggetto `DbContext`. Si tratta della durata predefinita quando si registra un oggetto `DbContext` con `services.AddDbContext` nel contenitore IoC dal metodo ConfigureServices del file `Startup.cs` nel progetto API Web di ASP.NET Core. Questa condizione è illustrata nel codice che segue.

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
                               sqlOptions => sqlOptions.MigrationsAssembly(typeof(Startup).GetTypeInfo().
                                                                                    Assembly.GetName().Name));
      },
      ServiceLifetime.Scoped // Note that Scoped is the default choice
                             // in AddDbContext. It is shown here only for
                             // pedagogic purposes.
      );
}
```

La modalità di creazione di un'istanza di DbContext non deve essere configurata come ServiceLifetime.Transient o ServiceLifetime.Singleton.

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a>Durata dell'istanza del repository nel contenitore IoC

In modo analogo, la durata del repository deve essere in genere impostata come ambito (InstancePerLifetimeScope in Autofac). Può anche essere temporanea (InstancePerDependency in Autofac), ma se si usa la durata inclusa nell'ambito il servizio risulterà più efficiente in termini di memoria.

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

L'uso della durata singleton per il repository può causare gravi problemi di concorrenza quando la DbContext è impostata sulla durata dell'ambito (InstancePerLifetimeScope) (durata predefinita per un DBContext).

### <a name="additional-resources"></a>Risorse aggiuntive

- **Implementazione dei modelli di repository e unità di lavoro in un'applicazione MVC ASP.NET** \
  <https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application>

- **Jonathan Allen. Strategie di implementazione per il modello di repository con Entity Framework, elegante e Chain** \
  <https://www.infoq.com/articles/repository-implementation-strategies>

- **Cesar de la Torre. Confronto ASP.NET Core durate del servizio contenitore IoC con gli ambiti dell'istanza del contenitore IoC Autofac** \
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="table-mapping"></a>Mapping tabella

Il mapping di tabella consente di identificare i dati di tabella per i quali eseguire query dal database e che devono essere salvati nel database. In precedenza, è stato spiegato come usare entità di dominio, ad esempio un dominio order o product, per generare uno schema di database correlato. Entity Framework si basa principalmente sul concetto di *convenzioni*. Le convenzioni risolvono domande come "quale sarà il nome di una tabella?" o "quale proprietà è la chiave primaria?" Le convenzioni sono in genere basate sui nomi convenzionali. Ad esempio, è tipico che la chiave primaria sia una proprietà che termina con `Id` .

Per convenzione, ogni entità viene configurata in modo da eseguire il mapping a una tabella con lo stesso nome della proprietà `DbSet<TEntity>` che espone l'entità nel contesto derivato. Se per l'entità specificata non viene definito un valore `DbSet<TEntity>`, viene usato il nome di classe.

### <a name="data-annotations-versus-fluent-api"></a>Annotazioni di dati e API Fluent

Esistono numerose convenzioni aggiuntive di Entity Framework Core e la maggior parte di esse può essere modificata tramite le annotazioni di dati o l'API Fluent, implementata all'interno del metodo OnModelCreating.

Le annotazioni di dati devono essere usate sulle classi stesse del modello di entità e questa costituisce una modalità di utilizzo più intrusiva dal punto di vista della progettazione basata su dominio. Questo in quanto si sta contaminando il modello con annotazioni di dati correlate al database dell'infrastruttura. D'altra parte, l'API Fluent è un modo pratico per modificare la maggior parte delle convenzioni e i mapping all'interno del livello dell'infrastruttura di persistenza dei dati, in modo che il modello di entità sia pulito e scollegato dall'infrastruttura di persistenza.

### <a name="fluent-api-and-the-onmodelcreating-method"></a>API Fluent e il metodo OnModelCreating

Come accennato in precedenza, per modificare le convenzioni e i mapping, è possibile usare il metodo OnModelCreating nella classe DbContext.

Il microservizio Ordering in eShopOnContainers implementa la configurazione e il mapping esplicito, quando necessario, come illustrato nel codice seguente.

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities' configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);

        orderConfiguration.HasKey(o => o.Id);

        orderConfiguration.Ignore(b => b.DomainEvents);

        orderConfiguration.Property(o => o.Id)
            .UseHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

        //Address value object persisted as owned entity type supported since EF Core 2.0
        orderConfiguration
            .OwnsOne(o => o.Address, a =>
            {
                a.WithOwner();
            });

        orderConfiguration
            .Property<int?>("_buyerId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("BuyerId")
            .IsRequired(false);

        orderConfiguration
            .Property<DateTime>("_orderDate")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("OrderDate")
            .IsRequired();

        orderConfiguration
            .Property<int>("_orderStatusId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("OrderStatusId")
            .IsRequired();

        orderConfiguration
            .Property<int?>("_paymentMethodId")
            .UsePropertyAccessMode(PropertyAccessMode.Field)
            .HasColumnName("PaymentMethodId")
            .IsRequired(false);

        orderConfiguration.Property<string>("Description").IsRequired(false);

        var navigation = orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        // DDD Patterns comment:
        //Set as field (New since EF 1.1) to access the OrderItem collection property through its field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        orderConfiguration.HasOne<PaymentMethod>()
            .WithMany()
            .HasForeignKey("_paymentMethodId")
            .IsRequired(false)
            .OnDelete(DeleteBehavior.Restrict);

        orderConfiguration.HasOne<Buyer>()
            .WithMany()
            .IsRequired(false)
            .HasForeignKey("_buyerId");

        orderConfiguration.HasOne(o => o.OrderStatus)
            .WithMany()
            .HasForeignKey("_orderStatusId");
    }
}
```

È possibile impostare tutti i mapping API Fluent nello stesso `OnModelCreating` metodo, ma è consigliabile partizionare il codice e avere più classi di configurazione, una per entità, come illustrato nell'esempio. In particolare per i modelli di grandi dimensioni, è consigliabile disporre di classi di configurazione separate per la configurazione di tipi di entità diversi.

Il codice nell'esempio mostra alcuni mapping e dichiarazioni esplicite. Le convenzioni di Entity Framework Core eseguono però automaticamente molti di questi mapping, di conseguenza il codice effettivo necessario potrebbe essere ridotto.

### <a name="the-hilo-algorithm-in-ef-core"></a>Algoritmo Hi/Lo in Entity Framework Core

Un aspetto interessante del codice nell'esempio precedente è che usa l'[algoritmo Hi/Low](https://vladmihalcea.com/the-hilo-algorithm/) come strategia di generazione delle chiavi.

L'algoritmo Hi/Lo è utile quando sono necessarie chiavi univoche prima di apportare modifiche. Riassumendo, l'algoritmo Hi-Lo assegna identificatori univoci alle righe della tabella, pur non dipendendo immediatamente dall'archiviazione della riga nel database. In questo modo è possibile iniziare subito a usare gli identificatori, come avviene con gli ID dei normali database sequenziali.

L'algoritmo Hi/Lo descrive un meccanismo per il recupero di un batch di ID univoci da una sequenza di database correlata. Questi ID sono sicuri perché il database garantisce l'univocità, pertanto non vi sarà alcuna collisione tra utenti. Questo algoritmo è interessante per i motivi seguenti:

- Non causa interruzioni nello schema Unit of Work.

- Ottiene gli ID di sequenza in batch, per ridurre al minimo i round trip al database.

- Genera un identificatore leggibile, a differenza delle tecniche che usano GUID.

EF Core supporta [Hilo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) con il `UseHiLo` metodo, come illustrato nell'esempio precedente.

### <a name="map-fields-instead-of-properties"></a>Eseguire il mapping di campi anziché di proprietà

Con questa funzionalità, disponibile a partire da Entity Framework Core 1.1, è possibile eseguire direttamente il mapping delle colonne ai campi. Non è possibile usare proprietà nella classe di entità e limitarsi a eseguire il mapping delle colonne di una tabella ai campi. Questa funzionalità viene usata in genere per campi privati relativi a un qualsiasi stato interno che non devono essere accessibili dall'esterno dell'entità.

È possibile eseguire questa operazione con singoli campi o anche con le raccolte, ad esempio un campo `List<>`. Questo aspetto è stato menzionato in precedenza quando è stata illustrata la modellazione delle classi del modello di dominio, ma qui è possibile comprendere in che modo viene eseguito tale mapping con la configurazione di `PropertyAccessMode.Field` evidenziata nel codice precedente.

### <a name="use-shadow-properties-in-ef-core-hidden-at-the-infrastructure-level"></a>Usare le proprietà shadow in Entity Framework Core, nascoste a livello di infrastruttura

In Entity Framework Core le proprietà shadow sono proprietà che non esistono nel modello della classe di entità. I valori e gli stati di queste proprietà vengono gestiti esclusivamente nella classe [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) a livello di infrastruttura.

## <a name="implement-the-query-specification-pattern"></a>Implementare lo schema di specifica della query

Come descritto in precedenza nella sezione relativa alla progettazione, lo schema di specifica della query è un schema di progettazione basato su dominio concepito come punto in cui è possibile inserire la definizione di una query con logica facoltativa di ordinamento e paging.

Lo schema di specifica della query consente di definire una query in un oggetto. Per poter incapsulare una query di paging che cerca alcuni prodotti, ad esempio, è possibile creare una specifica PagedProduct che accetta i parametri di input necessari (pageNumber, pageSize, filter e così via). In questo modo, qualsiasi metodo di repository (in genere un overload List()) accetterà un elemento IQuerySpecification ed eseguirà la query in base a tale specifica.

Un esempio di interfaccia di specifica generica è il codice seguente tratto da [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb).

```csharp
// GENERIC SPECIFICATION INTERFACE
// https://github.com/dotnet-architecture/eShopOnWeb

public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

L'implementazione della classe di base di una specifica generica è la seguente.

```csharp
// GENERIC SPECIFICATION IMPLEMENTATION (BASE CLASS)
// https://github.com/dotnet-architecture/eShopOnWeb

public abstract class BaseSpecification<T> : ISpecification<T>
{
    public BaseSpecification(Expression<Func<T, bool>> criteria)
    {
        Criteria = criteria;
    }
    public Expression<Func<T, bool>> Criteria { get; }

    public List<Expression<Func<T, object>>> Includes { get; } =
                                           new List<Expression<Func<T, object>>>();

    public List<string> IncludeStrings { get; } = new List<string>();

    protected virtual void AddInclude(Expression<Func<T, object>> includeExpression)
    {
        Includes.Add(includeExpression);
    }

    // string-based includes allow for including children of children
    // e.g. Basket.Items.Product
    protected virtual void AddInclude(string includeString)
    {
        IncludeStrings.Add(includeString);
    }
}
```

La specifica seguente carica una singola entità basket in base all'ID del carrello o all'ID dell'acquirente a cui appartiene il carrello. Verrà [caricata con entusiasmo](/ef/core/querying/related-data) la raccolta del carrello `Items` .

```csharp
// SAMPLE QUERY SPECIFICATION IMPLEMENTATION

public class BasketWithItemsSpecification : BaseSpecification<Basket>
{
    public BasketWithItemsSpecification(int basketId)
        : base(b => b.Id == basketId)
    {
        AddInclude(b => b.Items);
    }

    public BasketWithItemsSpecification(string buyerId)
        : base(b => b.BuyerId == buyerId)
    {
        AddInclude(b => b.Items);
    }
}
```

È infine possibile osservare sotto in che modo un repository generico di Entity Framework può usare tale specifica per filtrare ed eseguire il caricamento eager di dati correlati a un dato tipo di entità T.

```csharp
// GENERIC EF REPOSITORY WITH SPECIFICATION
// https://github.com/dotnet-architecture/eShopOnWeb

public IEnumerable<T> List(ISpecification<T> spec)
{
    // fetch a Queryable that includes all expression-based includes
    var queryableResultWithIncludes = spec.Includes
        .Aggregate(_dbContext.Set<T>().AsQueryable(),
            (current, include) => current.Include(include));

    // modify the IQueryable to include any string-based include statements
    var secondaryResult = spec.IncludeStrings
        .Aggregate(queryableResultWithIncludes,
            (current, include) => current.Include(include));

    // return the result of the query using the specification's criteria expression
    return secondaryResult
                    .Where(spec.Criteria)
                    .AsEnumerable();
}
```

Oltre a incapsulare la logica di filtro, la specifica è in grado di indicare la forma dei dati da restituire, incluse le proprietà da popolare.

Sebbene non sia consigliabile tornare `IQueryable` da un repository, è possibile usarli all'interno del repository per creare un set di risultati. È possibile osservare questo approccio usato nel metodo List precedente, che usa espressioni intermedie `IQueryable` per creare l'elenco di inclusioni della query prima di eseguire la query con i criteri della specifica sull'ultima riga.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Mapping tabella** \
  [https://docs.microsoft.com/ef/core/modeling/relational/tables](/ef/core/modeling/relational/tables)

- **Usare HiLo per generare chiavi con Entity Framework Core** \
  <https://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/>

- **Campi sottoposti a backup** \
  [https://docs.microsoft.com/ef/core/modeling/backing-field](/ef/core/modeling/backing-field)

- **Steve Smith. Raccolte incapsulate in Entity Framework Core** \
  <https://ardalis.com/encapsulated-collections-in-entity-framework-core>

- **Proprietà Shadow** \
  [https://docs.microsoft.com/ef/core/modeling/shadow-properties](/ef/core/modeling/shadow-properties)

- **Modello di specifica** \
  <https://deviq.com/specification-pattern/>

> [!div class="step-by-step"]
> [Precedente](infrastructure-persistence-layer-design.md) 
>  [Avanti](nosql-database-persistence-infrastructure.md)
