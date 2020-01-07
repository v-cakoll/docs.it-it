---
title: Implementazione del livello dell'applicazione di microservizi tramite l'API Web
description: Architettura di microservizi .NET per applicazioni .NET incluse in contenitori | Informazioni sull'inserimento di dipendenze e sugli schemi Mediator e i relativi dettagli di implementazione nel livello dell'applicazione API Web.
ms.date: 10/08/2018
ms.openlocfilehash: 08cb409b06a54c6b30afa393a817e14bd64fbcbf
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "73737499"
---
# <a name="implement-the-microservice-application-layer-using-the-web-api"></a>Implementare il livello dell'applicazione del microservizio usando l'API Web

## <a name="use-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a>Usare l'inserimento delle dipendenze per inserire oggetti dell'infrastruttura nel livello dell'applicazione

Come accennato in precedenza, il livello dell'applicazione può essere implementato come parte dell'elemento (assembly) che si sta creando, ad esempio in un progetto API Web o un progetto app Web MVC. Nel caso di un microservizio creato con ASP.NET Core, il livello dell'applicazione sarà in genere la libreria di API Web. Per separare ciò che proviene da ASP.NET Core (l'infrastruttura più i controlli) dal codice del livello dell'applicazione personalizzato, è facoltativamente possibile inserire il livello dell'applicazione in una libreria di classi separata.

Il codice del livello dell'applicazione del microservizio degli ordini, ad esempio, viene direttamente implementato come parte del progetto **Ordering.API** (un progetto API Web ASP.NET Core), come illustrato nella figura 7-23.

:::image type="complex" source="./media/microservice-application-layer-implementation-web-api/ordering-api-microservice.png" alt-text="Screenshot del microservizio ordering. API nella Esplora soluzioni.":::
La visualizzazione Esplora soluzioni del microservizio Ordering.API contiene le sottocartelle della cartella Application: Behaviors, Commands, DomainEventHandlers, IntegrationEvents, Models, Queries e Validations.
:::image-end:::

**Figura 7-23**. Livello dell'applicazione nel progetto API Web ASP.NET Core Ordering.API

