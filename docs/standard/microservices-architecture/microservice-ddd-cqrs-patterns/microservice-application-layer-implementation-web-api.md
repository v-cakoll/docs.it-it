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
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a><span data-ttu-id="f2b5b-104">Implementa il livello di applicazione microservizio mediante l'API Web</span><span class="sxs-lookup"><span data-stu-id="f2b5b-104">Implementing the microservice application layer using the Web API</span></span>

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a><span data-ttu-id="f2b5b-105">Utilizzo di inserimento di dipendenze per inserire oggetti infrastruttura nel livello dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="f2b5b-105">Using Dependency Injection to inject infrastructure objects into your application layer</span></span>

<span data-ttu-id="f2b5b-106">Come accennato in precedenza, il livello di applicazione può essere implementato come parte dell'elemento a cui si sta creando, ad esempio come all'interno di un progetto di API Web o un progetto di applicazione web MVC.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-106">As mentioned previously, the application layer can be implemented as part of the artifact you are building, such as within a Web API project or an MVC web app project.</span></span> <span data-ttu-id="f2b5b-107">Nel caso microservizio compilata con ASP.NET Core, il livello dell'applicazione sarà in genere la libreria di API Web.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-107">In the case of a microservice built with ASP.NET Core, the application layer will usually be your Web API library.</span></span> <span data-ttu-id="f2b5b-108">Se si desidera separare sviluppi futuri da ASP.NET Core (l'infrastruttura e i controller) dal codice di livello applicazione personalizzata, è anche possibile posizionare il livello di applicazione in una libreria di classi separato, ma che è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-108">If you want to separate what is coming from ASP.NET Core (its infrastructure plus your controllers) from your custom application layer code, you could also place your application layer in a separate class library, but that is optional.</span></span>

<span data-ttu-id="f2b5b-109">Ad esempio, il codice del livello applicazione di microservizio l'ordinamento viene implementato direttamente come parte di **Ordering.API** progetto (un'API Web di ASP.NET Core), come illustrato nella figura 9-19.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-109">For instance, the application layer code of the ordering microservice is directly implemented as part of the **Ordering.API** project (an ASP.NET Core Web API project), as shown in Figure 9-19.</span></span>

![](./media/image20.png)

<span data-ttu-id="f2b5b-110">**Figura 9-19**.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-110">**Figure 9-19**.</span></span> <span data-ttu-id="f2b5b-111">Il livello dell'applicazione nel progetto Ordering.API ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="f2b5b-111">The application layer in the Ordering.API ASP.NET Core Web API project</span></span>

