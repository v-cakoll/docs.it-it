---
title: Implementa il livello di applicazione microservizio mediante l'API Web
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementa il livello di applicazione microservizio mediante l'API Web
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: d505a2561ae9b8dee05e803fd639387b63b28b70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a>Implementa il livello di applicazione microservizio mediante l'API Web

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a>Utilizzo di inserimento di dipendenze per inserire oggetti infrastruttura nel livello dell'applicazione

Come accennato in precedenza, il livello di applicazione può essere implementato come parte dell'elemento a cui si sta creando, ad esempio come all'interno di un progetto di API Web o un progetto di applicazione web MVC. Nel caso microservizio compilata con ASP.NET Core, il livello dell'applicazione sarà in genere la libreria di API Web. Se si desidera separare sviluppi futuri da ASP.NET Core (l'infrastruttura e i controller) dal codice di livello applicazione personalizzata, è anche possibile posizionare il livello di applicazione in una libreria di classi separato, ma che è facoltativo.

Ad esempio, il codice del livello applicazione di microservizio l'ordinamento viene implementato direttamente come parte di **Ordering.API** progetto (un'API Web di ASP.NET Core), come illustrato nella figura 9-19.

![](./media/image20.png)

**Figura 9-19**. Il livello dell'applicazione nel progetto Ordering.API ASP.NET Core Web API