ASP.NET Core include un semplice [contenitore IoC predefinito](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (rappresentato dall'interfaccia IServiceProvider) che supporta l'inserimento del costruttore per impostazione predefinita, mentre ASP.NET rende disponibili determinati servizi tramite l'inserimento delle dipendenze. In ASP.NET Core il termine *servizio* indica qualsiasi tipo registrato che verrà inserito tramite l'inserimento delle dipendenze. I servizi del contenitore predefinito vengono configurati nel metodo ConfigureServices nella classe Startup dell'applicazione. Le dipendenze vengono implementate nei servizi necessari per un tipo e registrati nel contenitore IoC.

È in genere necessario inserire dipendenze che implementano oggetti dell'infrastruttura. Un repository è un tipico esempio di dipendenza da inserire, ma è possibile inserire qualsiasi altra dipendenza dell'infrastruttura disponibile. Per implementazioni più semplici, è possibile inserire direttamente l'oggetto schema Unit of Work (oggetto DbContext EF), perché DBContext è anche l'implementazione degli oggetti persistenza dell'infrastruttura.

Nell'esempio seguente è possibile osservare come .NET Core inserisca gli oggetti del repository necessari tramite il costruttore. La classe è un gestore comando, che verrà illustrato nella sezione successiva.

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
                                     IOrderRepository orderRepository,
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ??
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ??
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ??
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,
                              message.CardNumber, message.CardSecurityNumber,
                              message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

La classe usa i repository inseriti per eseguire la transazione e rendere permanenti le modifiche allo stato. Non è importante se tale classe è un gestore comando, un metodo del controller API Web ASP.NET Core o un [servizio dell'applicazione nella progettazione basata su domini](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/). È in definitiva una semplice classe che usa repository, entità di dominio e altre funzionalità di coordinamento dell'applicazione in modo simile a un gestore comando. L'inserimento delle dipendenze funziona allo stesso modo per tutte le classi citate, come nell'esempio che usa l'inserimento delle dipendenze basato sul costruttore.

### <a name="register-the-dependency-implementation-types-and-interfaces-or-abstractions"></a>Registrare i tipi di implementazione delle dipendenze e interfacce o astrazioni

Prima di usare gli oggetti inseriti tramite i costruttori, è necessario sapere dove registrare le interfacce e le classi che generano gli oggetti inseriti nelle classi dell'applicazione tramite l'inserimento delle dipendenze, come nell'inserimento delle dipendenze basato sul costruttore, come illustrato prima.

#### <a name="use-the-built-in-ioc-container-provided-by-aspnet-core"></a>Usare il contenitore IoC predefinito specificato da ASP.NET Core

Quando si usa il contenitore IoC predefinito fornito da ASP.NET Core, si registrano i tipi che si vuole inserire nel metodo ConfigureServices nel file Startup.cs, come nel codice seguente:

```csharp
// Registration of types into ASP.NET Core built-in container
public void ConfigureServices(IServiceCollection services)
{
    // Register out-of-the-box framework services.
    services.AddDbContext<CatalogContext>(c =>
    {
        c.UseSqlServer(Configuration["ConnectionString"]);
    },
    ServiceLifetime.Scoped
    );
    services.AddMvc();
    // Register custom application dependencies.
    services.AddScoped<IMyCustomRepository, MyCustomSQLRepository>();
}
```

Lo schema più comune quando si registrano i tipi in un contenitore IoC prevede la registrazione di una coppia di tipi: un'interfaccia e la classe di implementazione correlata. Quando dunque si richiede un oggetto dal contenitore IoC tramite un costruttore, si richiede un oggetto di un determinato tipo di interfaccia. Nell'esempio precedente l'ultima riga indica che, quando uno dei costruttori ha una dipendenza da IMyCustomRepository (interfaccia o astrazione), il contenitore IoC inserirà un'istanza della classe di implementazione MyCustomSQLServerRepository.

#### <a name="use-the-scrutor-library-for-automatic-types-registration"></a>Usare la libreria Scrutor per la registrazione automatica dei tipi

Quando si usa l'inserimento delle dipendenze in .NET Core, potrebbe essere necessario analizzare un assembly e registrarne automaticamente i tipi, per convenzione. Questa funzionalità non è attualmente disponibile in ASP.NET Core. È tuttavia possibile la libreria [Scrutor](https://github.com/khellang/Scrutor) a tale scopo. Questo approccio è utile quando è necessario registrare decine di tipi nel contenitore IoC.

#### <a name="additional-resources"></a>Risorse aggiuntive

- **Matthew King. Registrazione di servizi con Scrutor** \
  <https://www.mking.net/blog/registering-services-with-scrutor>

- **Kristian Hellang. Scrutor.** Repository GitHub. \
  <https://github.com/khellang/Scrutor>

#### <a name="use-autofac-as-an-ioc-container"></a>Usare Autofac come contenitore IoC

È anche possibile usare contenitori IoC aggiuntivi e collegarli alla pipeline ASP.NET Core, come nel microservizio degli ordini in eShopOnContainers, che usa [Autofac](https://autofac.org/). Quando si usa Autofac, in genere si registrano i tipi tramite i moduli, che consentono di dividere i tipi di registrazioni tra più file a seconda della posizione dei tipi, proprio come si potrebbero distribuire i tipi di applicazioni in più librerie di classi.

Il seguente, ad esempio, è il [modulo dell'applicazione Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) per il progetto [API Web Ordering.API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) con i tipi da inserire.

```csharp
public class ApplicationModule : Autofac.Module
{
    public string QueriesConnectionString { get; }
    public ApplicationModule(string qconstr)
    {
        QueriesConnectionString = qconstr;
    }

    protected override void Load(ContainerBuilder builder)
    {
        builder.Register(c => new OrderQueries(QueriesConnectionString))
            .As<IOrderQueries>()
            .InstancePerLifetimeScope();
        builder.RegisterType<BuyerRepository>()
            .As<IBuyerRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<OrderRepository>()
            .As<IOrderRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<RequestManager>()
            .As<IRequestManager>()
            .InstancePerLifetimeScope();
   }
}
```

Autofac offre inoltre una funzionalità per [l'analisi degli assembly e la registrazione dei tipi in base alle convenzioni di denominazione](https://autofac.readthedocs.io/en/latest/register/scanning.html).

Il processo di registrazione e i relativi concetti sono molto simili al modo in cui è possibile registrare i tipi con il contenitore IoC ASP.NET Core, ma la sintassi quando si usa Autofac è leggermente diversa.

Nel codice di esempio l'astrazione IOrderRepository viene registrata con la classe di implementazione OrderRepository. Quando dunque un costruttore dichiara una dipendenza tramite l'astrazione o l'interfaccia IOrderRepository, il contenitore IoC inserirà un'istanza della classe OrderRepository.

Il tipo di ambito di un'istanza determina come un'istanza viene condivisa tra le richieste per lo stesso servizio o dipendenza. Quando viene effettuata una richiesta per una dipendenza, il contenitore IoC può restituire quanto segue:

- Una singola istanza per ogni ambito di durata (detta *con ambito* nel contenitore IoC ASP.NET Core).

- Una nuova istanza per ogni dipendenza (detta *temporanea* nel contenitore IoC ASP.NET Core).

- Una singola istanza condivisa tra tutti gli oggetti tramite il contenitore IoC (detta *singleton* nel contenitore IoC ASP.NET Core).

#### <a name="additional-resources"></a>Risorse aggiuntive

- **Introduzione all'inserimento delle dipendenze in ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection](/aspnet/core/fundamentals/dependency-injection)

- **Autofac.** Documentazione ufficiale. \
  <https://docs.autofac.org/en/latest/>

- **Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes - Cesar de la Torre** (Confronto tra la durata del servizio contenitore ASP.NET Core IoC e gli ambiti delle istanze di contenitore Autofac IoC) \
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="implement-the-command-and-command-handler-patterns"></a>Implementare gli schemi Command e Command Handler

Nell'esempio di inserimento delle dipendenze tramite costruttore illustrato nella sezione precedente il contenitore IoC ha inserito i repository tramite un costruttore in una classe. Ma esattamente dove sono stati inseriti? In un'API Web semplice, ad esempio il microservizio catalogo in eShopOnContainers, vengono inseriti nel livello dei controller MVC, in un costruttore del controller, come parte della pipeline di richiesta di ASP.NET Core. Nel codice iniziale di questa sezione (la classe [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) del servizio Ordering.API in eShopOnContainers), tuttavia, l'inserimento delle dipendenze viene eseguito tramite il costruttore di un particolare gestore comando. Verrà ora illustrato che cos'è un gestore comando e perché usarlo.

Lo schema Command è intrinsecamente correlato allo schema CQRS illustrato prima in questa guida. CQRS presenta due aree. La prima è quella delle query, in cui si usano query semplificate con il micro ORM [Dapper](https://github.com/StackExchange/dapper-dot-net), illustrato in precedenza. La seconda area è quella dei comandi, ovvero il punto iniziale delle transazioni e il canale di input dall'esterno del servizio.

Come illustrato nella figura 7-24, lo schema si basa sull'accettazione dei comandi dal lato client, sulla loro elaborazione in base alle regole del modello di dominio e infine sulla persistenza degli stati con le transazioni.

![Diagramma che mostra il flusso di dati di alto livello dal client al database.](./media/microservice-application-layer-implementation-web-api/high-level-writes-side.png)

**Figura 7-24**. Panoramica generale dei comandi o "lato transazionale" nello schema CQRS

La figura 7-24 Mostra che l'app dell'interfaccia utente invia un comando tramite l'API che raggiunge una `CommandHandler`, che dipende dal modello di dominio e dall'infrastruttura, per aggiornare il database.

### <a name="the-command-class"></a>Classe di comando

Un comando è una richiesta per il sistema di eseguire un'azione che modifica lo stato del sistema. I comandi sono imperativi e devono essere elaborati una sola volta.

Poiché i comandi sono imperativi, in genere vengono denominati con un verbo al modo imperativo (ad esempio, "create" o "update") e possono includere il tipo di aggregazione, ad esempio CreateOrderCommand. Diversamente da un evento, un comando non è un fatto avvenuto nel passato, ma solo una richiesta e quindi può essere rifiutato.

I comandi possono essere originati dall'interfaccia utente a seguito di una richiesta di un utente o da un gestore di processi quando ordina a un'aggregazione di eseguire un'azione.

Una caratteristica importante di un comando è che deve essere elaborato una sola volta da un singolo ricevitore. Un comando è infatti una singola azione o transazione che si vuole eseguire nell'applicazione. Lo stesso comando di creazione di un ordine, ad esempio, non deve essere elaborato più di una volta. Si tratta di una differenza importante rispetto agli eventi. Gli eventi possono essere elaborati più volte, perché più sistemi o microservizi possono essere interessati.

È anche importante che un comando venga elaborato una sola volta qualora non sia idempotente. Un comando è idempotente se può essere eseguito più volte senza modificare il risultato, a causa della natura del comando o del modo in cui il sistema gestisce il comando.

È consigliabile rendere idempotenti i comandi e gli aggiornamenti quando è opportuno per le regole business e gli invarianti del dominio. Per usare lo stesso esempio, se per qualsiasi motivo (logica di ripetizione dei tentativi, intrusioni e così via) lo stesso comando CreateOrder raggiunge più volte il sistema, è consigliabile identificarlo e assicurarsi di non creare più ordini. A questo scopo, è necessario associare alle operazioni qualche forma di identità e stabilire se il comando è già stato elaborato.

Un comando viene inviato a un singolo ricevitore e non viene pubblicato. La pubblicazione è riservata agli eventi che determinano un fatto, ovvero qualcosa che è accaduto e potrebbe essere interessante per i ricevitori dell'evento. Nel caso degli eventi, per l'entità di pubblicazione non è importante chi riceve l'evento o come lo gestisce, ma gli eventi di dominio o integrazione, di cui si è già parlato nelle sezioni precedenti, sono diversi.

Un comando viene implementato con una classe contenente campi dati o raccolte con tutte le informazioni necessarie per eseguire tale comando. Un comando è un particolare tipo di DTO (Data Transfer Object), usato in modo specifico per richiedere modifiche o transazioni. Il comando in sé si basa esclusivamente sulle informazioni necessarie per elaborare il comando.

Nell'esempio seguente viene illustrata la classe `CreateOrderCommand` semplificata. Si tratta di un comando non modificabile usato nel microservizio degli ordini in eShopOnContainers.

```csharp
// DDD and CQRS patterns comment
// Note that we recommend that you implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties
[DataContract]
public class CreateOrderCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    private readonly List<OrderItemDTO> _orderItems;
    [DataMember]
    public string City { get; private set; }
    [DataMember]
    public string Street { get; private set; }
    [DataMember]
    public string State { get; private set; }
    [DataMember]
    public string Country { get; private set; }
    [DataMember]
    public string ZipCode { get; private set; }
    [DataMember]
    public string CardNumber { get; private set; }
    [DataMember]
    public string CardHolderName { get; private set; }
    [DataMember]
    public DateTime CardExpiration { get; private set; }
    [DataMember]
    public string CardSecurityNumber { get; private set; }
    [DataMember]
    public int CardTypeId { get; private set; }
    [DataMember]
    public IEnumerable<OrderItemDTO> OrderItems => _orderItems;

    public CreateOrderCommand()
    {
        _orderItems = new List<OrderItemDTO>();
    }

    public CreateOrderCommand(List<BasketItem> basketItems, string city,
        string street,
        string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = MapToOrderItems(basketItems);
        City = city;
        Street = street;
        State = state;
        Country = country;
        ZipCode = zipcode;
        CardNumber = cardNumber;
        CardHolderName = cardHolderName;
        CardSecurityNumber = cardSecurityNumber;
        CardTypeId = cardTypeId;
        CardExpiration = cardExpiration;
    }

    public class OrderItemDTO
    {
        public int ProductId { get; set; }
        public string ProductName { get; set; }
        public decimal UnitPrice { get; set; }
        public decimal Discount { get; set; }
        public int Units { get; set; }
        public string PictureUrl { get; set; }
    }
}
```

In sostanza, la classe del comando contiene tutti i dati necessari per eseguire una transazione aziendale usando gli oggetti modello di dominio. I comandi quindi sono semplicemente strutture dei dati contenenti dati di sola lettura e nessun comportamento. Il nome del comando ne indica lo scopo. In numerosi linguaggi, come C#, i comandi sono rappresentati come classi, ma non si tratta di vere e proprie classi nel senso degli oggetti.

Un'altra caratteristica dei comandi è di non essere modificabili, perché l'utilizzo previsto è che vengano elaborati direttamente dal modello di dominio. Non è necessario modificarli nell'arco della durata prevista. In una classe C# l'immutabilità può essere ottenuta anche senza setter o altri metodi che modificano lo stato interno.

Tenere presente che se si intende o si prevede che i comandi vengano sottoposti a un processo di serializzazione/deserializzazione, le proprietà devono avere un setter privato e l'attributo `[DataMember]` (o `[JsonProperty]`), altrimenti il deserializzatore non sarà in grado di ricostruire l'oggetto nella destinazione con i valori richiesti.

Ad esempio, la classe del comando per la creazione di un ordine è probabilmente simile, in termini di dati, all'ordine che si vuole creare, ma è altrettanto probabile che non siano necessari gli stessi attributi. Ad esempio, `CreateOrderCommand` non dispone di un ID ordine, perché l'ordine non è ancora stato creato.

Molte classi di comandi possono essere semplici e richiedere solo alcuni campi per gli stati che devono essere modificati, ad esempio quando si deve solo modificare lo stato di un ordine da "in corso" a "pagato" o "spedito" usando un comando simile al seguente:

```csharp
[DataContract]
public class UpdateOrderStatusCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    public string Status { get; private set; }

    [DataMember]
    public string OrderId { get; private set; }

    [DataMember]
    public string BuyerIdentityGuid { get; private set; }
}
```

Alcuni sviluppatori preferiscono tenere gli oggetti richiesta dell'interfaccia utente separati dagli oggetti DTO dei comandi, anche se non è necessario. Si tratta di una separazione noiosa, non particolarmente utile, e la forma degli oggetti è quasi esattamente la stessa. In eShopOnContainers, ad esempio, alcuni comandi provengono direttamente dal lato client.

### <a name="the-command-handler-class"></a>Classe del gestore comando

È consigliabile implementare una classe di gestore comando specifica per ogni comando. In tale classe, che è alla base del funzionamento dello schema, si useranno l'oggetto comando, gli oggetti dominio e gli oggetti del repository dell'infrastruttura. Il gestore comando è di fatto il cuore del livello dell'applicazione in termini di CQRS e progettazione basata su domini. Tutta la logica del dominio deve tuttavia essere contenuta nelle classi di dominio, ovvero le radici di aggregazione (entità radice), le entità figlio o i [servizi di dominio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), ma non nel gestore comando, che è una classe del livello dell'applicazione.

La classe del gestore comandi offre un efficace trampolino di lancio per il modo in cui si ottiene il principio di singola responsabilità (SRP, Single Responsibility Principle) menzionato in una sezione precedente.

Un gestore comando riceve un comando e ottiene un risultato dall'aggregazione usata. Il risultato deve essere la corretta esecuzione del comando o un'eccezione. Se è un'eccezione, lo stato del sistema non dovrebbe risultare modificato.

Il gestore comando in genere esegue questi passaggi:

- Riceve l'oggetto comando, ad esempio un DTO (dal [Mediator](https://en.wikipedia.org/wiki/Mediator_pattern) o da un altro oggetto dell'infrastruttura).

- Verifica che il comando sia valido (se non viene convalidato dal Mediator).

- Crea un'istanza della radice di aggregazione che è la destinazione del comando corrente.

- Esegue il metodo sull'istanza della radice di aggregazione, ottenendo dal comando i dati necessari.

- Rende permanente il nuovo stato dell'aggregazione nel database correlato. Quest'ultima operazione è la transazione vera e propria.

Un gestore comando in genere si occupa di una singola aggregazione basata sulla radice di aggregazione (entità radice). Se più aggregazioni devono essere interessate dalla ricezione di un singolo comando, è possibile usare gli eventi di dominio per propagare gli stati o le azioni in più aggregazioni.

L'importante in questo caso è che, quando un comando viene elaborato, tutta la logica di dominio deve essere nel modello di dominio (le aggregazioni), completamente incapsulata e pronta per il testing unità. Il gestore comando è solo un modo per ottenere il modello di dominio dal database e, come passaggio finale, per indicare al livello infrastruttura (repository) di rendere permanenti le modifiche quando il modello viene modificato. Il vantaggio di questo approccio è che è possibile effettuare il refactoring della logica di dominio in un modello di dominio avanzato, completamente incapsulato e isolato senza modificare il codice nei livelli infrastruttura o applicazione, che costituiscono il livello di plumbing (gestori comando, API Web, repository e così via).

Quando i gestori comando sono complessi, con una logica eccessiva, può trattarsi di code smell. Esaminarli e, se si trova la logica di dominio, effettuare il refactoring del codice per spostare tale comportamento del dominio nei metodi degli oggetti dominio (la radice di aggregazione e l'entità figlio).

Come esempio di una classe di gestori di comandi, il codice seguente mostra la stessa classe di `CreateOrderCommandHandler` visualizzata all'inizio di questo capitolo. In questo caso, sono in evidenza il metodo Handle e le operazioni con gli oggetti o le aggregazioni del modello di dominio.

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
                                     IOrderRepository orderRepository,
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ??
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ??
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ??
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,
                              message.CardNumber, message.CardSecurityNumber,
                              message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

I seguenti sono passaggi aggiuntivi che devono essere eseguiti da un gestore comando:

- Usare i dati del comando per operare con i metodi e il comportamento della radice di aggregazione.

- All'interno degli oggetti dominio, generare eventi di dominio mentre la transazione è in esecuzione, ma trasparente dal punto di vista del gestore comando.

- Se il risultato dell'operazione di aggregazione è positivo e dopo che la transazione è stata completata, generare gli eventi di integrazione. che potrebbe anche essere generato dalle classi dell'infrastruttura, ad esempio i repository.

#### <a name="additional-resources"></a>Risorse aggiuntive

- **Contrassegno. Ai limiti, le applicazioni non sono orientate agli oggetti** \
  <https://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/>

- **Comandi ed eventi** \
  <https://cqrs.nu/Faq/commands-and-events>

- **What does a command handler do?** (Qual è la funzione di un gestore comandi?) \
  <https://cqrs.nu/Faq/command-handlers>

- **Jimmy Bogard. Modelli di comandi di dominio: gestori** \
  <https://jimmybogard.com/domain-command-patterns-handlers/>

- **Jimmy Bogard. Modelli di comando di dominio-convalida** \
  <https://jimmybogard.com/domain-command-patterns-validation/>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a>Pipeline di elaborazione del comando: come attivare un gestore comando

La domanda successiva è come richiamare un gestore comando. È possibile chiamarlo manualmente da ogni controller ASP.NET Core correlato. Tale approccio sarebbe tuttavia troppo vincolante e non è l'ideale.

Le altre due principali opzioni, che sono quelle consigliate, sono:

- Tramite un elemento schema Mediator in memoria.

- Con una coda di messaggi asincroni, tra i controller e i gestori.

### <a name="use-the-mediator-pattern-in-memory-in-the-command-pipeline"></a>Usare lo schema Mediator (in memoria) nella pipeline del comando

Come illustrato nella figura 7-25, in un approccio CQRS si usa un Mediator intelligente, simile a un bus in memoria, in grado di eseguire il reindirizzamento al gestore comandi appropriato in base al tipo di comando o DTO che viene ricevuto. Le singole frecce nere tra i componenti rappresentano le dipendenze tra gli oggetti (in molti casi inseriti tramite inserimento delle dipendenze) con le interazioni correlate.

![Diagramma che mostra un flusso di dati più dettagliato dal client al database.](./media/microservice-application-layer-implementation-web-api/mediator-cqrs-microservice.png)

**Figura 7-25**. Uso dello schema Mediator in esecuzione in un singolo microservizio CQRS

Il diagramma precedente mostra uno zoom dall'immagine 7-24: il controller ASP.NET Core invia il comando alla pipeline dei comandi di Mediator, in modo da ottenere il gestore appropriato.

L'uso dello schema Mediator è sensato perché nelle applicazioni aziendali l'elaborazione delle richieste può essere complessa. Potrebbe essere necessario aggiungere un numero indeterminato di problematiche trasversali, ad esempio registrazione, convalide, controllo e sicurezza. In questi casi, è possibile affidarsi a una pipeline di Mediator (vedere [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern)) per fornire un mezzo per gestire questi comportamenti o problematiche trasversali aggiuntive.

Un Mediator è un oggetto che incapsula la modalità di questo processo: coordina l'esecuzione in base a uno stato, il modo in cui un gestore comando viene richiamato o il payload fornito al gestore. Con un componente Mediator è possibile applicare le problematiche trasversali in modo centralizzato e trasparente applicando gli elementi Decorator (o [comportamenti della pipeline](https://github.com/jbogard/MediatR/wiki/Behaviors) da [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)). Per altre informazioni, vedere lo [schema Decorator](https://en.wikipedia.org/wiki/Decorator_pattern).

Gli elementi Decorator e i comportamenti sono simili alla [programmazione orientata agli aspetti](https://en.wikipedia.org/wiki/Aspect-oriented_programming), che viene applicata solo a una pipeline di processi specifica gestita dal componente Mediator. Gli aspetti nella programmazione orientata agli aspetti, che implementano i problemi trasversali, vengono applicati in base ai *weaver degli aspetti* inseriti in fase di compilazione o in base all'intercettazione della chiamata all'oggetto. Si dice a volte che entrambi i tipici approcci alla programmazione orientata agli aspetti "fanno magie", perché non è facile vedere come funziona la programmazione orientata agli aspetti. Quando si affrontano problemi o bug gravi, può essere difficile eseguire il debug della programmazione orientata agli aspetti. D'altra parte, questi elementi Decorator/comportamenti sono espliciti e vengono applicati solo nel contesto del Mediator, quindi il debug è molto più prevedibile e semplice.

Nel microservizio degli ordini di eShopOnContainers vengono implementati due comportamenti di esempio, una classe [LogBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) e una classe [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs). L'implementazione dei comportamenti è illustrata nella sezione successiva mostrando il modo in cui eShopOnContainers usa i [comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) [Mediator 3](https://www.nuget.org/packages/MediatR/3.0.0) .

### <a name="use-message-queues-out-of-proc-in-the-commands-pipeline"></a>Usare le code di messaggi (out-of-process) nella pipeline del comando

È anche possibile usare i messaggi asincroni basati su broker o code di messaggi, come illustrato nella figura 7-26. Questa opzione può anche essere combinata con il componente Mediator subito prima del gestore comando.

![Diagramma che mostra il flusso di dataflow con una coda di messaggi a disponibilità elevata.](./media/microservice-application-layer-implementation-web-api/add-ha-message-queue.png)

**Figura 7-26**. Uso delle code di messaggi (comunicazione out-of-process e interprocesso) con i comandi CQRS

La pipeline del comando può essere gestita anche da una coda di messaggi a disponibilità elevata per recapitare i comandi al gestore appropriato. L'uso di code di messaggi per accettare i comandi può rendere ancora più complessa la pipeline del comando, perché probabilmente sarà necessario dividere la pipeline in due processi connessi tramite la coda di messaggi esterna. È consigliabile servirsene se è necessario migliorare la scalabilità e le prestazioni in base alla messaggistica asincrona. Si consideri che, nel caso della figura 7-26, il controller inserisce solo il messaggio di comando nella coda e torna indietro. I gestori comando elaborano quindi i messaggi alla velocità stabilita. Ecco un vantaggio considerevole delle code: la coda di messaggi può fungere da buffer nei casi in cui è necessaria l'iperscalabilità, ad esempio per le quotazioni di borsa o altri scenari con un volume elevato di dati in ingresso.

A causa della natura asincrona delle code di messaggi, è tuttavia necessario capire come comunicare all'applicazione client l'esito positivo o negativo dell'elaborazione del comando. Di norma, è preferibile non usare mai i comandi di tipo "fire and forget". Ogni applicazione aziendale deve sapere se un comando è stato elaborato correttamente o quanto meno convalidato e accettato.

Poter rispondere al client dopo la convalida di un messaggio di comando inviato a una coda asincrona accresce quindi la complessità del sistema, rispetto a un'elaborazione di comando in-process che restituisce il risultato dell'operazione dopo l'esecuzione della transazione. Usando le code, potrebbe essere necessario restituire il risultato dell'elaborazione del comando tramite altri messaggi sul risultato dell'operazione, per cui saranno richiesti componenti aggiuntivi e una comunicazione personalizzata nel sistema.

Inoltre, i comandi asincroni sono comandi unidirezionali, che in molti casi potrebbero non essere necessari, come illustrato dall'interessante scambio seguente tra Burtsev Alexey e Greg Young nell'ambito di una [conversazione online](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):

> \[Burtsev Alexey\] Trovo una gran quantità di codice dove le persone usano la gestione dei comandi asincroni o la messaggistica basata su comandi unidirezionali senza alcun motivo per farlo (non devono eseguire operazioni lunghe, non devono eseguire codice asincrono esterno, non devono neppure attraversare il limite dell'applicazione per usare il bus di messaggi). Perché rendono tutto così complesso senza motivo? E finora non ho visto un solo esempio di codice CQRS con il blocco dei gestori comando, anche se funzionerebbe davvero bene nella maggior parte dei casi.
>
> \[Greg Young\] \[...\] un comando asincrono non esiste; si tratta in realtà di un altro evento. Se devo accettare quello che tu mi invii e generare un evento se non sono d'accordo, non mi stai più dicendo di fare qualcosa \[quindi, non è un comando\]. Mi stai dicendo che qualcosa è stato fatto. A prima vista, sembra una piccola differenza, ma le implicazioni sono molte.

I comandi asincroni accrescono considerevolmente la complessità di un sistema, perché non esiste un modo semplice per indicare gli errori. I comandi asincroni non sono quindi consigliati se non quando sono necessari requisiti di ridimensionamento o in casi particolari quando si comunicano i microservizi interni tramite la messaggistica. In tali casi, è necessario progettare un sistema di segnalazione e ripristino separato per gli errori.

Nella versione iniziale di eShopOnContainers è stato deciso di usare l'elaborazione dei comandi sincroni, avviata dalle richieste HTTP e gestita dallo schema Mediator. In questo modo è possibile restituire facilmente l'esito positivo o negativo del processo, come nell'implementazione [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs).

In ogni caso, la decisione deve essere presa in base ai requisiti aziendali dell'applicazione o del microservizio.

## <a name="implement-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a>Implementare la pipeline di elaborazione del comando con uno schema Mediator (MediatR)

Come implementazione di esempio, questa guida propone l'uso della pipeline in-process basata sullo schema Mediator per gestire l'inserimento dei comandi e instradare i comandi, in memoria, ai gestori comando appropriati. La guida propone anche l'applicazione di [comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) per separare le problematiche trasversali.

Per l'implementazione in .NET Core, sono disponibili più librerie open source che implementano lo schema Mediator. Quella usata in questa guida è la libreria open source [MediatR](https://github.com/jbogard/MediatR) (creata da Jimmy Bogard), ma è possibile adottare un altro approccio. MediatR è una libreria semplice di piccole dimensioni che consente di elaborare messaggi in memoria, ad esempio un comando, applicando al contempo elementi Decorator o comportamenti.

L'uso dello schema Mediator consente di ridurre l'accoppiamento e di isolare le problematiche del lavoro richiesto, connettendosi automaticamente nello stesso tempo al gestore che esegue tale lavoro, in questo caso ai gestori comando.

Un altro valido motivo per usare lo schema Mediator è stato illustrato da Jimmy durante la revisione di questa guida:

> Penso che qui valga la pena parlare dei test, che offrono un quadro coerente del comportamento del sistema. Richiesta-in, risposta in uscita. Questo aspetto è molto utile per la creazione di test comportati in modo coerente.

Verrà prima di tutto esaminato un controller API Web di esempio, in cui è effettivamente possibile usare l'oggetto Mediator. Se non si utilizza l'oggetto Mediator, è necessario inserire tutte le dipendenze per quel controller, ad esempio un oggetto logger e altri elementi. Il costruttore sarebbe quindi piuttosto complesso. D'altra parte, se si usa l'oggetto Mediator, il costruttore del controller può essere molto più semplice, con solo alcune dipendenze invece di molte se ne fosse presente una per ogni operazione trasversale, come nell'esempio seguente:

```csharp
public class MyMicroserviceController : Controller
{
    public MyMicroserviceController(IMediator mediator,
                                    IMyMicroserviceQueries microserviceQueries)
    {
        // ...
    }
}
```

Si può osservare che il Mediator fornisce un controller API Web essenziale. Inoltre, nei metodi del controller, il codice per inviare un comando all'oggetto Mediator è praticamente di una sola riga:

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> ExecuteBusinessOperation([FromBody]RunOpCommand
                                                               runOperationCommand)
{
    var commandResult = await _mediator.SendAsync(runOperationCommand);

    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

### <a name="implement-idempotent-commands"></a>Implementare i comandi idempotenti

In **eShopOnContainers** un esempio più avanzato di quello precedente prevede l'invio di un oggetto CreateOrderCommand dal microservizio degli ordini. Tuttavia, poiché il processo di business degli ordini è un po' più complesso e, in questo caso, inizia effettivamente con il microservizio basket, questa azione di invio dell'oggetto CreateOrderCommand viene eseguita da un gestore dell'evento di integrazione denominato [UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) anziché da un semplice controller WebAPI chiamato dall'app client come nell'esempio più semplice precedente.

L'azione di invio del comando a MediatR è però molto simile, come illustrato nel codice seguente.

```csharp
var createOrderCommand = new CreateOrderCommand(eventMsg.Basket.Items,
                                                eventMsg.UserId, eventMsg.City,
                                                eventMsg.Street, eventMsg.State,
                                                eventMsg.Country, eventMsg.ZipCode,
                                                eventMsg.CardNumber,
                                                eventMsg.CardHolderName,
                                                eventMsg.CardExpiration,
                                                eventMsg.CardSecurityNumber,
                                                eventMsg.CardTypeId);

var requestCreateOrder = new IdentifiedCommand<CreateOrderCommand,bool>(createOrderCommand,
                                                                        eventMsg.RequestId);
result = await _mediator.Send(requestCreateOrder);
```

Questo caso è tuttavia anche un po' più avanzato perché vengono anche implementati comandi idempotenti. Il processo CreateOrderCommand dovrebbe essere idempotente, quindi, se per qualsiasi motivo lo stesso messaggio viene duplicato in rete, ad esempio a causa di più tentativi, lo stesso ordine aziendale verrà elaborato più di una volta.

Per l'implementazione viene eseguito il wrapping del comando aziendale (in questo caso CreateOrderCommand), che viene quindi incorporato in un generico IdentifiedCommand di cui viene tenuta traccia usando un ID di ogni messaggio in arrivo dalla rete che deve essere idempotente.

Nel codice seguente è possibile osservare che IdentifiedCommand è semplicemente un oggetto DTO con un ID e l'oggetto comando aziendale di cui viene eseguito il wrapping.

```csharp
public class IdentifiedCommand<T, R> : IRequest<R>
    where T : IRequest<R>
{
    public T Command { get; }
    public Guid Id { get; }
    public IdentifiedCommand(T command, Guid id)
    {
        Command = command;
        Id = id;
    }
}
```

Quindi l'elemento CommandHandler per l'elemento IdentifiedCommand denominato [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) fondamentalmente controllerà se l'ID immesso come parte del messaggio esiste già in una tabella. Se esiste già, tale comando non verrà elaborato di nuovo, quindi si comporta come un comando idempotente. Tale codice dell'infrastruttura viene eseguito dalla chiamata al metodo `_requestManager.ExistAsync` seguente.

```csharp
// IdentifiedCommandHandler.cs
public class IdentifiedCommandHandler<T, R> :
                                   IAsyncRequestHandler<IdentifiedCommand<T, R>, R>
                                   where T : IRequest<R>
{
    private readonly IMediator _mediator;
    private readonly IRequestManager _requestManager;

    public IdentifiedCommandHandler(IMediator mediator,
                                    IRequestManager requestManager)
    {
        _mediator = mediator;
        _requestManager = requestManager;
    }

    protected virtual R CreateResultForDuplicateRequest()
    {
        return default(R);
    }

    public async Task<R> Handle(IdentifiedCommand<T, R> message)
    {
        var alreadyExists = await _requestManager.ExistAsync(message.Id);
        if (alreadyExists)
        {
            return CreateResultForDuplicateRequest();
        }
        else
        {
            await _requestManager.CreateRequestForCommandAsync<T>(message.Id);

            // Send the embedded business command to mediator
            // so it runs its related CommandHandler
            var result = await _mediator.Send(message.Command);

            return result;
        }
    }
}
```

Poiché IdentifiedCommand funge da busta del comando aziendale, quando il comando aziendale deve essere elaborato perché non è un ID ripetuto, prende tale comando aziendale interno e lo invia di nuovo al Mediator, come nell'ultima parte del codice illustrato sopra quando si esegue `_mediator.Send(message.Command)`, da [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs).

Durante tale operazione, collegherà ed eseguirà il gestore comando aziendale, in questo caso [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs), che sta eseguendo le transazioni nel database degli ordini, come illustrato nel codice seguente.

```csharp
// CreateOrderCommandHandler.cs
public class CreateOrderCommandHandler
                                   : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator,
                                     IOrderRepository orderRepository,
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ??
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ??
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ??
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Add/Update the Buyer AggregateRoot
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,
                              message.CardNumber, message.CardSecurityNumber,
                              message.CardHolderName, message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

### <a name="register-the-types-used-by-mediatr"></a>Registrare i tipi usati da MediatR

Per consentire a MediatR di conoscere le classi di gestori comando, è necessario registrare le classi Mediator e le classi di gestori comando nel contenitore IoC. Per impostazione predefinita, MediatR usa Autofac come contenitore IoC, ma è anche possibile usare il contenitore IoC ASP.NET Core predefinito o qualsiasi altro contenitore supportato da MediatR.

Il codice seguente illustra come registrare i tipi e i comandi di Mediator quando si usano i moduli di Autofac.

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IAsyncRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IAsyncRequestHandler<,>));
        // Other types registration
        //...
    }
}
```

È qui che "avviene la vera e propria magia" con MediatR.

Poiché ogni gestore comandi implementa l'interfaccia `IAsyncRequestHandler<T>` generica, quando si registrano gli assembly, il codice registra con `RegisteredAssemblyTypes` tutti i tipi contrassegnati come `IAsyncRequestHandler` mentre correla gli elementi `CommandHandlers` con i rispettivi `Commands`, grazie alla relazione stabilita nella classe `CommandHandler`, come nell'esempio seguente:

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

Questo è il codice che correla i comandi con i gestori comando. Il gestore è solo una semplice classe, ma eredita da `RequestHandler<T>`, dove T è il tipo di comando, e MediatR verifica che venga richiamato con il payload corretto (il comando).

## <a name="apply-cross-cutting-concerns-when-processing-commands-with-the-behaviors-in-mediatr"></a>Applicare problematiche trasversali quando si elaborano i comandi con i comportamenti in MediatR

Un aspetto da considerare è la possibilità di applicare problematiche trasversali alla pipeline Mediator. È anche possibile osservare alla fine del codice del modulo di registrazione di Autofac come registra un tipo di comportamento, in particolare una classe LoggingBehavior personalizzata e una classe ValidatorBehavior, ma è anche possibile aggiungere altri comportamenti personalizzati.

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IAsyncRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IAsyncRequestHandler<,>));
        // Other types registration
        //...
        builder.RegisterGeneric(typeof(LoggingBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
        builder.RegisterGeneric(typeof(ValidatorBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
    }
}
```

Tale classe [LoggingBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) può essere implementata come il codice seguente, che registra le informazioni sul gestore comando che viene eseguito e l'esito positivo o negativo.

```csharp
public class LoggingBehavior<TRequest, TResponse>
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly ILogger<LoggingBehavior<TRequest, TResponse>> _logger;
    public LoggingBehavior(ILogger<LoggingBehavior<TRequest, TResponse>> logger) =>
                                                                  _logger = logger;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        _logger.LogInformation($"Handling {typeof(TRequest).Name}");
        var response = await next();
        _logger.LogInformation($"Handled {typeof(TResponse).Name}");
        return response;
    }
}
```

Semplicemente implementando questa classe di comportamento e registrandola nella pipeline (nell'oggetto MediatorModule di cui sopra), tutti i comandi elaborati con MediatR registreranno le informazioni sull'esecuzione.

Il microservizio degli ordini di eShopOnContainers applica anche un secondo comportamento per le convalide di base, la classe [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs) che si basa sulla libreria [FluentValidation](https://github.com/JeremySkinner/FluentValidation), come illustrato nel codice seguente:

```csharp
public class ValidatorBehavior<TRequest, TResponse>
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly IValidator<TRequest>[] _validators;
    public ValidatorBehavior(IValidator<TRequest>[] validators) =>
                                                         _validators = validators;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        var failures = _validators
            .Select(v => v.Validate(request))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();

        if (failures.Any())
        {
            throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                        new ValidationException("Validation exception", failures));
        }

        var response = await next();
        return response;
    }
}
```

In questo caso il comportamento genera un'eccezione se la convalida non riesce, ma è anche possibile restituire un oggetto risultato che contiene il risultato del comando se ha avuto esito positivo o i messaggi di convalida nel caso contrario. Questo probabilmente semplificherebbe la visualizzazione dei risultati della convalida per l'utente.

Quindi in base alla libreria [FluentValidation](https://github.com/JeremySkinner/FluentValidation), è stata creata una convalida per i dati passati con CreateOrderCommand, come nel codice seguente:

```csharp
public class CreateOrderCommandValidator : AbstractValidator<CreateOrderCommand>
{
    public CreateOrderCommandValidator()
    {
        RuleFor(command => command.City).NotEmpty();
        RuleFor(command => command.Street).NotEmpty();
        RuleFor(command => command.State).NotEmpty();
        RuleFor(command => command.Country).NotEmpty();
        RuleFor(command => command.ZipCode).NotEmpty();
        RuleFor(command => command.CardNumber).NotEmpty().Length(12, 19);
        RuleFor(command => command.CardHolderName).NotEmpty();
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).Must(ContainOrderItems).WithMessage("No order items found");
    }

    private bool BeValidExpirationDate(DateTime dateTime)
    {
        return dateTime >= DateTime.UtcNow;
    }

    private bool ContainOrderItems(IEnumerable<OrderItemDTO> orderItems)
    {
        return orderItems.Any();
    }
}

```

È possibile creare convalide aggiuntive. È un modo molto essenziale e accurato di implementare le convalide dei comandi.

In modo simile, è possibile implementare altri comportamenti per ulteriori aspetti o problematiche trasversali che si vuole applicare ai comandi quando li si gestisce.

#### <a name="additional-resources"></a>Risorse aggiuntive

##### <a name="the-mediator-pattern"></a>Schema Mediator

- **Schema Mediator** \
  [https://en.wikipedia.org/wiki/Mediator\_pattern](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a>Schema Decorator

- **Schema Decorator** \
  [https://en.wikipedia.org/wiki/Decorator\_pattern](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a>MediatR (Jimmy Bogard)

- **MediatR.** Repository GitHub. \
  <https://github.com/jbogard/MediatR>

- **CQRS with MediatR and AutoMapper (CQRS con MediatR e AutoMapper)**  \
  <https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/>

- **Put your controllers on a diet: POSTs and commands.** (Mettere a dieta i controller: POST e comandi) \
  <https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/>

- **Tackling cross-cutting concerns with a mediator pipeline (Affrontare i problemi di montaggio incrociato con una pipeline MediatR)**  \
  <https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/>

- **CQRS and REST: the perfect match (CQRS e REST: la coppia perfetta)**  \
  <https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/>

- **MediatR Pipeline Examples** \ (Esempi di pipeline MediatR)
  <https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/>

- **Vertical Slice Test Fixtures for MediatR and ASP.NET Core** \ (Fixture di test per sezioni verticali per MediatR e ASP.NET Core)
  <https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>

- **MediatR Extensions for Microsoft Dependency Injection Released (Rilascio delle estensioni MediatR per l'inserimento di dipendenze Microsoft)**  \
  <https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/>

##### <a name="fluent-validation"></a>Convalida Fuent

- **Jeremy Skinner. Alla fluentvalidation.** Repository GitHub. \
  <https://github.com/JeremySkinner/FluentValidation>

> [!div class="step-by-step"]
> [Precedente](microservice-application-layer-web-api-design.md)
> [Successivo](../implement-resilient-applications/index.md)