<span data-ttu-id="f2b5b-112">ASP.NET Core include un semplice [incorporato contenitore IoC](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (rappresentato dall'interfaccia IServiceProvider) che supporta inserimento del costruttore per impostazione predefinita e ASP.NET rende disponibili tramite DI determinati servizi.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-112">ASP.NET Core includes a simple [built-in IoC container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (represented by the IServiceProvider interface) that supports constructor injection by default, and ASP.NET makes certain services available through DI.</span></span> <span data-ttu-id="f2b5b-113">ASP.NET Core viene utilizzato il termine *servizio* per i tipi di registrazione che verranno inseriti tramite DI.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-113">ASP.NET Core uses the term *service* for any of the types you register that will be injected through DI.</span></span> <span data-ttu-id="f2b5b-114">Configurare i servizi del contenitore predefinito nel metodo ConfigureServices nella classe di avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-114">You configure the built-in container's services in the ConfigureServices method in your application's Startup class.</span></span> <span data-ttu-id="f2b5b-115">Le dipendenze vengono implementate nei servizi che è necessario un tipo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-115">Your dependencies are implemented in the services that a type needs.</span></span>

<span data-ttu-id="f2b5b-116">In genere, si desidera inserire le dipendenze che implementano oggetti dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-116">Typically, you want to inject dependencies that implement infrastructure objects.</span></span> <span data-ttu-id="f2b5b-117">Una dipendenza di inserire in genere è un repository.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-117">A very typical dependency to inject is a repository.</span></span> <span data-ttu-id="f2b5b-118">Ma è possibile inserire qualsiasi altra dipendenza di infrastruttura che è possibile.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-118">But you could inject any other infrastructure dependency that you may have.</span></span> <span data-ttu-id="f2b5b-119">Per le implementazioni più semplici, si potrebbe inserire direttamente l'oggetto modello di unità di lavoro (l'oggetto DbContext EF), poiché l'elemento DBContext è anche l'implementazione degli oggetti di persistenza di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-119">For simpler implementations, you could directly inject your Unit of Work pattern object (the EF DbContext object), because the DBContext is also the implementation of your infrastructure persistence objects.</span></span>

<span data-ttu-id="f2b5b-120">Nell'esempio seguente, è possibile visualizzare la modalità .NET Core è inserendo gli oggetti necessari repository tramite il costruttore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-120">In the following example, you can see how .NET Core is injecting the required repository objects through the constructor.</span></span> <span data-ttu-id="f2b5b-121">La classe è un gestore del comando, che verranno illustrate nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-121">The class is a command handler, which we will cover in the next section.</span></span>

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

<span data-ttu-id="f2b5b-122">La classe utilizza i repository inseriti per eseguire la transazione e rendere permanenti le modifiche di stato.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-122">The class uses the injected repositories to execute the transaction and persist the state changes.</span></span> <span data-ttu-id="f2b5b-123">Non è importante se tale classe è un gestore del comando, un metodo del controller API Web di ASP.NET Core, o una [DDD applicazione servizio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-123">It does not matter whether that class is a command handler, an ASP.NET Core Web API controller method, or a [DDD Application Service](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span></span> <span data-ttu-id="f2b5b-124">In definitiva è una classe semplice che utilizza repository, entità di dominio e il coordinamento di altre applicazioni in modo simile a un gestore del comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-124">It is ultimately a simple class that uses repositories, domain entities, and other application coordination in a fashion similar to a command handler.</span></span> <span data-ttu-id="f2b5b-125">Funzionamento di Injection dipendenza in base allo stesso modo per tutte le classi indicate, come illustrato nell'esempio DI utilizzo del costruttore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-125">Dependency Injection works the same way for all the mentioned classes, as in the example using DI based on the constructor.</span></span>

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a><span data-ttu-id="f2b5b-126">Registrazione di tipi di implementazione di dipendenza e interfacce o astrazioni</span><span class="sxs-lookup"><span data-stu-id="f2b5b-126">Registering the dependency implementation types and interfaces or abstractions</span></span>

<span data-ttu-id="f2b5b-127">Prima di utilizzare gli oggetti inseriti tramite costruttori, è necessario sapere dove registrare le interfacce e classi che producono gli oggetti inseriti in classi e DI applicazione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-127">Before you use the objects injected through constructors, you need to know where to register the interfaces and classes that produce the objects injected into your application classes through DI.</span></span> <span data-ttu-id="f2b5b-128">(Ad esempio DI in base al costruttore come illustrato in precedenza).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-128">(Like DI based on the constructor, as shown previously.)</span></span>

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a><span data-ttu-id="f2b5b-129">Usa il contenitore IoC predefinito fornito da ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f2b5b-129">Using the built-in IoC container provided by ASP.NET Core</span></span>

<span data-ttu-id="f2b5b-130">Quando si usa il contenitore IoC predefinito fornito da ASP.NET Core, registrare i tipi che si desidera inserire nel metodo ConfigureServices nel file Startup.cs, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-130">When you use the built-in IoC container provided by ASP.NET Core, you register the types you want to inject in the ConfigureServices method in the Startup.cs file, as in the following code:</span></span>

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

<span data-ttu-id="f2b5b-131">Il modello più comune quando la registrazione di tipi in un contenitore IoC consiste nel registrare una coppia di tipi, ovvero un'interfaccia e la relativa classe di implementazione correlata.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-131">The most common pattern when registering types in an IoC container is to register a pair of types—an interface and its related implementation class.</span></span> <span data-ttu-id="f2b5b-132">Quindi quando si richiede un oggetto dal contenitore IoC tramite qualsiasi altro costruttore, richiedere un oggetto di un determinato tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-132">Then when you request an object from the IoC container through any constructor, you request an object of a certain type of interface.</span></span> <span data-ttu-id="f2b5b-133">Nell'esempio precedente, ad esempio, l'ultima riga indica che quando uno dei costruttori del presentano una dipendenza da IMyCustomRepository (interfaccia o astrazione), il contenitore IoC inserirà un'istanza dell'implementazione MyCustomSQLServerRepository classe.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-133">For instance, in the previous example, the last line states that when any of your constructors have a dependency on IMyCustomRepository (interface or abstraction), the IoC container will inject an instance of the MyCustomSQLServerRepository implementation class.</span></span>

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a><span data-ttu-id="f2b5b-134">Utilizzo della libreria Scrutor per la registrazione automatica di tipi</span><span class="sxs-lookup"><span data-stu-id="f2b5b-134">Using the Scrutor library for automatic types registration</span></span>

<span data-ttu-id="f2b5b-135">Quando si utilizza DI .NET Core, si potrebbe voler essere in grado di analizzare un assembly e registrare automaticamente i tipi per convenzione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-135">When using DI in .NET Core, you might want to be able to scan an assembly and automatically register its types by convention.</span></span> <span data-ttu-id="f2b5b-136">Questa funzionalità non è attualmente disponibile in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-136">This feature is not currently available in ASP.NET Core.</span></span> <span data-ttu-id="f2b5b-137">Tuttavia, è possibile utilizzare il [Scrutor](https://github.com/khellang/Scrutor) libreria a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-137">However, you can use the [Scrutor](https://github.com/khellang/Scrutor) library for that.</span></span> <span data-ttu-id="f2b5b-138">Questo approccio è utile quando si dispone di decine di tipi che devono essere registrati nel contenitore di inversione di controllo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-138">This approach is convenient when you have dozens of types that need to be registered in your IoC container.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="f2b5b-139">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f2b5b-139">Additional resources</span></span>

-   <span data-ttu-id="f2b5b-140">**Re Matthew. Registrazione dei servizi con Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-140">**Matthew King. Registering services with Scrutor**
[*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span></span>

<!-- -->

-   <span data-ttu-id="f2b5b-141">**Kristian Hellang. Scrutor.**</span><span class="sxs-lookup"><span data-stu-id="f2b5b-141">**Kristian Hellang. Scrutor.**</span></span> <span data-ttu-id="f2b5b-142">Repository di GitHub.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-142">GitHub repo.</span></span>
    [<span data-ttu-id="f2b5b-143">*https://github.com/khellang/Scrutor*</span><span class="sxs-lookup"><span data-stu-id="f2b5b-143">*https://github.com/khellang/Scrutor*</span></span>](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a><span data-ttu-id="f2b5b-144">Utilizzo di Autofac come un contenitore IoC</span><span class="sxs-lookup"><span data-stu-id="f2b5b-144">Using Autofac as an IoC container</span></span>

<span data-ttu-id="f2b5b-145">È possibile utilizzare altri contenitori IoC e inserirli nella pipeline ASP.NET di base, come l'ordinamento microservizio in eShopOnContainers, che usa [Autofac](https://autofac.org/).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-145">You can also use additional IoC containers and plug them into the ASP.NET Core pipeline, as in the ordering microservice in eShopOnContainers, which uses [Autofac](https://autofac.org/).</span></span> <span data-ttu-id="f2b5b-146">Quando si utilizza Autofac in genere necessario registrare i tipi tramite moduli, che consentono di dividere i tipi di registrazione tra più file in base alla posizione dei tipi, esattamente come è possibile includere i tipi di applicazioni distribuiti tra più librerie di classi.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-146">When using Autofac you typically register the types via modules, which allow you to split the registration types between multiple files depending on where your types are, just as you could have the application types distributed across multiple class libraries.</span></span>

<span data-ttu-id="f2b5b-147">Ad esempio, ecco la [modulo applicazione Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) per il [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) progetto con i tipi a cui si desidera inserire.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-147">For example, the following is the [Autofac application module](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) for the [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) project with the types you will want to inject.</span></span>

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

<span data-ttu-id="f2b5b-148">I concetti e il processo di registrazione sono molto simili al modo in cui che è possibile registrare i tipi con il contenitore di iOS ASP.NET Core incorporato, ma la sintassi quando si utilizza Autofac è leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-148">The registration process and concepts are very similar to the way you can register types with the built-in ASP.NET Core iOS container, but the syntax when using Autofac is a bit different.</span></span>

<span data-ttu-id="f2b5b-149">Nell'esempio di codice, l'astrazione IOrderRepository è registrato con la classe di implementazione OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-149">In the example code, the abstraction IOrderRepository is registered along with the implementation class OrderRepository.</span></span> <span data-ttu-id="f2b5b-150">Ciò significa che ogni volta che una dipendenza tramite l'interfaccia o IOrderRepository astrazione dichiara un costruttore, il contenitore IoC inserirà un'istanza della classe OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-150">This means that whenever a constructor is declaring a dependency through the IOrderRepository abstraction or interface, the IoC container will inject an instance of the OrderRepository class.</span></span>

<span data-ttu-id="f2b5b-151">Il tipo di ambito istanza determina come un'istanza condivisa tra le richieste per lo stesso servizio o dipendenze.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-151">The instance scope type determines how an instance is shared between requests for the same service or dependency.</span></span> <span data-ttu-id="f2b5b-152">Quando viene effettuata una richiesta per una dipendenza, il contenitore IoC può restituire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-152">When a request is made for a dependency, the IoC container can return the following:</span></span>

-   <span data-ttu-id="f2b5b-153">Una singola istanza per ogni ambito di durata (a cui il contenitore di ASP.NET Core IoC *con ambito*).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-153">A single instance per lifetime scope (referred to in the ASP.NET Core IoC container as *scoped*).</span></span>

-   <span data-ttu-id="f2b5b-154">Una nuova istanza per ogni dipendenza (a cui il contenitore di ASP.NET Core IoC *temporanei*).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-154">A new instance per dependency (referred to in the ASP.NET Core IoC container as *transient*).</span></span>

-   <span data-ttu-id="f2b5b-155">Una singola istanza condivisa tra tutti gli oggetti utilizzando il contenitore IoC (a cui il contenitore di ASP.NET Core IoC *singleton*).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-155">A single instance shared across all objects using the IoC container (referred to in the ASP.NET Core IoC container as *singleton*).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="f2b5b-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f2b5b-156">Additional resources</span></span>

-   <span data-ttu-id="f2b5b-157">**Introduzione a Dependency Injection in ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-157">**Introduction to Dependency Injection in ASP.NET Core**
[*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span></span>

-   <span data-ttu-id="f2b5b-158">**Autofac.**</span><span class="sxs-lookup"><span data-stu-id="f2b5b-158">**Autofac.**</span></span> <span data-ttu-id="f2b5b-159">Documentazione ufficiale.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-159">Official documentation.</span></span>
    [<span data-ttu-id="f2b5b-160">*http://docs.autofac.org/en/Latest/*</span><span class="sxs-lookup"><span data-stu-id="f2b5b-160">*http://docs.autofac.org/en/latest/*</span></span>](http://docs.autofac.org/en/latest/)

-   <span data-ttu-id="f2b5b-161">**Cesar de la Torre. Confronto tra la durata di servizio contenitore di ASP.NET Core IoC con ambiti di istanza contenitore IoC Autofac**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-core-IoC-Service-Life-Times-and-autofac-IoC-Instance-Scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-161">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="implementing-the-command-and-command-handler-patterns"></a><span data-ttu-id="f2b5b-162">Implementare i modelli di comando e il gestore del comando</span><span class="sxs-lookup"><span data-stu-id="f2b5b-162">Implementing the Command and Command Handler patterns</span></span>

<span data-ttu-id="f2b5b-163">Nell'esempio DI-a-costruttore illustrato nella sezione precedente, il contenitore IoC stato inserendo repository tramite un costruttore in una classe.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-163">In the DI-through-constructor example shown in the previous section, the IoC container was injecting repositories through a constructor in a class.</span></span> <span data-ttu-id="f2b5b-164">Ma esattamente in cui sono stati sono inserite?</span><span class="sxs-lookup"><span data-stu-id="f2b5b-164">But exactly where were they injected?</span></span> <span data-ttu-id="f2b5b-165">In un'API Web semplice (ad esempio, microservizio catalogo in eShopOnContainers), invece possibile inserire tali a livello di controller MVC, in un costruttore di controller.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-165">In a simple Web API (for example, the catalog microservice in eShopOnContainers), you inject them at the MVC controllers level, in a controller constructor.</span></span> <span data-ttu-id="f2b5b-166">Tuttavia, nel codice iniziale di questa sezione (il [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) classe dal servizio Ordering.API in eShopOnContainers), l'inserimento di dipendenze viene eseguita tramite il costruttore di un particolare comando gestore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-166">However, in the initial code of this section (the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) class from the Ordering.API service in eShopOnContainers), the injection of dependencies is done through the constructor of a particular command handler.</span></span> <span data-ttu-id="f2b5b-167">Segnalare il problema viene illustrato un gestore di comandi è e motivi per cui si desidera utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-167">Let us explain what a command handler is and why you would want to use it.</span></span>

<span data-ttu-id="f2b5b-168">Il modello di comando è intrinsecamente correlato al modello CQRS che è stata introdotta in precedenza in questa Guida.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-168">The Command pattern is intrinsically related to the CQRS pattern that was introduced earlier in this guide.</span></span> <span data-ttu-id="f2b5b-169">CQRS ha due lati.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-169">CQRS has two sides.</span></span> <span data-ttu-id="f2b5b-170">La prima area è una query, tramite query semplificata con la [Dapper](https://github.com/StackExchange/dapper-dot-net) ORM micro, che è stata illustrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-170">The first area is queries, using simplified queries with the [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, which was explained previously.</span></span> <span data-ttu-id="f2b5b-171">La seconda area è comandi, ovvero il punto di partenza per le transazioni e il canale di input all'esterno del servizio.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-171">The second area is commands, which are the starting point for transactions, and the input channel from outside the service.</span></span>

<span data-ttu-id="f2b5b-172">Come illustrato nella figura 9-20, il modello è basato sull'accetta comandi dal lato client, l'elaborazione in base alle regole del modello di dominio e infine la persistenza degli Stati con transazioni.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-172">As shown in Figure 9-20, the pattern is based on accepting commands from the client side, processing them based on the domain model rules, and finally persisting the states with transactions.</span></span>

![](./media/image21.png)

<span data-ttu-id="f2b5b-173">**Figura 9-20**.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-173">**Figure 9-20**.</span></span> <span data-ttu-id="f2b5b-174">Visualizzazione di alto livello dei comandi "transazionale lato" in un modello CQRS</span><span class="sxs-lookup"><span data-stu-id="f2b5b-174">High-level view of the commands or “transactional side” in a CQRS pattern</span></span>

### <a name="the-command-class"></a><span data-ttu-id="f2b5b-175">La classe di comando</span><span class="sxs-lookup"><span data-stu-id="f2b5b-175">The command class</span></span>

<span data-ttu-id="f2b5b-176">Un comando è una richiesta per il sistema eseguire un'azione che modifica lo stato del sistema.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-176">A command is a request for the system to perform an action that changes the state of the system.</span></span> <span data-ttu-id="f2b5b-177">I comandi sono imperativi e devono essere elaborati una sola volta.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-177">Commands are imperative, and should be processed just once.</span></span>

<span data-ttu-id="f2b5b-178">Poiché i comandi sono esigenze, in genere sono denominate con un verbo all'interno di uno stile imperativo (ad esempio, "Crea" o "aggiornamento") e potrebbero includere il tipo di aggregazione, ad esempio CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-178">Since commands are imperatives, they are typically named with a verb in the imperative mood (for example, "create" or "update"), and they might include the aggregate type, such as CreateOrderCommand.</span></span> <span data-ttu-id="f2b5b-179">A differenza di un evento, un comando non è un fatto trascorsa; è solo una richiesta e pertanto non può essere rifiutata.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-179">Unlike an event, a command is not a fact from the past; it is only a request, and thus may be refused.</span></span>

<span data-ttu-id="f2b5b-180">Quando il gestore di processi è indirizzare un'aggregazione per eseguire un'azione, i comandi possono provenire dall'interfaccia utente in seguito a un utente che ha avviato una richiesta o da un gestore di processi.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-180">Commands can originate from the UI as a result of a user initiating a request, or from a process manager when the process manager is directing an aggregate to perform an action.</span></span>

<span data-ttu-id="f2b5b-181">Una caratteristica importante di un comando è che deve essere elaborato una sola volta da un singolo ricevitore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-181">An important characteristic of a command is that it should be processed just once by a single receiver.</span></span> <span data-ttu-id="f2b5b-182">In questo modo un comando è una singola azione o una transazione da eseguire nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-182">This is because a command is a single action or transaction you want to perform in the application.</span></span> <span data-ttu-id="f2b5b-183">Ad esempio, il comando di creazione dell'ordine stesso non deve essere elaborato più volte.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-183">For example, the same order creation command should not be processed more than once.</span></span> <span data-ttu-id="f2b5b-184">Si tratta di un'importante differenza tra i comandi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-184">This is an important difference between commands and events.</span></span> <span data-ttu-id="f2b5b-185">Gli eventi possono essere elaborati più volte, in quanto molti sistemi o microservizi potrebbero essere interessati nell'evento.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-185">Events may be processed multiple times, because many systems or microservices might be interested in the event.</span></span>

<span data-ttu-id="f2b5b-186">Inoltre, è importante che un comando elaborato solo una volta nel caso in cui il comando non è idempotente.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-186">In addition, it is important that a command be processed only once in case the command is not idempotent.</span></span> <span data-ttu-id="f2b5b-187">Un comando è idempotente, se può essere eseguita più volte senza modificare il risultato, oppure a causa della natura del comando, a causa del modo in cui che il sistema gestisce il comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-187">A command is idempotent if it can be executed multiple times without changing the result, either because of the nature of the command, or because of the way the system handles the command.</span></span>

<span data-ttu-id="f2b5b-188">È buona norma dei comandi e aggiorna idempotente quando avrebbe senso in regole di business del proprio dominio e invarianti.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-188">It is a good practice to make your commands and updates idempotent when it makes sense under your domain’s business rules and invariants.</span></span> <span data-ttu-id="f2b5b-189">Per utilizzare lo stesso esempio, se per qualsiasi motivo (logica di ripetizione dei tentativi di attacco, e così via) lo stesso comando CreateOrder raggiunge il sistema più volte, ad esempio, deve essere in grado di identificarlo e assicurarsi di non creare più ordini.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-189">For instance, to use the same example, if for any reason (retry logic, hacking, etc.) the same CreateOrder command reaches your system multiple times, you should be able to identify it and ensure that you do not create multiple orders.</span></span> <span data-ttu-id="f2b5b-190">A tale scopo, è necessario collegare un tipo di identità nelle operazioni e identificare se il comando o l'aggiornamento è già stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-190">To do so, you need to attach some kind of identity in the operations and identify whether the command or update was already processed.</span></span>

<span data-ttu-id="f2b5b-191">Si invia un comando a un singolo destinatario; non pubblica di un comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-191">You send a command to a single receiver; you do not publish a command.</span></span> <span data-ttu-id="f2b5b-192">La pubblicazione è per gli eventi di integrazione che lo stato di un fatto, che un elemento si è verificato e potrebbe essere interessante per i ricevitori di eventi.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-192">Publishing is for integration events that state a fact—that something has happened and might be interesting for event receivers.</span></span> <span data-ttu-id="f2b5b-193">Nel caso di eventi, il server di pubblicazione non ha dubbi sui ricevitori di ottenere l'evento o lo scopo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-193">In the case of events, the publisher has no concerns about which receivers get the event or what they do it.</span></span> <span data-ttu-id="f2b5b-194">Questi eventi di integrazione con un'altra storia già introdotta nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-194">But integration events are a different story already introduced in previous sections.</span></span>

<span data-ttu-id="f2b5b-195">Un comando è implementato con una classe che contiene i campi dati o le raccolte con tutte le informazioni necessarie per eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-195">A command is implemented with a class that contains data fields or collections with all the information that is needed in order to execute that command.</span></span> <span data-ttu-id="f2b5b-196">Un comando è un tipo speciale di dati trasferire oggetti (DTO), che viene usato in modo specifico per richiedere modifiche o le transazioni.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-196">A command is a special kind of Data Transfer Object (DTO), one that is specifically used to request changes or transactions.</span></span> <span data-ttu-id="f2b5b-197">Il comando stesso si basa sul esattamente le informazioni necessarie per elaborare il comando e nient'altro.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-197">The command itself is based on exactly the information that is needed for processing the command, and nothing more.</span></span>

<span data-ttu-id="f2b5b-198">Nell'esempio seguente viene illustrata la classe CreateOrderCommand semplificata.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-198">The following example shows the simplified CreateOrderCommand class.</span></span> <span data-ttu-id="f2b5b-199">Si tratta di un comando non modificabile che viene utilizzato per l'ordinamento microservizio in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-199">This is an immutable command that is used in the ordering microservice in eShopOnContainers.</span></span>

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

<span data-ttu-id="f2b5b-200">In pratica, la classe di comando contiene tutti i dati che necessari per l'esecuzione di una transazione di business utilizzando gli oggetti modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-200">Basically, the command class contains all the data you need for performing a business transaction by using the domain model objects.</span></span> <span data-ttu-id="f2b5b-201">Pertanto, i comandi sono semplicemente strutture di dati che contengono dati di sola lettura e alcun comportamento.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-201">Thus, commands are simply data structures that contain read-only data, and no behavior.</span></span> <span data-ttu-id="f2b5b-202">Il nome del comando indica lo scopo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-202">The command’s name indicates its purpose.</span></span> <span data-ttu-id="f2b5b-203">In molti linguaggi come C\#, i comandi sono rappresentati come classi, ma non sono classi true in senso reale orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-203">In many languages like C\#, commands are represented as classes, but they are not true classes in the real object-oriented sense.</span></span>

<span data-ttu-id="f2b5b-204">Come una caratteristica aggiuntiva, i comandi non sono modificabili, perché l'utilizzo previsto è che vengono elaborati direttamente dal modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-204">As an additional characteristic, commands are immutable, because the expected usage is that they are processed directly by the domain model.</span></span> <span data-ttu-id="f2b5b-205">Non devono cambiare durante il loro ciclo di vita previsto.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-205">They do not need to change during their projected lifetime.</span></span> <span data-ttu-id="f2b5b-206">In C\# (classe), immutabilità può essere ottenuta dalla mancanza di qualsiasi Setter o altri metodi che modificano lo stato interno.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-206">In a C\# class, immutability can be achieved by not having any setters or other methods that change internal state.</span></span>

<span data-ttu-id="f2b5b-207">Ad esempio, è probabilmente simile in termini di dati per l'ordine in cui che si desidera creare la classe di comando per la creazione di un ordine, ma probabile che non richiedono gli stessi attributi.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-207">For example, the command class for creating an order is probably similar in terms of data to the order you want to create, but you probably do not need the same attributes.</span></span> <span data-ttu-id="f2b5b-208">Ad esempio, CreateOrderCommand non dispone di un ID ordine, perché l'ordine non è ancora stato creato.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-208">For instance, CreateOrderCommand does not have an order ID, because the order has not been created yet.</span></span>

<span data-ttu-id="f2b5b-209">Molte classi di comando possono essere semplice, che richiede solo pochi campi su uno stato che deve essere modificato.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-209">Many command classes can be simple, requiring only a few fields about some state that needs to be changed.</span></span> <span data-ttu-id="f2b5b-210">Che è il caso se si desidera modificare solo lo stato di un ordine da "in corso" a "pagamento" o "consegna" utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-210">That would be the case if you are just changing the status of an order from “in process” to “paid” or “shipped” by using a command similar to the following:</span></span>

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

<span data-ttu-id="f2b5b-211">Alcuni sviluppatori apportare separato dal loro DTO comando i relativi oggetti di richiesta dell'interfaccia utente, ma che solo una questione di preferenze.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-211">Some developers make their UI request objects separate from their command DTOs, but that is just a matter of preference.</span></span> <span data-ttu-id="f2b5b-212">È una separazione noiosa con un valore non aggiunto e gli oggetti sono quasi esattamente la stessa forma.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-212">It is a tedious separation with not much added value, and the objects are almost exactly the same shape.</span></span> <span data-ttu-id="f2b5b-213">Ad esempio, in eShopOnContainers, i comandi disponibili direttamente dal lato client.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-213">For instance, in eShopOnContainers, the commands come directly from the client side.</span></span>

### <a name="the-command-handler-class"></a><span data-ttu-id="f2b5b-214">La classe del gestore del comando</span><span class="sxs-lookup"><span data-stu-id="f2b5b-214">The Command Handler class</span></span>

<span data-ttu-id="f2b5b-215">È necessario implementare una classe del gestore di comandi specifici per ogni comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-215">You should implement a specific command handler class for each command.</span></span> <span data-ttu-id="f2b5b-216">Che è il funzionamento il modello in modo in cui si userà l'oggetto comando, gli oggetti di dominio e oggetti di repository dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-216">That is how the pattern works, and it is where you will use the command object, the domain objects, and the infrastructure repository objects.</span></span> <span data-ttu-id="f2b5b-217">Il gestore del comando è in realtà il cuore del livello dell'applicazione in termini di CQRS e DDD.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-217">The command handler is in fact the heart of the application layer in terms of CQRS and DDD.</span></span> <span data-ttu-id="f2b5b-218">Tuttavia, la logica di dominio deve essere contenuta all'interno delle classi di dominio, entro le radici di aggregazione (entità radice), le entità figlio, o [servizi di dominio](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), ma non all'interno del gestore di comando, ovvero una classe dall'applicazione livello.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-218">However, all the domain logic should be contained within the domain classes—within the aggregate roots (root entities), child entities, or [domain services](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), but not within the command handler, which is a class from the application layer.</span></span>

<span data-ttu-id="f2b5b-219">Un gestore del comando riceve un comando e ottiene un risultato dall'aggregazione utilizzata.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-219">A command handler receives a command and obtains a result from the aggregate that is used.</span></span> <span data-ttu-id="f2b5b-220">Il risultato deve essere corretta esecuzione del comando o un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-220">The result should be either successful execution of the command, or an exception.</span></span> <span data-ttu-id="f2b5b-221">In caso di eccezione, lo stato del sistema deve essere unchanged.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-221">In the case of an exception, the system state should be unchanged.</span></span>

<span data-ttu-id="f2b5b-222">In genere, il gestore del comando esegue i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-222">The command handler usually takes the following steps:</span></span>

-   <span data-ttu-id="f2b5b-223">Riceve l'oggetto comando, ad esempio un DTO (dal [mediatore](https://en.wikipedia.org/wiki/Mediator_pattern) o un altro oggetto infrastruttura).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-223">It receives the command object, like a DTO (from the [mediator](https://en.wikipedia.org/wiki/Mediator_pattern) or other infrastructure object).</span></span>

-   <span data-ttu-id="f2b5b-224">Convalida che il comando è valido (se non viene convalidata da mediatore).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-224">It validates that the command is valid (if not validated by the mediator).</span></span>

-   <span data-ttu-id="f2b5b-225">Crea l'istanza radice di aggregazione di destinazione del comando corrente.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-225">It instantiates the aggregate root instance that is the target of the current command.</span></span>

-   <span data-ttu-id="f2b5b-226">Il metodo viene eseguito nell'istanza principale di aggregazione, ottenere i dati richiesti dal comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-226">It executes the method on the aggregate root instance, getting the required data from the command.</span></span>

-   <span data-ttu-id="f2b5b-227">Il nuovo stato dell'aggregato al relativo database correlati persiste.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-227">It persists the new state of the aggregate to its related database.</span></span> <span data-ttu-id="f2b5b-228">L'ultima operazione è la transazione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-228">This last operation is the actual transaction.</span></span>

<span data-ttu-id="f2b5b-229">In genere, un gestore del comando riguarda una singola funzione di aggregazione dovute alla relativa radice di aggregazione (entità radice).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-229">Typically, a command handler deals with a single aggregate driven by its aggregate root (root entity).</span></span> <span data-ttu-id="f2b5b-230">Se più funzioni di aggregazione dovrebbe essere interessate dalla ricezione di un unico comando, è possibile utilizzare gli eventi di dominio per stati o le azioni si propagano tra più funzioni di aggregazione</span><span class="sxs-lookup"><span data-stu-id="f2b5b-230">If multiple aggregates should be impacted by the reception of a single command, you could use domain events to propagate states or actions across multiple aggregates</span></span>

<span data-ttu-id="f2b5b-231">Ecco l'aspetto importante è che, durante l'elaborazione di un comando, tutta la logica di dominio deve essere all'interno del modello di dominio (le funzioni di aggregazione), completamente incapsulato e pronto per gli unit test.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-231">The important point here is that when a command is being processed, all the domain logic should be inside the domain model (the aggregates), fully encapsulated and ready for unit testing.</span></span> <span data-ttu-id="f2b5b-232">Il gestore del comando viene utilizzato solo come un modo per ottenere il modello di dominio dal database e come il passaggio finale, per indicare il livello di infrastruttura (repository) per rendere permanenti le modifiche quando viene modificato il modello.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-232">The command handler just acts as a way to get the domain model from the database, and as the final step, to tell the infrastructure layer (repositories) to persist the changes when the model is changed.</span></span> <span data-ttu-id="f2b5b-233">Il vantaggio di questo approccio è che è possibile eseguire il refactoring di logica di dominio in un modello di dominio isolato, incapsulato completamente, RTF, comportamento senza modificare il codice dell'applicazione o i livelli di infrastruttura, che costituiscono il livello di infrastruttura (gestori di comandi, API Web, repository e così via).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-233">The advantage of this approach is that you can refactor the domain logic in an isolated, fully encapsulated, rich, behavioral domain model without changing code in the application or infrastructure layers, which are the plumbing level (command handlers, Web API, repositories, etc.).</span></span>

<span data-ttu-id="f2b5b-234">Quando i gestori di comandi ottengono complessi, con una quantità eccessiva logica, che può essere un odore di codice.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-234">When command handlers get complex, with too much logic, that can be a code smell.</span></span> <span data-ttu-id="f2b5b-235">Rivedere e se la logica di dominio, il refactoring del codice per spostare il comportamento di tale dominio ai metodi degli oggetti di dominio (l'entità di primo livello e figlio aggregazione).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-235">Review them, and if you find domain logic, refactor the code to move that domain behavior to the methods of the domain objects (the aggregate root and child entity).</span></span>

<span data-ttu-id="f2b5b-236">Ad esempio di una classe di gestore del comando, il codice seguente illustra la stessa classe CreateOrderCommandHandler che si verifica all'inizio di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-236">As an example of a command handler class, the following code shows the same CreateOrderCommandHandler class that you saw at the beginning of this chapter.</span></span> <span data-ttu-id="f2b5b-237">In questo caso è stato evidenziato il metodo di Handle e le operazioni con il dominio modello a oggetti o funzioni di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-237">In this case we have highlighted the Handle method and the operations with the domain model objects/aggregates.</span></span>

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

<span data-ttu-id="f2b5b-238">Questi sono necessari passaggi aggiuntivi che debba eseguire un gestore del comando:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-238">These are additional steps a command handler should take:</span></span>

-   <span data-ttu-id="f2b5b-239">Utilizzare i dati del comando per funzionare con metodi di aggregazione radice e il comportamento.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-239">Use the command’s data to operate with the aggregate root’s methods and behavior.</span></span>

-   <span data-ttu-id="f2b5b-240">Internamente all'interno di oggetti di dominio, generare eventi di dominio durante la transazione viene eseguita, ma che è trasparente da un punto di vista di comando gestore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-240">Internally within the domain objects, raise domain events while the transaction is executed, but that is transparent from a command handler point of view.</span></span>

-   <span data-ttu-id="f2b5b-241">Se il risultato dell'operazione di aggregazione ha esito positivo e al termine della transazione, generare il gestore del comando integrazione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-241">If the aggregate’s operation result is successful and after the transaction is finished, raise integration events command handler.</span></span> <span data-ttu-id="f2b5b-242">(Questi potrebbe anche essere generati dalle classi di infrastruttura come repository.)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-242">(These might also be raised by infrastructure classes like repositories.)</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="f2b5b-243">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f2b5b-243">Additional resources</span></span>

-   <span data-ttu-id="f2b5b-244">**Contrassegno Seemann. I limiti, le applicazioni sono orientata agli oggetti non**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries, orientata ai servizi ApplicationsareNotObject /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-244">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented**
[*http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span></span>

-   <span data-ttu-id="f2b5b-245">**I comandi ed eventi**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-245">**Commands and events**
[*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span></span>

-   <span data-ttu-id="f2b5b-246">**Che cosa è un gestore del comando? ** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-246">**What does a command handler do?**
[*http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span></span>

-   <span data-ttu-id="f2b5b-247">**Jimmy Bogard. Modelli di comandi dominio – gestori**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-247">**Jimmy Bogard. Domain Command Patterns – Handlers**
[*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span></span>

-   <span data-ttu-id="f2b5b-248">**Jimmy Bogard. Modelli di comandi di dominio: convalida**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-248">**Jimmy Bogard. Domain Command Patterns – Validation**
[*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span></span>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a><span data-ttu-id="f2b5b-249">La pipeline di processo del comando: come attivare un gestore del comando</span><span class="sxs-lookup"><span data-stu-id="f2b5b-249">The Command process pipeline: how to trigger a command handler</span></span>

<span data-ttu-id="f2b5b-250">Domanda successiva viene illustrato come richiamare un gestore del comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-250">The next question is how to invoke a command handler.</span></span> <span data-ttu-id="f2b5b-251">È possibile chiamarlo manualmente da ogni controller di ASP.NET Core correlati.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-251">You could manually call it from each related ASP.NET Core controller.</span></span> <span data-ttu-id="f2b5b-252">Tuttavia, che approccio potrebbe essere troppo ridotto e non è ideale.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-252">However, that approach would be too coupled and is not ideal.</span></span>

<span data-ttu-id="f2b5b-253">Le altre due opzioni principali, che sono le opzioni consigliate, sono:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-253">The other two main options, which are the recommended options, are:</span></span>

-   <span data-ttu-id="f2b5b-254">Tramite un elemento di modello mediatore in memoria.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-254">Through an in-memory Mediator pattern artifact.</span></span>

-   <span data-ttu-id="f2b5b-255">Con una coda di messaggi asincroni, tra i controller e i gestori.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-255">With an asynchronous message queue, in between controllers and handlers.</span></span>

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a><span data-ttu-id="f2b5b-256">Usando il modello di mediatore (in memoria) nella pipeline dei comandi</span><span class="sxs-lookup"><span data-stu-id="f2b5b-256">Using the Mediator pattern (in-memory) in the command pipeline</span></span>

<span data-ttu-id="f2b5b-257">Come illustrato nella figura 9-21, in un approccio CQRS si utilizza un mediatore intelligente, simile a un bus in memoria, ovvero abbastanza per reindirizzare al gestore del comando corretto in base al tipo del comando o DTO ricevuti.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-257">As shown in Figure 9-21, in a CQRS approach you use an intelligent mediator, similar to an in-memory bus, which is smart enough to redirect to the right command handler based on the type of the command or DTO being received.</span></span> <span data-ttu-id="f2b5b-258">Le frecce nere singole tra i componenti rappresentano le dipendenze tra oggetti (in molti casi, inseriti tramite DI) con le relative interazioni.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-258">The single black arrows between components represent the dependencies between objects (in many cases, injected through DI) with their related interactions.</span></span>

![](./media/image22.png)

<span data-ttu-id="f2b5b-259">**Figura 9-21**.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-259">**Figure 9-21**.</span></span> <span data-ttu-id="f2b5b-260">Usando il modello mediatore nel processo in un singolo microservizio CQRS</span><span class="sxs-lookup"><span data-stu-id="f2b5b-260">Using the Mediator pattern in process in a single CQRS microservice</span></span>

<span data-ttu-id="f2b5b-261">Il motivo che usa il modello mediatore significativo è che in applicazioni aziendali, le richieste di elaborazione possono diventare complicate.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-261">The reason that using the Mediator pattern makes sense is that in enterprise applications, the processing requests can get complicated.</span></span> <span data-ttu-id="f2b5b-262">Si desidera essere in grado di aggiungere un numero di aprire delle problematiche trasversali quali registrazione, le convalide, controllo e sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-262">You want to be able to add an open number of cross-cutting concerns like logging, validations, audit, and security.</span></span> <span data-ttu-id="f2b5b-263">In questi casi, è possibile basarsi su una pipeline mediatore (vedere [modello mediatore](https://en.wikipedia.org/wiki/Mediator_pattern)) per fornire un mezzo per questi comportamenti aggiuntivi o i problemi di montaggio incrociato.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-263">In these cases, you can rely on a mediator pipeline (see [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern)) to provide a means for these extra behaviors or cross-cutting concerns.</span></span>

<span data-ttu-id="f2b5b-264">Mediatore è un oggetto che incapsula il "come" di questo processo: coordina l'esecuzione in base allo stato, la modalità di un gestore del comando viene richiamata o il payload fornire al gestore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-264">A mediator is an object that encapsulates the “how” of this process: it coordinates execution based on state, the way a command handler is invoked, or the payload you provide to the handler.</span></span> <span data-ttu-id="f2b5b-265">Con un componente mediatore è possibile applicare a montaggio incrociato problemi in modo centralizzato e trasparente applicando gli elementi Decorator (o [pipeline comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) dal mediatore v3).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-265">With a mediator component you can apply cross-cutting concerns in a centralized and transparent way by applying decorators (or [pipeline behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) since Mediator v3).</span></span> <span data-ttu-id="f2b5b-266">(Per ulteriori informazioni, vedere il [modello di espressione Decorator](https://en.wikipedia.org/wiki/Decorator_pattern).)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-266">(For more information, see the [Decorator pattern](https://en.wikipedia.org/wiki/Decorator_pattern).)</span></span>

<span data-ttu-id="f2b5b-267">Gli elementi Decorator e comportamenti sono simili a [aspetto Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), applicato a una pipeline di processo specifico gestita dal componente mediatore solo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-267">Decorators and behaviors are similar to [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), only applied to a specific process pipeline managed by the mediator component.</span></span> <span data-ttu-id="f2b5b-268">Gli aspetti AOP che implementano i problemi di montaggio incrociato vengono applicati in base *weavers aspetto* inseriti in fase di compilazione o in base a intercettazione di chiamata di oggetto.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-268">Aspects in AOP that implement cross-cutting concerns are applied based on *aspect weavers* injected at compilation time or based on object call interception.</span></span> <span data-ttu-id="f2b5b-269">Entrambi gli approcci di AOP tipici vengono talvolta denominati funzionano "come chiave," perché non è facile capire come AOP esegue il proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-269">Both typical AOP approaches are sometimes said to work "like magic," because it is not easy to see how AOP does its work.</span></span> <span data-ttu-id="f2b5b-270">Quando si lavora con gravi problemi o i bug, AOP può essere difficile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-270">When dealing with serious issues or bugs, AOP can be difficult to debug.</span></span> <span data-ttu-id="f2b5b-271">D'altra parte, questi elementi Decorator e comportamenti sono esplicita e applicate solo nel contesto di mediatore, pertanto il debug è molto più semplice e prevedibile.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-271">On the other hand, these decorators/behaviors are explicit and applied only in the context of the mediator, so debugging is much more predictable and easy.</span></span>

<span data-ttu-id="f2b5b-272">Ad esempio, in eShopOnContainers ordinamento microservizio, sono implementati due elementi Decorator di esempio, un [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) classe e un [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) classe.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-272">For example, in the eShopOnContainers ordering microservice, we implemented two sample decorators, a [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class and a [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class.</span></span> <span data-ttu-id="f2b5b-273">Implementazione dell'elemento decorator è illustrato nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-273">The decorator’s implementation is explained in the next section.</span></span> <span data-ttu-id="f2b5b-274">Si noti che in una versione futura, eShopOnContainers verrà eseguita la migrazione a [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) e spostare [comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) anziché gli elementi Decorator.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-274">Note that in a future version, eShopOnContainers will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a><span data-ttu-id="f2b5b-275">Utilizzo delle code di messaggi (out-of-process) nella pipeline del comando</span><span class="sxs-lookup"><span data-stu-id="f2b5b-275">Using message queues (out-of-proc) in the command’s pipeline</span></span>

<span data-ttu-id="f2b5b-276">Un'altra opzione consiste nell'utilizzare messaggi asincroni in base alle istanze di Service Broker o code di messaggi, come illustrato nella figura 9 a 22.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-276">Another choice is to use asynchronous messages based on brokers or message queues, as shown in Figure 9-22.</span></span> <span data-ttu-id="f2b5b-277">Tale opzione, inoltre, può essere combinate con il componente mediatore immediatamente prima il gestore del comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-277">That option could also be combined with the mediator component right before the command handler.</span></span>

![](./media/image23.png)

<span data-ttu-id="f2b5b-278">**Figura 9 a 22**.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-278">**Figure 9-22**.</span></span> <span data-ttu-id="f2b5b-279">Usare le code di messaggi (fuori processo e comunicazione interprocesso) con i comandi CQRS</span><span class="sxs-lookup"><span data-stu-id="f2b5b-279">Using message queues (out of process and inter-process communication) with CQRS commands</span></span>

<span data-ttu-id="f2b5b-280">Tramite messaggio code per accettare che i comandi possono ulteriormente complicano la pipeline del comando, perché sarà probabilmente necessario suddividere la pipeline in due processi connessi tramite la coda di messaggi esterni.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-280">Using message queues to accept the commands can further complicate your command’s pipeline, because you will probably need to split the pipeline into two processes connected through the external message queue.</span></span> <span data-ttu-id="f2b5b-281">Ancora, e deve essere utilizzato se è necessario sono migliorate, scalabilità e prestazioni in base alla messaggistica asincrona.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-281">Still, it should be used if you need to have improved scalability and performance based on asynchronous messaging.</span></span> <span data-ttu-id="f2b5b-282">Tenere presente che nel caso di figura 9 a 22, il controller appena viene inviato il messaggio di comando in coda e restituisce.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-282">Consider that in the case of Figure 9-22, the controller just posts the command message into the queue and returns.</span></span> <span data-ttu-id="f2b5b-283">I gestori di comando quindi elaborano i messaggi in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-283">Then the command handlers process the messages at their own pace.</span></span> <span data-ttu-id="f2b5b-284">Vale a dire un notevole vantaggio delle code, ovvero la coda di messaggi può fungere da un buffer in casi quando la scalabilità hyper è necessaria, ad esempio stock o qualsiasi altro scenario con un elevato volume di dati in entrata.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-284">That is a great benefit of queues—the message queue can act as a buffer in cases when hyper scalability is needed, such as for stocks or any other scenario with a high volume of ingress data.</span></span>

<span data-ttu-id="f2b5b-285">Tuttavia, a causa della natura asincrona delle code di messaggi, è necessario capire come comunicare con l'applicazione client sull'esito positivo o negativo del processo del comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-285">However, because of the asynchronous nature of message queues, you need to figure out how to communicate with the client application about the success or failure of the command’s process.</span></span> <span data-ttu-id="f2b5b-286">Di norma, non utilizzare mai i comandi "fire and forget".</span><span class="sxs-lookup"><span data-stu-id="f2b5b-286">As a rule, you should never use “fire and forget” commands.</span></span> <span data-ttu-id="f2b5b-287">Ogni applicazione di business deve sapere se un comando è stato elaborato correttamente, o almeno convalidato e accettato.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-287">Every business application needs to know if a command was processed successfully, or at least validated and accepted.</span></span>

<span data-ttu-id="f2b5b-288">Di conseguenza, la possibilità di rispondere al client dopo la convalida di un messaggio di comando che è stato inviato a una coda asincrona aggiunge complessità al sistema, rispetto a un processo del comando in-process che restituisce il risultato dell'operazione dopo l'esecuzione della transazione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-288">Thus, being able to respond to the client after validating a command message that was submitted to an asynchronous queue adds complexity to your system, as compared to an in-process command process that returns the operation’s result after running the transaction.</span></span> <span data-ttu-id="f2b5b-289">Utilizzo delle code, potrebbe essere necessario restituire il risultato del processo di comando tramite altri messaggi, risultato dell'operazione che richiede i componenti aggiuntivi e personalizzate di comunicazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-289">Using queues, you might need to return the result of the command process through other operation result messages, which will require additional components and custom communication in your system.</span></span>

<span data-ttu-id="f2b5b-290">Inoltre, i comandi di async sono comandi unidirezionali, che, in molti casi, potrebbero non essere necessaria, come è illustrato nella seguente interessano scambio tra Burtsev Alexey e Greg Young in un [conversazione online](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span><span class="sxs-lookup"><span data-stu-id="f2b5b-290">Additionally, async commands are one-way commands, which in many cases might not be needed, as is explained in the following interesting exchange between Burtsev Alexey and Greg Young in an [online conversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span></span>

<span data-ttu-id="f2b5b-291">\[Burtsev Alexey\] è possibile individuare una grande quantità di codice in cui utenti utilizzano la gestione dei comandi asincrona o un comando unidirezionale messaggistica senza alcun motivo per eseguire questa operazione (non sta eseguendo un'operazione lunga, codice asincrono esterni non sono in esecuzione, non si incrociano anche applicazione limite di bus di messaggi).</span><span class="sxs-lookup"><span data-stu-id="f2b5b-291">\[Burtsev Alexey\] I find lots of code where people use async command handling or one way command messaging without any reason to do so (they are not doing some long operation, they are not executing external async code, they do not even cross application boundary to be using message bus).</span></span> <span data-ttu-id="f2b5b-292">Motivo per cui introducono questa complessità superflua?</span><span class="sxs-lookup"><span data-stu-id="f2b5b-292">Why do they introduce this unnecessary complexity?</span></span> <span data-ttu-id="f2b5b-293">E, in realtà, non ho visto un esempio di codice con il blocco fino a questo punto, i gestori di comandi CQRS se funziona bene nella maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-293">And actually, I haven't seen a CQRS code example with blocking command handlers so far, though it will work just fine in most cases.</span></span>

<span data-ttu-id="f2b5b-294">\[Greg Young\] \[... \] non esiste un comando asincrono, è effettivamente un altro evento.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-294">\[Greg Young\] \[...\] an asynchronous command doesn't exist; it's actually another event.</span></span> <span data-ttu-id="f2b5b-295">Se è necessario accettare ciò che si invia e genera un evento se non sono d'accordo, non è più si informa per eseguire un'operazione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-295">If I must accept what you send me and raise an event if I disagree, it's no longer you telling me to do something.</span></span> <span data-ttu-id="f2b5b-296">È è informa che un'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-296">It's you telling me something has been done.</span></span> <span data-ttu-id="f2b5b-297">Questa opzione sembri una leggera differenza inizialmente, ma presenta implicazioni molti.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-297">This seems like a slight difference at first, but it has many implications.</span></span>

<span data-ttu-id="f2b5b-298">Comandi asincroni aumentare notevolmente la complessità di un sistema, poiché non esiste un modo semplice per indicare gli errori.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-298">Asynchronous commands greatly increase the complexity of a system, because there is no simple way to indicate failures.</span></span> <span data-ttu-id="f2b5b-299">Di conseguenza, i comandi asincroni non sono consigliati diverso da quando sono necessari requisiti di scalabilità o, in casi speciali durante la comunicazione di microservizi interno tramite messaggistica.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-299">Therefore, asynchronous commands are not recommended other than when scaling requirements are needed or in special cases when communicating the internal microservices through messaging.</span></span> <span data-ttu-id="f2b5b-300">In questi casi, è necessario progettare un sistema di reporting e il ripristino separato per gli errori.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-300">In those cases, you must design a separate reporting and recovery system for failures.</span></span>

<span data-ttu-id="f2b5b-301">Nella versione iniziale di eShopOnContainers, si è deciso di utilizzare l'elaborazione di comandi sincroni, avviata da richieste HTTP e basato su questo modello mediatore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-301">In the initial version of eShopOnContainers, we decided to use synchronous command processing, started from HTTP requests and driven by the Mediator pattern.</span></span> <span data-ttu-id="f2b5b-302">Che consente di restituire l'esito positivo o negativo del processo, come in facilmente il [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementazione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-302">That easily allows you to return the success or failure of the process, as in the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementation.</span></span>

<span data-ttu-id="f2b5b-303">In ogni caso, deve trattarsi di una decisione in base ai requisiti di business dell'applicazione o del microservizio.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-303">In any case, this should be a decision based on your application’s or microservice’s business requirements.</span></span>

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a><span data-ttu-id="f2b5b-304">Implementazione della pipeline di processo del comando con un criterio di mediatore (MediatR)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-304">Implementing the command process pipeline with a mediator pattern (MediatR)</span></span>

<span data-ttu-id="f2b5b-305">Come un'implementazione di esempio, questa guida vengono proposte tramite la pipeline in-process in base al modello mediatore per l'inserimento di comando di unità e routing, in memoria, per i gestori di comando corretto.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-305">As a sample implementation, this guide proposes using the in-process pipeline based on the Mediator pattern to drive command ingestion and routing them, in memory, to the right command handlers.</span></span> <span data-ttu-id="f2b5b-306">La guida propone inoltre l'applicazione gli elementi Decorator o [comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) per separare le problematiche a montaggio incrociato.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-306">The guide also proposes applying decorators or [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) in order to separate cross-cutting concerns.</span></span>

<span data-ttu-id="f2b5b-307">Per l'implementazione di .NET Core, sono disponibili più librerie di open source disponibili che implementano il modello mediatore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-307">For implementation in .NET Core, there are multiple open-source libraries available that implement the Mediator pattern.</span></span> <span data-ttu-id="f2b5b-308">La libreria utilizzata in questa guida è il [MediatR](https://github.com/jbogard/MediatR) libreria open source (creato dal Jimmy Bogard), ma è possibile utilizzare un altro approccio.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-308">The library used in this guide is the [MediatR](https://github.com/jbogard/MediatR) open-source library (created by Jimmy Bogard), but you could use another approach.</span></span> <span data-ttu-id="f2b5b-309">MediatR è una libreria di piccola e semplice che consente di elaborare messaggi in memoria come un comando, durante l'applicazione di comportamenti o gli elementi Decorator.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-309">MediatR is a small and simple library that allows you to process in-memory messages like a command, while applying decorators or behaviors.</span></span>

<span data-ttu-id="f2b5b-310">Usando il modello mediatore consente di ridurre l'accoppiamento e per isolare i problemi del lavoro richiesto, durante la connessione automatica al gestore che esegue il lavoro, in questo caso, per i gestori di comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-310">Using the Mediator pattern helps you to reduce coupling and to isolate the concerns of the requested work, while automatically connecting to the handler that performs that work—in this case, to command handlers.</span></span>

<span data-ttu-id="f2b5b-311">Un altro buon motivo per utilizzare il modello mediatore stato descritto da Jimmy Bogard durante la revisione di questa guida:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-311">Another good reason to use the Mediator pattern was explained by Jimmy Bogard when reviewing this guide:</span></span>

<span data-ttu-id="f2b5b-312">Credo che potrebbe essere utile citare test qui: fornisce una finestra coerenza nice esplicitamente il comportamento del sistema.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-312">I think it might be worth mentioning testing here – it provides a nice consistent window into the behavior of your system.</span></span> <span data-ttu-id="f2b5b-313">Richiesta e risposta in uscita. È stata trovata l'aspetto molto utili nella creazione di un comportamento coerente di test.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-313">Request-in, response-out. We’ve found that aspect quite valuable in building consistently behaving tests.</span></span>

<span data-ttu-id="f2b5b-314">In primo luogo, possiamo osservare per il codice del controller in cui è in realtà utilizzerebbe l'oggetto mediatore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-314">First, let us take a look to the controller code where you actually would use the mediator object.</span></span> <span data-ttu-id="f2b5b-315">Se non si utilizza l'oggetto mediatore, è necessario inserire tutte le dipendenze per tale controller, ad esempio un oggetto logger e altri utenti.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-315">If you were not using the mediator object, you would need to inject all the dependencies for that controller, things like a logger object and others.</span></span> <span data-ttu-id="f2b5b-316">Pertanto, il costruttore sarà piuttosto complesso.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-316">Therefore, the constructor would be quite complicated.</span></span> <span data-ttu-id="f2b5b-317">D'altra parte, se si utilizza l'oggetto mediatore, il costruttore del controller può essere molto più semplice, con pochi dipendenze anziché numerose dipendenze che si avrebbe se fosse uno per ogni operazione di montaggio incrociato, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-317">On the other hand, if you use the mediator object, the constructor of your controller can be a lot simpler, with just a few dependencies instead of many dependencies that you would have if you had one per cross-cutting operation, as in the following example:</span></span>

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

<span data-ttu-id="f2b5b-318">È possibile vedere che mediatore fornisce un costruttore di controller API Web pulito e pulito.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-318">You can see that the mediator provides a clean and lean Web API controller constructor.</span></span> <span data-ttu-id="f2b5b-319">Inoltre, all'interno dei metodi di controller, il codice per inviare un comando per l'oggetto mediatore è quasi una riga:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-319">In addition, within the controller methods, the code to send a command to the mediator object is almost one line:</span></span>

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

<span data-ttu-id="f2b5b-320">Affinché MediatR da tenere presenti le classi del gestore del comando, è necessario registrare le classi mediatore e le classi di gestore del comando nel contenitore di inversione di controllo.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-320">In order for MediatR to be aware of your command handler classes, you need to register the mediator classes and the command handler classes in your IoC container.</span></span> <span data-ttu-id="f2b5b-321">Per impostazione predefinita, MediatR utilizza Autofac come contenitore di inversione di controllo, ma è anche possibile utilizzare il contenitore di ASP.NET Core IoC predefinito o qualsiasi altro contenitore supportati da MediatR.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-321">By default, MediatR uses Autofac as the IoC container, but you can also use the built-in ASP.NET Core IoC container or any other container supported by MediatR.</span></span>

<span data-ttu-id="f2b5b-322">Il codice seguente viene illustrato come registrare i tipi e i comandi del mediatore quando si utilizzano moduli Autofac.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-322">The following code shows how to register Mediator’s types and commands when using Autofac modules.</span></span>

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

<span data-ttu-id="f2b5b-323">Poiché ogni gestore del comando implementa l'interfaccia generica IAsyncRequestHandler&lt;T&gt; e quindi controlla la RegisteredAssemblyTypes dell'oggetto, il gestore è in grado di correlare ogni comando con il gestore del comando, in quanto che relazione viene dichiarata nella classe CommandHandler, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-323">Because each command handler implements the interface with generic IAsyncRequestHandler&lt;T&gt; and then inspects the RegisteredAssemblyTypes object, the handler is able to relate each command with its command handler, because that relationship is stated in the CommandHandler class, as in the following example:</span></span>

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

<span data-ttu-id="f2b5b-324">Questo è il codice che mette in correlazione i comandi e gestori di comandi.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-324">This is the code that correlates commands with command handlers.</span></span> <span data-ttu-id="f2b5b-325">Il gestore è solo una classe semplice, ma eredita da RequestHandler&lt;T&gt;, e MediatR garantisce viene richiamato con il payload corretto.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-325">The handler is just a simple class, but it inherits from RequestHandler&lt;T&gt;, and MediatR makes sure it gets invoked with the correct payload.</span></span>

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a><span data-ttu-id="f2b5b-326">L'applicazione a montaggio incrociato problemi durante l'elaborazione dei comandi con gli schemi mediatore e Decorator</span><span class="sxs-lookup"><span data-stu-id="f2b5b-326">Applying cross-cutting concerns when processing commands with the Mediator and Decorator patterns</span></span>

<span data-ttu-id="f2b5b-327">Un ulteriore elemento: la possibilità di applicare a montaggio incrociato riguarda la pipeline mediatore.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-327">There is one more thing: being able to apply cross-cutting concerns to the mediator pipeline.</span></span> <span data-ttu-id="f2b5b-328">È inoltre possibile visualizzare il codice del modulo registrazione Autofac fine come si sta registrando un elemento decorator del tipo, in particolare, una classe LogDecorator personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-328">You can also see at the end of the Autofac registration module code how it is registering a decorator type, specifically, a custom LogDecorator class.</span></span>

<span data-ttu-id="f2b5b-329">Tenere presente che una versione futura di eShopOnContainers eseguirà la migrazione [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) e spostare [comportamenti](https://github.com/jbogard/MediatR/wiki/Behaviors) anziché gli elementi Decorator.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-329">Again, note that a future version of eShopOnContainers it will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

<span data-ttu-id="f2b5b-330">Che [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) classe può essere implementata come il codice seguente, che registra le informazioni sul gestore del comando in esecuzione e se è riuscito o meno.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-330">That [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class can be implemented as the following code, which logs information about the command handler being executed and whether it was successful or not.</span></span>

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

<span data-ttu-id="f2b5b-331">Solo mediante l'implementazione di questa classe decorator e tramite la pipeline con esso, tutti i comandi di elaborazione tramite MediatR effettuerà l'accesso informazioni relative all'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-331">Just by implementing this decorator class and by decorating the pipeline with it, all the commands processed through MediatR will be logging information about the execution.</span></span>

<span data-ttu-id="f2b5b-332">Il eShopOnContainers ordinamento microservizio si applica anche un secondo elemento decorator per eseguire le convalide di base, il [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) classe da cui dipende il [FluentValidation](https://github.com/JeremySkinner/FluentValidation) libreria, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-332">The eShopOnContainers ordering microservice also applies a second decorator for basic validations, the [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class that relies on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, as shown in the following code:</span></span>

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

<span data-ttu-id="f2b5b-333">Quindi, in base il [FluentValidation](https://github.com/JeremySkinner/FluentValidation) libreria, creata convalida per i dati passati con CreateOrderCommand, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f2b5b-333">Then, based on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, we created validation for the data passed with CreateOrderCommand, as in the following code:</span></span>

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

<span data-ttu-id="f2b5b-334">È possibile creare le convalide aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-334">You could create additional validations.</span></span> <span data-ttu-id="f2b5b-335">Questo è un modo molto pulito ed elegante per implementare le convalide di comando.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-335">This is a very clean and elegant way to implement your command validations.</span></span>

<span data-ttu-id="f2b5b-336">In modo analogo, è possibile implementare altri elementi Decorator per aspetti aggiuntivi o problemi di montaggio incrociato che si desidera applicare ai comandi durante la loro gestione.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-336">In a similar way, you could implement other decorators for additional aspects or cross-cutting concerns that you want to apply to commands when handling them.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="f2b5b-337">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f2b5b-337">Additional resources</span></span>

##### <a name="the-mediator-pattern"></a><span data-ttu-id="f2b5b-338">Il modello mediatore</span><span class="sxs-lookup"><span data-stu-id="f2b5b-338">The mediator pattern</span></span>

-   <span data-ttu-id="f2b5b-339">**Modello mediatore**
    [*https://en.wikipedia.org/wiki/Mediator\_modello*](https://en.wikipedia.org/wiki/Mediator_pattern)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-339">**Mediator pattern**
[*https://en.wikipedia.org/wiki/Mediator\_pattern*](https://en.wikipedia.org/wiki/Mediator_pattern)</span></span>

##### <a name="the-decorator-pattern"></a><span data-ttu-id="f2b5b-340">Il modello di espressione decorator</span><span class="sxs-lookup"><span data-stu-id="f2b5b-340">The decorator pattern</span></span>

-   <span data-ttu-id="f2b5b-341">**Modello di espressione Decorator**
    [*https://en.wikipedia.org/wiki/Decorator\_modello*](https://en.wikipedia.org/wiki/Decorator_pattern)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-341">**Decorator pattern**
[*https://en.wikipedia.org/wiki/Decorator\_pattern*](https://en.wikipedia.org/wiki/Decorator_pattern)</span></span>

##### <a name="mediatr-jimmy-bogard"></a><span data-ttu-id="f2b5b-342">MediatR (Jimmy Bogard)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-342">MediatR (Jimmy Bogard)</span></span>

-   <span data-ttu-id="f2b5b-343">**MediatR.**</span><span class="sxs-lookup"><span data-stu-id="f2b5b-343">**MediatR.**</span></span> <span data-ttu-id="f2b5b-344">Repository di GitHub.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-344">GitHub repo.</span></span>
    [<span data-ttu-id="f2b5b-345">*https://github.com/jbogard/MediatR*</span><span class="sxs-lookup"><span data-stu-id="f2b5b-345">*https://github.com/jbogard/MediatR*</span></span>](https://github.com/jbogard/MediatR)

-   <span data-ttu-id="f2b5b-346">**CQRS con MediatR e AutoMapper**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-346">**CQRS with MediatR and AutoMapper**
[*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span></span>

-   <span data-ttu-id="f2b5b-347">**Inserire i controller su un cibo: post e comandi. ** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-347">**Put your controllers on a diet: POSTs and commands.**
[*https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span></span>

-   <span data-ttu-id="f2b5b-348">**Affrontare i problemi di montaggio incrociato con una pipeline mediatore**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-348">**Tackling cross-cutting concerns with a mediator pipeline**
[*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span></span>

-   <span data-ttu-id="f2b5b-349">**CQRS e REST: abbina**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-349">**CQRS and REST: the perfect match**
[*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span></span>

-   <span data-ttu-id="f2b5b-350">**Esempi di Pipeline MediatR**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-350">**MediatR Pipeline Examples**
[*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span></span>

-   <span data-ttu-id="f2b5b-351">**Sezione verticale degli strumenti di Test per MediatR e ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*</span><span class="sxs-lookup"><span data-stu-id="f2b5b-351">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core**
*<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/> *</span></span>

-   <span data-ttu-id="f2b5b-352">**MediatR estensioni per l'aggiunta della dipendenza di Microsoft rilasciato**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-352">**MediatR Extensions for Microsoft Dependency Injection Released**
[*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span></span>

##### <a name="fluent-validation"></a><span data-ttu-id="f2b5b-353">Convalida Fluent</span><span class="sxs-lookup"><span data-stu-id="f2b5b-353">Fluent validation</span></span>

-   <span data-ttu-id="f2b5b-354">**Jeremy Skinner. FluentValidation.**</span><span class="sxs-lookup"><span data-stu-id="f2b5b-354">**Jeremy Skinner. FluentValidation.**</span></span> <span data-ttu-id="f2b5b-355">Repository di GitHub.</span><span class="sxs-lookup"><span data-stu-id="f2b5b-355">GitHub repo.</span></span>
    [<span data-ttu-id="f2b5b-356">*https://github.com/JeremySkinner/FluentValidation*</span><span class="sxs-lookup"><span data-stu-id="f2b5b-356">*https://github.com/JeremySkinner/FluentValidation*</span></span>](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
<span data-ttu-id="f2b5b-357">[Precedente] (microservice-application-layer-web-api-design.md) [Avanti] (... /Implement-resilient-Applications/index.MD)</span><span class="sxs-lookup"><span data-stu-id="f2b5b-357">[Previous] (microservice-application-layer-web-api-design.md) [Next] (../implement-resilient-applications/index.md)</span></span>