ASP.NET Core include un semplice [incorporato contenitore IoC](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (rappresentato dall'interfaccia IServiceProvider) che supporta inserimento del costruttore per impostazione predefinita e ASP.NET rende disponibili tramite DI determinati servizi. ASP.NET Core viene utilizzato il termine *servizio* per i tipi di registrazione che verranno inseriti tramite DI. Configurare i servizi del contenitore predefinito nel metodo ConfigureServices nella classe di avvio dell'applicazione. Le dipendenze vengono implementate nei servizi che è necessario un tipo.

In genere, si desidera inserire le dipendenze che implementano oggetti dell'infrastruttura. Una dipendenza di inserire in genere è un repository. Ma è possibile inserire qualsiasi altra dipendenza di infrastruttura che è possibile. Per le implementazioni più semplici, si potrebbe inserire direttamente l'oggetto modello di unità di lavoro (l'oggetto DbContext EF), poiché l'elemento DBContext è anche l'implementazione degli oggetti di persistenza di infrastruttura.

Nell'esempio seguente, è possibile visualizzare la modalità .NET Core è inserendo gli oggetti necessari repository tramite il costruttore. La classe è un gestore del comando, che verranno illustrate nella sezione successiva.

```csharp
// Sample command handler
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;

    // Constructor where Dependencies are injected
    public CreateOrderCommandHandler(IOrderRepository orderRepository)
    {
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // ... Additional code
        //
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
            message.Country, message.ZipCode);
        var order = new Order(address, message.CardTypeId, message.CardNumber,
            message.CardSecurityNumber,
            message.CardHolderName,
            message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        //Persist the Order through the Repository
        _orderRepository.Add(order);
        var result = await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
        return result > 0;
    }
}
```

La classe utilizza i repository inseriti per eseguire la transazione e rendere permanenti le modifiche di stato. Non è importante se tale classe è un gestore del comando, un metodo del controller API Web di ASP.NET Core, o una [DDD applicazione servizio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/). In definitiva è una classe semplice che utilizza repository, entità di dominio e il coordinamento di altre applicazioni in modo simile a un gestore del comando. Funzionamento di Injection dipendenza in base allo stesso modo per tutte le classi indicate, come illustrato nell'esempio DI utilizzo del costruttore.

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a>Registrazione di tipi di implementazione di dipendenza e interfacce o astrazioni

Prima di utilizzare gli oggetti inseriti tramite costruttori, è necessario sapere dove registrare le interfacce e classi che producono gli oggetti inseriti in classi e DI applicazione. (Ad esempio DI in base al costruttore come illustrato in precedenza).

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a>Usa il contenitore IoC predefinito fornito da ASP.NET Core

Quando si usa il contenitore IoC predefinito fornito da ASP.NET Core, registrare i tipi che si desidera inserire nel metodo ConfigureServices nel file Startup.cs, come illustrato nel codice seguente:

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

Il modello più comune quando la registrazione di tipi in un contenitore IoC consiste nel registrare una coppia di tipi, ovvero un'interfaccia e la relativa classe di implementazione correlata. Quindi quando si richiede un oggetto dal contenitore IoC tramite qualsiasi altro costruttore, richiedere un oggetto di un determinato tipo di interfaccia. Nell'esempio precedente, ad esempio, l'ultima riga indica che quando uno dei costruttori del presentano una dipendenza da IMyCustomRepository (interfaccia o astrazione), il contenitore IoC inserirà un'istanza dell'implementazione MyCustomSQLServerRepository classe.

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a>Utilizzo della libreria Scrutor per la registrazione automatica di tipi

Quando si utilizza DI .NET Core, si potrebbe voler essere in grado di analizzare un assembly e registrare automaticamente i tipi per convenzione. Questa funzionalità non è attualmente disponibile in ASP.NET Core. Tuttavia, è possibile utilizzare il [Scrutor](https://github.com/khellang/Scrutor) libreria a tale scopo. Questo approccio è utile quando si dispone di decine di tipi che devono essere registrati nel contenitore di inversione di controllo.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Re Matthew. Registrazione dei servizi con Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)

<!-- -->

-   **Kristian Hellang. Scrutor.** Repository di GitHub.
    [*https://github.com/khellang/Scrutor*](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a>Utilizzo di Autofac come un contenitore IoC

È possibile utilizzare altri contenitori IoC e inserirli nella pipeline ASP.NET di base, come l'ordinamento microservizio in eShopOnContainers, che usa [Autofac](https://autofac.org/). Quando si utilizza Autofac in genere necessario registrare i tipi tramite moduli, che consentono di dividere i tipi di registrazione tra più file in base alla posizione dei tipi, esattamente come è possibile includere i tipi di applicazioni distribuiti tra più librerie di classi.

Ad esempio, ecco la [modulo applicazione Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) per il [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) progetto con i tipi a cui si desidera inserire.

```csharp
public class ApplicationModule
    :Autofac.Module
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

I concetti e il processo di registrazione sono molto simili al modo in cui che è possibile registrare i tipi con il contenitore di iOS ASP.NET Core incorporato, ma la sintassi quando si utilizza Autofac è leggermente diversa.

Nell'esempio di codice, l'astrazione IOrderRepository è registrato con la classe di implementazione OrderRepository. Ciò significa che ogni volta che una dipendenza tramite l'interfaccia o IOrderRepository astrazione dichiara un costruttore, il contenitore IoC inserirà un'istanza della classe OrderRepository.

Il tipo di ambito istanza determina come un'istanza condivisa tra le richieste per lo stesso servizio o dipendenze. Quando viene effettuata una richiesta per una dipendenza, il contenitore IoC può restituire le operazioni seguenti:

-   Una singola istanza per ogni ambito di durata (a cui il contenitore di ASP.NET Core IoC *con ambito*).

-   Una nuova istanza per ogni dipendenza (a cui il contenitore di ASP.NET Core IoC *temporanei*).

-   Una singola istanza condivisa tra tutti gli oggetti utilizzando il contenitore IoC (a cui il contenitore di ASP.NET Core IoC *singleton*).

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Introduzione a Dependency Injection in ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)

-   **Autofac.** Documentazione ufficiale.
    [*http://docs.autofac.org/en/Latest/*](http://docs.autofac.org/en/latest/)

-   **Cesar de la Torre. Confronto tra la durata di servizio contenitore di ASP.NET Core IoC con ambiti di istanza contenitore IoC Autofac**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-core-IoC-Service-Life-Times-and-autofac-IoC-Instance-Scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="implementing-the-command-and-command-handler-patterns"></a>Implementare i modelli di comando e il gestore del comando

Nell'esempio DI-a-costruttore illustrato nella sezione precedente, il contenitore IoC stato inserendo repository tramite un costruttore in una classe. Ma esattamente in cui sono stati sono inserite? In un'API Web semplice (ad esempio, microservizio catalogo in eShopOnContainers), invece possibile inserire tali a livello di controller MVC, in un costruttore di controller. Tuttavia, nel codice iniziale di questa sezione (il [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) classe dal servizio Ordering.API in eShopOnContainers), l'inserimento di dipendenze viene eseguita tramite il costruttore di un particolare comando gestore. Segnalare il problema viene illustrato un gestore di comandi è e motivi per cui si desidera utilizzarlo.

Il modello di comando è intrinsecamente correlato al modello CQRS che è stata introdotta in precedenza in questa Guida. CQRS ha due lati. La prima area è una query, tramite query semplificata con la [Dapper](https://github.com/StackExchange/dapper-dot-net) ORM micro, che è stata illustrata in precedenza. La seconda area è comandi, ovvero il punto di partenza per le transazioni e il canale di input all'esterno del servizio.

Come illustrato nella figura 9-20, il modello è basato sull'accetta comandi dal lato client, l'elaborazione in base alle regole del modello di dominio e infine la persistenza degli Stati con transazioni.

![](./media/image21.png)

**Figura 9-20**. Visualizzazione di alto livello dei comandi "transazionale lato" in un modello CQRS

### <a name="the-command-class"></a>La classe di comando

Un comando è una richiesta per il sistema eseguire un'azione che modifica lo stato del sistema. I comandi sono imperativi e devono essere elaborati una sola volta.

Poiché i comandi sono esigenze, in genere sono denominate con un verbo all'interno di uno stile imperativo (ad esempio, "Crea" o "aggiornamento") e potrebbero includere il tipo di aggregazione, ad esempio CreateOrderCommand. A differenza di un evento, un comando non è un fatto trascorsa; è solo una richiesta e pertanto non può essere rifiutata.

Quando il gestore di processi è indirizzare un'aggregazione per eseguire un'azione, i comandi possono provenire dall'interfaccia utente in seguito a un utente che ha avviato una richiesta o da un gestore di processi.

Una caratteristica importante di un comando è che deve essere elaborato una sola volta da un singolo ricevitore. In questo modo un comando è una singola azione o una transazione da eseguire nell'applicazione. Ad esempio, il comando di creazione dell'ordine stesso non deve essere elaborato più volte. Si tratta di un'importante differenza tra i comandi ed eventi. Gli eventi possono essere elaborati più volte, in quanto molti sistemi o microservizi potrebbero essere interessati nell'evento.

Inoltre, è importante che un comando elaborato solo una volta nel caso in cui il comando non è idempotente. Un comando è idempotente, se può essere eseguita più volte senza modificare il risultato, oppure a causa della natura del comando, a causa del modo in cui che il sistema gestisce il comando.

È buona norma dei comandi e aggiorna idempotente quando avrebbe senso in regole di business del proprio dominio e invarianti. Per utilizzare lo stesso esempio, se per qualsiasi motivo (logica di ripetizione dei tentativi di attacco, e così via) lo stesso comando CreateOrder raggiunge il sistema più volte, ad esempio, deve essere in grado di identificarlo e assicurarsi di non creare più ordini. A tale scopo, è necessario collegare un tipo di identità nelle operazioni e identificare se il comando o l'aggiornamento è già stato elaborato.

Si invia un comando a un singolo destinatario; non pubblica di un comando. La pubblicazione è per gli eventi di integrazione che lo stato di un fatto, che un elemento si è verificato e potrebbe essere interessante per i ricevitori di eventi. Nel caso di eventi, il server di pubblicazione non ha dubbi sui ricevitori di ottenere l'evento o lo scopo. Questi eventi di integrazione con un'altra storia già introdotta nelle sezioni precedenti.

Un comando è implementato con una classe che contiene i campi dati o le raccolte con tutte le informazioni necessarie per eseguire il comando. Un comando è un tipo speciale di dati trasferire oggetti (DTO), che viene usato in modo specifico per richiedere modifiche o le transazioni. Il comando stesso si basa sul esattamente le informazioni necessarie per elaborare il comando e nient'altro.

Nell'esempio seguente viene illustrata la classe CreateOrderCommand semplificata. Si tratta di un comando non modificabile che viene utilizzato per l'ordinamento microservizio in eShopOnContainers.

```csharp
// DDD and CQRS patterns comment
// Note that it is recommended that yuo implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://msdn.microsoft.com/en-us/library/bb383979.aspx
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

    public CreateOrderCommand(List<OrderItemDTO> orderItems, string city,
        string street,
        string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = orderItems;
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

In pratica, la classe di comando contiene tutti i dati che necessari per l'esecuzione di una transazione di business utilizzando gli oggetti modello di dominio. Pertanto, i comandi sono semplicemente strutture di dati che contengono dati di sola lettura e alcun comportamento. Il nome del comando indica lo scopo. In molti linguaggi come C\#, i comandi sono rappresentati come classi, ma non sono classi true in senso reale orientata agli oggetti.

Come una caratteristica aggiuntiva, i comandi non sono modificabili, perché l'utilizzo previsto è che vengono elaborati direttamente dal modello di dominio. Non devono cambiare durante il loro ciclo di vita previsto. In C\# (classe), immutabilità può essere ottenuta dalla mancanza di qualsiasi Setter o altri metodi che modificano lo stato interno.

Ad esempio, è probabilmente simile in termini di dati per l'ordine in cui che si desidera creare la classe di comando per la creazione di un ordine, ma probabile che non richiedono gli stessi attributi. Ad esempio, CreateOrderCommand non dispone di un ID ordine, perché l'ordine non è ancora stato creato.

Molte classi di comando possono essere semplice, che richiede solo pochi campi su uno stato che deve essere modificato. Che è il caso se si desidera modificare solo lo stato di un ordine da "in corso" a "pagamento" o "consegna" utilizzando un comando simile al seguente:

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

Alcuni sviluppatori apportare separato dal loro DTO comando i relativi oggetti di richiesta dell'interfaccia utente, ma che solo una questione di preferenze. È una separazione noiosa con un valore non aggiunto e gli oggetti sono quasi esattamente la stessa forma. Ad esempio, in eShopOnContainers, i comandi disponibili direttamente dal lato client.

### <a name="the-command-handler-class"></a>La classe del gestore del comando

È necessario implementare una classe del gestore di comandi specifici per ogni comando. Che è il funzionamento il modello in modo in cui si userà l'oggetto comando, gli oggetti di dominio e oggetti di repository dell'infrastruttura. Il gestore del comando è in realtà il cuore del livello dell'applicazione in termini di CQRS e DDD. Tuttavia, la logica di dominio deve essere contenuta all'interno delle classi di dominio, entro le radici di aggregazione (entità radice), le entità figlio, o [servizi di dominio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), ma non all'interno del gestore di comando, ovvero una classe dall'applicazione livello.

Un gestore del comando riceve un comando e ottiene un risultato dall'aggregazione utilizzata. Il risultato deve essere corretta esecuzione del comando o un'eccezione. In caso di eccezione, lo stato del sistema deve essere unchanged.

In genere, il gestore del comando esegue i passaggi seguenti:

-   Riceve l'oggetto comando, ad esempio un DTO (dal [mediatore](https://en.wikipedia.org/wiki/Mediator_pattern) o un altro oggetto infrastruttura).

-   Convalida che il comando è valido (se non viene convalidata da mediatore).

-   Crea l'istanza radice di aggregazione di destinazione del comando corrente.

-   Il metodo viene eseguito nell'istanza principale di aggregazione, ottenere i dati richiesti dal comando.

-   Il nuovo stato dell'aggregato al relativo database correlati persiste. L'ultima operazione è la transazione.

In genere, un gestore del comando riguarda una singola funzione di aggregazione dovute alla relativa radice di aggregazione (entità radice). Se più funzioni di aggregazione dovrebbe essere interessate dalla ricezione di un unico comando, è possibile utilizzare gli eventi di dominio per stati o le azioni si propagano tra più funzioni di aggregazione

Ecco l'aspetto importante è che, durante l'elaborazione di un comando, tutta la logica di dominio deve essere all'interno del modello di dominio (le funzioni di aggregazione), completamente incapsulato e pronto per gli unit test. Il gestore del comando viene utilizzato solo come un modo per ottenere il modello di dominio dal database e come il passaggio finale, per indicare il livello di infrastruttura (repository) per rendere permanenti le modifiche quando viene modificato il modello. Il vantaggio di questo approccio è che è possibile eseguire il refactoring di logica di dominio in un modello di dominio isolato, incapsulato completamente, RTF, comportamento senza modificare il codice dell'applicazione o i livelli di infrastruttura, che costituiscono il livello di infrastruttura (gestori di comandi, API Web, repository e così via).

Quando i gestori di comandi ottengono complessi, con una quantità eccessiva logica, che può essere un odore di codice. Rivedere e se la logica di dominio, il refactoring del codice per spostare il comportamento di tale dominio ai metodi degli oggetti di dominio (l'entità di primo livello e figlio aggregazione).

Ad esempio di una classe di gestore del comando, il codice seguente illustra la stessa classe CreateOrderCommandHandler che si verifica all'inizio di questo capitolo. In questo caso è stato evidenziato il metodo di Handle e le operazioni con il dominio modello a oggetti o funzioni di aggregazione.

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IBuyerRepository _buyerRepository;
    private readonly IOrderRepository _orderRepository;

    public CreateOrderCommandHandler(IBuyerRepository buyerRepository,
        IOrderRepository orderRepository)
    {
        if (buyerRepository == null)
        {
            throw new ArgumentNullException(nameof(buyerRepository));
        }
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }

        _buyerRepository = buyerRepository;
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // Additional code ...
        //
        // Create the Order aggregate root
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var order = new Order(buyer.Id, payment.Id,
            new Address(message.Street,
            message.City, message.State,
            message.Country, message.ZipCode));

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        // Persist the Order through the aggregate's repository
        _orderRepository.Add(order);
        return await _orderRepository.UnitOfWork.SaveChangesAsync();
    }
}
```

Questi sono necessari passaggi aggiuntivi che debba eseguire un gestore del comando:

-   Utilizzare i dati del comando per funzionare con metodi di aggregazione radice e il comportamento.

-   Internamente all'interno di oggetti di dominio, generare eventi di dominio durante la transazione viene eseguita, ma che è trasparente da un punto di vista di comando gestore.

-   Se il risultato dell'operazione di aggregazione ha esito positivo e al termine della transazione, generare il gestore del comando integrazione degli eventi. (Questi potrebbe anche essere generati dalle classi di infrastruttura come repository.)

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Contrassegno Seemann. I limiti, le applicazioni sono orientata agli oggetti non**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries, orientata ai servizi ApplicationsareNotObject /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)

-   **I comandi ed eventi**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)

-   **Che cosa è un gestore del comando? ** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)

-   **Jimmy Bogard. Modelli di comandi dominio – gestori**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)

-   **Jimmy Bogard. Modelli di comandi di dominio: convalida**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a>La pipeline di processo del comando: come attivare un gestore del comando

Domanda successiva viene illustrato come richiamare un gestore del comando. È possibile chiamarlo manualmente da ogni controller di ASP.NET Core correlati. Tuttavia, che approccio potrebbe essere troppo ridotto e non è ideale.

Le altre due opzioni principali, che sono le opzioni consigliate, sono:

-   Tramite un elemento di modello mediatore in memoria.

-   Con una coda di messaggi asincroni, tra i controller e i gestori.

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a>Usando il modello di mediatore (in memoria) nella pipeline dei comandi

Come illustrato nella figura 9-21, in un approccio CQRS si utilizza un mediatore intelligente, simile a un bus in memoria, ovvero abbastanza per reindirizzare al gestore del comando corretto in base al tipo del comando o DTO ricevuti. Le frecce nere singole tra i componenti rappresentano le dipendenze tra oggetti (in molti casi, inseriti tramite DI) con le relative interazioni.

![](./media/image22.png)

**Figura 9-21**. Usando il modello mediatore nel processo in un singolo microservizio CQRS

Il motivo che usa il modello mediatore significativo è che in applicazioni aziendali, le richieste di elaborazione possono diventare complicate. Si desidera essere in grado di aggiungere un numero di aprire delle problematiche trasversali quali registrazione, le convalide, controllo e sicurezza. In questi casi, è possibile basarsi su una pipeline mediatore (vedere [modello mediatore](https://en.wikipedia.org/wiki/Mediator_pattern)) per fornire un mezzo per questi comportamenti aggiuntivi o i problemi di montaggio incrociato.

Mediatore è un oggetto che incapsula il "come" di questo processo: coordina l'esecuzione in base allo stato, la modalità di un gestore del comando viene richiamata o il payload fornire al gestore. Con un componente mediatore è possibile applicare a montaggio incrociato problemi in modo centralizzato e trasparente applicando gli elementi Decorator (o [pipeline comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) dal mediatore v3). (Per ulteriori informazioni, vedere il [modello di espressione Decorator](https://en.wikipedia.org/wiki/Decorator_pattern).)

Gli elementi Decorator e comportamenti sono simili a [aspetto Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), applicato a una pipeline di processo specifico gestita dal componente mediatore solo. Gli aspetti AOP che implementano i problemi di montaggio incrociato vengono applicati in base *weavers aspetto* inseriti in fase di compilazione o in base a intercettazione di chiamata di oggetto. Entrambi gli approcci di AOP tipici vengono talvolta denominati funzionano "come chiave," perché non è facile capire come AOP esegue il proprio lavoro. Quando si lavora con gravi problemi o i bug, AOP può essere difficile eseguire il debug. D'altra parte, questi elementi Decorator e comportamenti sono esplicita e applicate solo nel contesto di mediatore, pertanto il debug è molto più semplice e prevedibile.

Ad esempio, in eShopOnContainers ordinamento microservizio, sono implementati due elementi Decorator di esempio, un [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) classe e un [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) classe. Implementazione dell'elemento decorator è illustrato nella sezione successiva. Si noti che in una versione futura, eShopOnContainers verrà eseguita la migrazione a [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) e spostare [comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) anziché gli elementi Decorator.

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a>Utilizzo delle code di messaggi (out-of-process) nella pipeline del comando

Un'altra opzione consiste nell'utilizzare messaggi asincroni in base alle istanze di Service Broker o code di messaggi, come illustrato nella figura 9 a 22. Tale opzione, inoltre, può essere combinate con il componente mediatore immediatamente prima il gestore del comando.

![](./media/image23.png)

**Figura 9 a 22**. Usare le code di messaggi (fuori processo e comunicazione interprocesso) con i comandi CQRS

Tramite messaggio code per accettare che i comandi possono ulteriormente complicano la pipeline del comando, perché sarà probabilmente necessario suddividere la pipeline in due processi connessi tramite la coda di messaggi esterni. Ancora, e deve essere utilizzato se è necessario sono migliorate, scalabilità e prestazioni in base alla messaggistica asincrona. Tenere presente che nel caso di figura 9 a 22, il controller appena viene inviato il messaggio di comando in coda e restituisce. I gestori di comando quindi elaborano i messaggi in base alle proprie esigenze. Vale a dire un notevole vantaggio delle code, ovvero la coda di messaggi può fungere da un buffer in casi quando la scalabilità hyper è necessaria, ad esempio stock o qualsiasi altro scenario con un elevato volume di dati in entrata.

Tuttavia, a causa della natura asincrona delle code di messaggi, è necessario capire come comunicare con l'applicazione client sull'esito positivo o negativo del processo del comando. Di norma, non utilizzare mai i comandi "fire and forget". Ogni applicazione di business deve sapere se un comando è stato elaborato correttamente, o almeno convalidato e accettato.

Di conseguenza, la possibilità di rispondere al client dopo la convalida di un messaggio di comando che è stato inviato a una coda asincrona aggiunge complessità al sistema, rispetto a un processo del comando in-process che restituisce il risultato dell'operazione dopo l'esecuzione della transazione. Utilizzo delle code, potrebbe essere necessario restituire il risultato del processo di comando tramite altri messaggi, risultato dell'operazione che richiede i componenti aggiuntivi e personalizzate di comunicazione del sistema.

Inoltre, i comandi di async sono comandi unidirezionali, che, in molti casi, potrebbero non essere necessaria, come è illustrato nella seguente interessano scambio tra Burtsev Alexey e Greg Young in un [conversazione online](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):

\[Burtsev Alexey\] è possibile individuare una grande quantità di codice in cui utenti utilizzano la gestione dei comandi asincrona o un comando unidirezionale messaggistica senza alcun motivo per eseguire questa operazione (non sta eseguendo un'operazione lunga, codice asincrono esterni non sono in esecuzione, non si incrociano anche applicazione limite di bus di messaggi). Motivo per cui introducono questa complessità superflua? E, in realtà, non ho visto un esempio di codice con il blocco fino a questo punto, i gestori di comandi CQRS se funziona bene nella maggior parte dei casi.

\[Greg Young\] \[... \] non esiste un comando asincrono, è effettivamente un altro evento. Se è necessario accettare ciò che si invia e genera un evento se non sono d'accordo, non è più si informa per eseguire un'operazione. È è informa che un'operazione è stata completata. Questa opzione sembri una leggera differenza inizialmente, ma presenta implicazioni molti.

Comandi asincroni aumentare notevolmente la complessità di un sistema, poiché non esiste un modo semplice per indicare gli errori. Di conseguenza, i comandi asincroni non sono consigliati diverso da quando sono necessari requisiti di scalabilità o, in casi speciali durante la comunicazione di microservizi interno tramite messaggistica. In questi casi, è necessario progettare un sistema di reporting e il ripristino separato per gli errori.

Nella versione iniziale di eShopOnContainers, si è deciso di utilizzare l'elaborazione di comandi sincroni, avviata da richieste HTTP e basato su questo modello mediatore. Che consente di restituire l'esito positivo o negativo del processo, come in facilmente il [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementazione.

In ogni caso, deve trattarsi di una decisione in base ai requisiti di business dell'applicazione o del microservizio.

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a>Implementazione della pipeline di processo del comando con un criterio di mediatore (MediatR)

Come un'implementazione di esempio, questa guida vengono proposte tramite la pipeline in-process in base al modello mediatore per l'inserimento di comando di unità e routing, in memoria, per i gestori di comando corretto. La guida propone inoltre l'applicazione gli elementi Decorator o [comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) per separare le problematiche a montaggio incrociato.

Per l'implementazione di .NET Core, sono disponibili più librerie di open source disponibili che implementano il modello mediatore. La libreria utilizzata in questa guida è il [MediatR](https://github.com/jbogard/MediatR) libreria open source (creato dal Jimmy Bogard), ma è possibile utilizzare un altro approccio. MediatR è una libreria di piccola e semplice che consente di elaborare messaggi in memoria come un comando, durante l'applicazione di comportamenti o gli elementi Decorator.

Usando il modello mediatore consente di ridurre l'accoppiamento e per isolare i problemi del lavoro richiesto, durante la connessione automatica al gestore che esegue il lavoro, in questo caso, per i gestori di comando.

Un altro buon motivo per utilizzare il modello mediatore stato descritto da Jimmy Bogard durante la revisione di questa guida:

Credo che potrebbe essere utile citare test qui: fornisce una finestra coerenza nice esplicitamente il comportamento del sistema. Richiesta e risposta in uscita. È stata trovata l'aspetto molto utili nella creazione di un comportamento coerente di test.

In primo luogo, possiamo osservare per il codice del controller in cui è in realtà utilizzerebbe l'oggetto mediatore. Se non si utilizza l'oggetto mediatore, è necessario inserire tutte le dipendenze per tale controller, ad esempio un oggetto logger e altri utenti. Pertanto, il costruttore sarà piuttosto complesso. D'altra parte, se si utilizza l'oggetto mediatore, il costruttore del controller può essere molto più semplice, con pochi dipendenze anziché numerose dipendenze che si avrebbe se fosse uno per ogni operazione di montaggio incrociato, come nell'esempio seguente:

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

È possibile vedere che mediatore fornisce un costruttore di controller API Web pulito e pulito. Inoltre, all'interno dei metodi di controller, il codice per inviare un comando per l'oggetto mediatore è quasi una riga:

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> CreateOrder([FromBody]CreateOrderCommand
    createOrderCommand)
{
    var commandResult = await _mediator.SendAsync(createOrderCommand);
    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

Affinché MediatR da tenere presenti le classi del gestore del comando, è necessario registrare le classi mediatore e le classi di gestore del comando nel contenitore di inversione di controllo. Per impostazione predefinita, MediatR utilizza Autofac come contenitore di inversione di controllo, ma è anche possibile utilizzare il contenitore di ASP.NET Core IoC predefinito o qualsiasi altro contenitore supportati da MediatR.

Il codice seguente viene illustrato come registrare i tipi e i comandi del mediatore quando si utilizzano moduli Autofac.

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();
        builder.RegisterAssemblyTypes(typeof(CreateOrderCommand)
            .GetTypeInfo().Assembly)
            .As(o => o.GetInterfaces()
            .Where(i => i.IsClosedTypeOf(typeof(IAsyncRequestHandler<,>)))
            .Select(i => new KeyedService("IAsyncRequestHandler", i)));
        builder.RegisterGenericDecorator(typeof(LogDecorator<,>),
            typeof(IAsyncRequestHandler<,>), "IAsyncRequestHandler");

        // Other types registration
    }
}
```

Poiché ogni gestore del comando implementa l'interfaccia generica IAsyncRequestHandler&lt;T&gt; e quindi controlla la RegisteredAssemblyTypes dell'oggetto, il gestore è in grado di correlare ogni comando con il gestore del comando, in quanto che relazione viene dichiarata nella classe CommandHandler, come nell'esempio seguente:

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

Questo è il codice che mette in correlazione i comandi e gestori di comandi. Il gestore è solo una classe semplice, ma eredita da RequestHandler&lt;T&gt;, e MediatR garantisce viene richiamato con il payload corretto.

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a>L'applicazione a montaggio incrociato problemi durante l'elaborazione dei comandi con gli schemi mediatore e Decorator

Un ulteriore elemento: la possibilità di applicare a montaggio incrociato riguarda la pipeline mediatore. È inoltre possibile visualizzare il codice del modulo registrazione Autofac fine come si sta registrando un elemento decorator del tipo, in particolare, una classe LogDecorator personalizzata.

Tenere presente che una versione futura di eShopOnContainers eseguirà la migrazione [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) e spostare [comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) anziché gli elementi Decorator.

Che [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) classe può essere implementata come il codice seguente, che registra le informazioni sul gestore del comando in esecuzione e se è riuscito o meno.

```csharp
public class LogDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly ILogger<LogDecorator<TRequest, TResponse>> _logger;

    public LogDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        ILogger<LogDecorator<TRequest, TResponse>> logger)
    {
        _inner = inner;
        _logger = logger;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        _logger.LogInformation($"Executing command {_inner.GetType().FullName}");
        var response = await _inner.Handle(message);
        _logger.LogInformation($"Succeeded executed command{_inner.GetType().FullName}");
        return response;
    }
}
```

Solo mediante l'implementazione di questa classe decorator e tramite la pipeline con esso, tutti i comandi di elaborazione tramite MediatR effettuerà l'accesso informazioni relative all'esecuzione.

Il eShopOnContainers ordinamento microservizio si applica anche un secondo elemento decorator per eseguire le convalide di base, il [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) classe da cui dipende il [FluentValidation](https://github.com/JeremySkinner/FluentValidation) libreria, come illustrato nel codice seguente:

```csharp
public class ValidatorDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly IValidator<TRequest>[] _validators;

    public ValidatorDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        IValidator<TRequest>[] validators)
    {
        _inner = inner;
        _validators = validators;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        var failures = _validators
            .Select(v => v.Validate(message))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();
            if (failures.Any())
            {
                throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                new ValidationException("Validation exception", failures));
            }
            var response = await _inner.Handle(message);
        return response;
    }
}
```

Quindi, in base il [FluentValidation](https://github.com/JeremySkinner/FluentValidation) libreria, creata convalida per i dati passati con CreateOrderCommand, come illustrato nel codice seguente:

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
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).
            WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).
            Must(ContainOrderItems).WithMessage("No order items found");
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

È possibile creare le convalide aggiuntive. Questo è un modo molto pulito ed elegante per implementare le convalide di comando.

In modo analogo, è possibile implementare altri elementi Decorator per aspetti aggiuntivi o problemi di montaggio incrociato che si desidera applicare ai comandi durante la loro gestione.

#### <a name="additional-resources"></a>Risorse aggiuntive

##### <a name="the-mediator-pattern"></a>Il modello mediatore

-   **Modello mediatore**
    [*https://en.wikipedia.org/wiki/Mediator\_modello*](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a>Il modello di espressione decorator

-   **Modello di espressione Decorator**
    [*https://en.wikipedia.org/wiki/Decorator\_modello*](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a>MediatR (Jimmy Bogard)

-   **MediatR.** Repository di GitHub.
    [*https://github.com/jbogard/MediatR*](https://github.com/jbogard/MediatR)

-   **CQRS con MediatR e AutoMapper**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)

-   **Inserire i controller su un cibo: post e comandi. ** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)

-   **Affrontare i problemi di montaggio incrociato con una pipeline mediatore**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)

-   **CQRS e REST: abbina**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)

-   **Esempi di Pipeline MediatR**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)

-   **Sezione verticale degli strumenti di Test per MediatR e ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*

-   **MediatR estensioni per l'aggiunta della dipendenza di Microsoft rilasciato**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)

##### <a name="fluent-validation"></a>Convalida Fluent

-   **Jeremy Skinner. FluentValidation.** Repository di GitHub.
    [*https://github.com/JeremySkinner/FluentValidation*](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
[Precedente] (microservice-application-layer-web-api-design.md) [Avanti] (... /Implement-resilient-Applications/index.MD)
