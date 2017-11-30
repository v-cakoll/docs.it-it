---
title: Implementazione di un modello di dominio microservizio con .NET Core
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione di un modello di dominio microservizio con .NET Core
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 26c480a82ad7bb806734decebdfbe5b4a07998e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a><span data-ttu-id="24828-104">Implementazione di un modello di dominio microservizio con .NET Core</span><span class="sxs-lookup"><span data-stu-id="24828-104">Implementing a microservice domain model with .NET Core</span></span> 

<span data-ttu-id="24828-105">Nella sezione precedente, sono stati illustrati i principi di progettazione fondamentali e modelli per la progettazione di un modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="24828-105">In the previous section, the fundamental design principles and patterns for designing a domain model were explained.</span></span> <span data-ttu-id="24828-106">Ora è possibile esplorare i possibili modi per implementare il modello di dominio tramite .NET Core (C normale\# codice) e Core di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="24828-106">Now it is time to explore possible ways to implement the domain model by using .NET Core (plain C\# code) and EF Core.</span></span> <span data-ttu-id="24828-107">Si noti che il modello di dominio sarà costituito semplicemente il codice.</span><span class="sxs-lookup"><span data-stu-id="24828-107">Note that your domain model will be composed simply of your code.</span></span> <span data-ttu-id="24828-108">Solo i requisiti del modello Entity Framework Core, ma anche le dipendenze non reale disporrà in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="24828-108">It will have just the EF Core model requirements, but not real dependencies on EF.</span></span> <span data-ttu-id="24828-109">Non è necessario dipendenze rigide o riferimenti a componenti di base di EF o qualsiasi altra ORM nel modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="24828-109">You should not have hard dependencies or references to EF Core or any other ORM in your domain model.</span></span>

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a><span data-ttu-id="24828-110">Struttura modello di dominio in una libreria .NET Standard personalizzata</span><span class="sxs-lookup"><span data-stu-id="24828-110">Domain model structure in a custom .NET Standard library</span></span>

<span data-ttu-id="24828-111">L'organizzazione della cartella utilizzato per l'applicazione di riferimento eShopOnContainers viene illustrato il modello DDD per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24828-111">The folder organization used for the eShopOnContainers reference application demonstrates the DDD model for the application.</span></span> <span data-ttu-id="24828-112">È possibile che un'organizzazione di cartella diverso comunica in modo più chiaro delle scelte effettuate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="24828-112">You might find that a different folder organization more clearly communicates the design choices made for your application.</span></span> <span data-ttu-id="24828-113">Come si vede nella figura 9-10, nel modello di dominio di ordinamento sono presenti due funzioni di aggregazione, l'aggregazione di ordine e l'aggregazione dell'acquirente.</span><span class="sxs-lookup"><span data-stu-id="24828-113">As you can see in Figure 9-10, in the ordering domain model there are two aggregates, the order aggregate and the buyer aggregate.</span></span> <span data-ttu-id="24828-114">Ogni aggregazione è un gruppo di entità di dominio e gli oggetti di valore, anche se è possibile disporre di una funzione di aggregazione nonché costituito da un'entità di dominio singolo (aggregazione radice o entità radice).</span><span class="sxs-lookup"><span data-stu-id="24828-114">Each aggregate is a group of domain entities and value objects, although you could have an aggregate composed of a single domain entity (the aggregate root or root entity) as well.</span></span>

![](./media/image11.png)

<span data-ttu-id="24828-115">**Figura 9-10**.</span><span class="sxs-lookup"><span data-stu-id="24828-115">**Figure 9-10**.</span></span> <span data-ttu-id="24828-116">Struttura modello di dominio per l'ordinamento microservizio in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="24828-116">Domain model structure for the ordering microservice in eShopOnContainers</span></span>

<span data-ttu-id="24828-117">Inoltre, il livello del modello di dominio include i contratti di repository (interfacce) che sono i requisiti dell'infrastruttura del modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="24828-117">Additionally, the domain model layer includes the repository contracts (interfaces) that are the infrastructure requirements of your domain model.</span></span> <span data-ttu-id="24828-118">In altre parole, queste interfacce express quali repository deve implementare il livello di infrastruttura e in che modo.</span><span class="sxs-lookup"><span data-stu-id="24828-118">In other words, these interfaces express what repositories the infrastructure layer must implement and how.</span></span> <span data-ttu-id="24828-119">È importante che l'implementazione degli archivi di essere posizionato di fuori di livello del modello di dominio, nella libreria di livello di infrastruttura, quindi il livello del modello di dominio è "contaminato" dagli API o le classi di tecnologie di infrastruttura, ad esempio Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="24828-119">It is critical that the implementation of the repositories be placed outside of the domain model layer, in the infrastructure layer library, so the domain model layer is not “contaminated” by API or classes from infrastructure technologies, like Entity Framework.</span></span>

<span data-ttu-id="24828-120">È inoltre possibile visualizzare un [SeedWork](https://martinfowler.com/bliki/Seedwork.html) cartella che contiene le classi base personalizzate che è possibile utilizzare come base per le entità di dominio e il valore di oggetti, pertanto non è il codice ridondante nella classe di oggetti di ciascun dominio.</span><span class="sxs-lookup"><span data-stu-id="24828-120">You can also see a [SeedWork](https://martinfowler.com/bliki/Seedwork.html) folder that contains custom base classes that you can use as a base for your domain entities and value objects, so you do not have redundant code in each domain’s object class.</span></span>

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a><span data-ttu-id="24828-121">Strutturazione di aggregazioni in una libreria .NET Standard personalizzata</span><span class="sxs-lookup"><span data-stu-id="24828-121">Structuring aggregates in a custom .NET Standard library</span></span>

<span data-ttu-id="24828-122">Un'aggregazione fa riferimento a un cluster di oggetti dominio raggruppati in modo da corrispondere la consistenza delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="24828-122">An aggregate refers to a cluster of domain objects grouped together to match transactional consistency.</span></span> <span data-ttu-id="24828-123">Tali oggetti possono essere le istanze di entità (uno dei quali è la radice di aggregazione o l'entità principale) e tutti gli oggetti valore aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="24828-123">Those objects could be instances of entities (one of which is the aggregate root or root entity) plus any additional value objects.</span></span>

<span data-ttu-id="24828-124">Consistenza transazionale significa che una funzione di aggregazione è garantito che siano coerenti e aggiornato alla fine di un'azione di business.</span><span class="sxs-lookup"><span data-stu-id="24828-124">Transactional consistency means that an aggregate is guaranteed to be consistent and up to date at the end of a business action.</span></span> <span data-ttu-id="24828-125">Ad esempio, l'aggregazione di ordine dal eShopOnContainers ordinamento microservizio modello di dominio è costituito da come illustrato nella figura 9-11.</span><span class="sxs-lookup"><span data-stu-id="24828-125">For example, the order aggregate from the eShopOnContainers ordering microservice domain model is composed as shown in Figure 9-11.</span></span>

![](./media/image12.png)

<span data-ttu-id="24828-126">**Figura 9-11**.</span><span class="sxs-lookup"><span data-stu-id="24828-126">**Figure 9-11**.</span></span> <span data-ttu-id="24828-127">L'ordine di aggregata nella soluzione Visual Studio</span><span class="sxs-lookup"><span data-stu-id="24828-127">The order aggregate in Visual Studio solution</span></span>

<span data-ttu-id="24828-128">Se si apre un file in una cartella di aggregazione, è possibile vedere come è contrassegnato come classe base o interfaccia, come oggetto di entità o un valore, come implementato nel [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) cartella.</span><span class="sxs-lookup"><span data-stu-id="24828-128">If you open any of the files in an aggregate folder, you can see how it is marked as either a custom base class or interface, like entity or value object, as implemented in the [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) folder.</span></span>

## <a name="implementing-domain-entities-as-poco-classes"></a><span data-ttu-id="24828-129">Implementazione di entità di dominio come classi POCO</span><span class="sxs-lookup"><span data-stu-id="24828-129">Implementing domain entities as POCO classes</span></span>

<span data-ttu-id="24828-130">Implementare un modello di dominio in .NET creando classi POCO che implementano le entità di dominio.</span><span class="sxs-lookup"><span data-stu-id="24828-130">You implement a domain model in .NET by creating POCO classes that implement your domain entities.</span></span> <span data-ttu-id="24828-131">Nell'esempio seguente, la classe Order è definita come un'entità e anche come directory radice dell'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="24828-131">In the following example, the Order class is defined as an entity and also as an aggregate root.</span></span> <span data-ttu-id="24828-132">Poiché la classe Order deriva dalla classe di base di entità, è possibile riutilizzare il codice comune correlate alle entità.</span><span class="sxs-lookup"><span data-stu-id="24828-132">Because the Order class derives from the Entity base class, it can reuse common code related to entities.</span></span> <span data-ttu-id="24828-133">Tenere presente che queste classi base e interfacce definite dall'utente nel progetto di modello di dominio, pertanto il codice, non il codice dell'infrastruttura da ORM come Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="24828-133">Bear in mind that these base classes and interfaces are defined by you in the domain model project, so it is your code, not infrastructure code from an ORM like EF.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 1.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    public int BuyerId { get; private set; }
    public DateTime OrderDate { get; private set; }
    public int StatusId { get; private set; }
    public ICollection<OrderItem> OrderItems { get; private set; }
    public Address ShippingAddress { get; private set; }
    public int PaymentId { get; private set; }
    protected Order() { } //Design constraint needed only by EF Core
    public Order(int buyerId, int paymentId)
    {
        BuyerId = buyerId;
        PaymentId = paymentId;
        StatusId = OrderStatus.InProcess.Id;
        OrderDate = DateTime.UtcNow;
        OrderItems = new List<OrderItem>();
    }

    public void AddOrderItem(productName,
        pictureUrl,
        unitPrice,
        discount,
        units)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...
        OrderItem item = new OrderItem(this.Id, ProductId, productName,
            pictureUrl, unitPrice, discount, units);
  
        OrderItems.Add(item);
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

<span data-ttu-id="24828-134">È importante notare che questa è un'entità di dominio implementata come classe POCO.</span><span class="sxs-lookup"><span data-stu-id="24828-134">It is important to note that this is a domain entity implemented as a POCO class.</span></span> <span data-ttu-id="24828-135">Non dispone di qualsiasi dipendenza diretta in Entity Framework Core o qualsiasi altro framework di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="24828-135">It does not have any direct dependency on Entity Framework Core or any other infrastructure framework.</span></span> <span data-ttu-id="24828-136">Questa implementazione è come dovrebbe essere, semplicemente C\# codice che implementa un modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="24828-136">This implementation is as it should be, just C\# code implementing a domain model.</span></span>

<span data-ttu-id="24828-137">Inoltre, la classe è decorata con un'interfaccia denominata IAggregateRoot.</span><span class="sxs-lookup"><span data-stu-id="24828-137">In addition, the class is decorated with an interface named IAggregateRoot.</span></span> <span data-ttu-id="24828-138">Tale interfaccia è un'interfaccia vuota, detta anche un *interfaccia marcatore*, che viene utilizzato solo per indicare che questa classe di entità è anche una radice di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="24828-138">That interface is an empty interface, sometimes called a *marker interface*, that is used just to indicate that this entity class is also an aggregate root.</span></span>

<span data-ttu-id="24828-139">Un'interfaccia marcatore talvolta viene considerata come un anti-pattern; Tuttavia, è anche un modo pulito per contrassegnare una classe, in particolare quando tale interfaccia potrà essere in evoluzione.</span><span class="sxs-lookup"><span data-stu-id="24828-139">A marker interface is sometimes considered as an anti-pattern; however, it is also a clean way to mark a class, especially when that interface might be evolving.</span></span> <span data-ttu-id="24828-140">Un attributo può essere scelta per il marcatore, ma è più rapido, vedere la classe di base (entità) accanto all'interfaccia IAggregate anziché inserire un marcatore di attributo di aggregazione di sopra della classe.</span><span class="sxs-lookup"><span data-stu-id="24828-140">An attribute could be the other choice for the marker, but it is quicker to see the base class (Entity) next to the IAggregate interface instead of putting an Aggregate attribute marker above the class.</span></span> <span data-ttu-id="24828-141">In ogni caso è un metter di preferenze.</span><span class="sxs-lookup"><span data-stu-id="24828-141">It is a metter of preferences, in any case.</span></span>

<span data-ttu-id="24828-142">Con un mezzo principale di aggregazione che la maggior parte del codice correlate coerenza e regole di business di entità dell'aggregazione devono essere implementate come metodi nella classe Order radice di aggregazione (ad esempio, AddOrderItem quando si aggiunge un oggetto OrderItem all'aggregazione) .</span><span class="sxs-lookup"><span data-stu-id="24828-142">Having an aggregate root means that most of the code related to consistency and business rules of the aggregate’s entities should be implemented as methods in the Order aggregate root class (for example, AddOrderItem when adding an OrderItem object to the aggregate).</span></span> <span data-ttu-id="24828-143">È consigliabile non creare o aggiornare oggetti OrderItems in modo indipendente o direttamente. la classe AggregateRoot deve mantenere la coerenza di qualsiasi operazione di aggiornamento con le entità figlio e di controllo.</span><span class="sxs-lookup"><span data-stu-id="24828-143">You should not create or update OrderItems objects independently or directly; the AggregateRoot class must keep control and consistency of any update operation against its child entities.</span></span>

<span data-ttu-id="24828-144">Ad esempio, è necessario *non* eseguire le operazioni seguenti da qualsiasi classe livello applicazione o del metodo del gestore di comando:</span><span class="sxs-lookup"><span data-stu-id="24828-144">For example, you should *not* do the following from any command handler method or application layer class:</span></span>

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

<span data-ttu-id="24828-145">In questo caso, il metodo Add è semplicemente un'operazione di aggiunta di dati, con accesso diretto alla raccolta OrderItems.</span><span class="sxs-lookup"><span data-stu-id="24828-145">In this case, the Add method is purely an operation to add data, with direct access to the OrderItems collection.</span></span> <span data-ttu-id="24828-146">Pertanto, la maggior parte della logica di dominio, regole o le convalide correlato che l'operazione con le entità figlio verrà distribuito tra il livello di applicazione (gestori di comandi e i controller API Web).</span><span class="sxs-lookup"><span data-stu-id="24828-146">Therefore, most of the domain logic, rules, or validations related to that operation with the child entities will be spread across the application layer (command handlers and Web API controllers).</span></span>

<span data-ttu-id="24828-147">Se si passa per la radice di aggregazione, la radice di aggregazione non garantisce l'invarianti, la validità o la consistenza.</span><span class="sxs-lookup"><span data-stu-id="24828-147">If you go around the aggregate root, the aggregate root cannot guarantee its invariants, its validity, or its consistency.</span></span> <span data-ttu-id="24828-148">Sarà infine necessario assai complicato o codice di script transazionali.</span><span class="sxs-lookup"><span data-stu-id="24828-148">Eventually you will have spaghetti code or transactional script code.</span></span>

<span data-ttu-id="24828-149">Per seguire pattern DDD, le entità non può avere un Setter pubblico in qualsiasi proprietà di entità.</span><span class="sxs-lookup"><span data-stu-id="24828-149">To follow DDD patterns, entities must not have public setters in any entity property.</span></span> <span data-ttu-id="24828-150">Le modifiche in un'entità devono essere dovute a metodi espliciti con linguaggio universale esplicite sulla modifica che sono in esecuzione nell'entità.</span><span class="sxs-lookup"><span data-stu-id="24828-150">Changes in an entity should be driven by explicit methods with explicit ubiquitous language about the change they are performing in the entity.</span></span>

<span data-ttu-id="24828-151">Inoltre, raccolte all'interno dell'entità (ad esempio, gli elementi di ordine) devono essere proprietà di sola lettura (il metodo AsReadOnly descritto più avanti).</span><span class="sxs-lookup"><span data-stu-id="24828-151">Furthermore, collections within the entity (like the order items) should be read-only properties (the AsReadOnly method explained later).</span></span> <span data-ttu-id="24828-152">È necessario eseguire l'aggiornamento solo da all'interno di metodi della classe radice di aggregazione o i metodi di entità figlio.</span><span class="sxs-lookup"><span data-stu-id="24828-152">You should be able to update it only from within the aggregate root class methods or the child entity methods.</span></span>

<span data-ttu-id="24828-153">Come si può notare nel codice per la radice di aggregazione di ordine, tutti i metodi di impostazione deve essere almeno di sola lettura o privata esternamente, in modo che qualsiasi operazione con i dati dell'entità o le entità figlio deve essere eseguita tramite i metodi nella classe di entità.</span><span class="sxs-lookup"><span data-stu-id="24828-153">As you can see in the code for the Order aggregate root, all setters should be private or at least read-only externally, so that any operation against the entity’s data or its child entities has to be performed through methods in the entity class.</span></span> <span data-ttu-id="24828-154">Questa viene mantenuta la coerenza in modo controllato e orientata agli oggetti anziché implementare codice di script transazionali.</span><span class="sxs-lookup"><span data-stu-id="24828-154">This maintains consistency in a controlled and object-oriented way instead of implementing transactional script code.</span></span>

<span data-ttu-id="24828-155">Frammento di codice seguente viene illustrato il modo corretto per l'operazione di aggiunta di un oggetto OrderItem per l'aggregazione di ordine del codice.</span><span class="sxs-lookup"><span data-stu-id="24828-155">The following code snippet shows the proper way to code the task of adding an OrderItem object to the Order aggregate.</span></span>

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

<span data-ttu-id="24828-156">In questo frammento di codice, la maggior parte della convalida o logica relative alla creazione di un oggetto OrderItem sarà sotto il controllo della radice di aggregazione dell'ordine, nel metodo AddOrderItem, soprattutto convalide e logica correlati agli altri elementi in di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="24828-156">In this snippet, most of the validations or logic related to the creation of an OrderItem object will be under the control of the Order aggregate root—in the AddOrderItem method—especially validations and logic related to other elements in the aggregate.</span></span> <span data-ttu-id="24828-157">Ad esempio, si potrebbe ottenere lo stesso elemento prodotto come risultato di più chiamate a AddOrderItem.</span><span class="sxs-lookup"><span data-stu-id="24828-157">For instance, you might get the same product item as the result of multiple calls to AddOrderItem.</span></span> <span data-ttu-id="24828-158">In quel metodo, è possibile esaminare gli elementi del prodotto e consolidare gli stessi elementi di prodotto in un singolo oggetto OrderItem con più unità.</span><span class="sxs-lookup"><span data-stu-id="24828-158">In that method, you could examine the product items and consolidate the same product items into a single OrderItem object with several units.</span></span> <span data-ttu-id="24828-159">Inoltre, se sono presenti gli importi di sconto differenti, ma l'ID prodotto è lo stesso, sarebbe probabilmente applicare lo sconto maggiore.</span><span class="sxs-lookup"><span data-stu-id="24828-159">Additionally, if there are different discount amounts but the product ID is the same, you would likely apply the higher discount.</span></span> <span data-ttu-id="24828-160">Questo principio si applica a qualsiasi altra logica di dominio per l'oggetto OrderItem.</span><span class="sxs-lookup"><span data-stu-id="24828-160">This principle applies to any other domain logic for the OrderItem object.</span></span>

<span data-ttu-id="24828-161">Inoltre, la nuova operazione OrderItem(params) che controllata ed eseguita dal metodo AddOrderItem dalla radice di aggregazione di ordine.</span><span class="sxs-lookup"><span data-stu-id="24828-161">In addition, the new OrderItem(params) operation will also be controlled and performed by the AddOrderItem method from the Order aggregate root.</span></span> <span data-ttu-id="24828-162">Pertanto, la maggior parte della logica o convalide correlato che l'operazione (in particolare tutto ciò che influisce sulla coerenza tra altre entità figlio) verrà ritentata in un'unica posizione nell'ambito della radice di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="24828-162">Therefore, most of the logic or validations related to that operation (especially anything that impacts the consistency between other child entities) will be in a single place within the aggregate root.</span></span> <span data-ttu-id="24828-163">Che è lo scopo principale del modello radice di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="24828-163">That is the ultimate purpose of the aggregate root pattern.</span></span>

<span data-ttu-id="24828-164">Quando si utilizza Entity Framework 1.1, un'entità DDD può essere espresso meglio, perché una delle nuove funzionalità di Entity Framework Core 1.1 è che consenta [mapping ai campi](https://docs.microsoft.com/ef/core/modeling/backing-field) oltre alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="24828-164">When you use Entity Framework 1.1, a DDD entity can be better expressed because one of the new features of Entity Framework Core 1.1 is that it allows [mapping to fields](https://docs.microsoft.com/ef/core/modeling/backing-field) in addition to properties.</span></span> <span data-ttu-id="24828-165">Ciò è utile quando si proteggono le raccolte di entità figlio o gli oggetti di valore.</span><span class="sxs-lookup"><span data-stu-id="24828-165">This is useful when protecting collections of child entities or value objects.</span></span> <span data-ttu-id="24828-166">Con questa funzionalità avanzata, è possibile utilizzare i campi privati semplici anziché le proprietà e consente di implementare gli aggiornamenti per la raccolta di campi nei metodi pubblici e fornire l'accesso di sola lettura tramite il metodo AsReadOnly.</span><span class="sxs-lookup"><span data-stu-id="24828-166">With this enhancement, you can use simple private fields instead of properties and you can implement any update to the field collection in public methods and provide read-only access through the AsReadOnly method.</span></span>

<span data-ttu-id="24828-167">In DDD che si desidera aggiornare l'entità solo tramite i metodi di entità (o costruttore) per controllare qualsiasi lingua e la coerenza dei dati, pertanto le proprietà sono definite solo con una funzione di accesso get.</span><span class="sxs-lookup"><span data-stu-id="24828-167">In DDD you want to update the entity only through methods in the entity (or the constructor) in order to control any invariant and the consistency of the data, so properties are defined only with a get accessor.</span></span> <span data-ttu-id="24828-168">Le proprietà sono supportate da campi privati.</span><span class="sxs-lookup"><span data-stu-id="24828-168">The properties are backed by private fields.</span></span> <span data-ttu-id="24828-169">Membri privati è accessibile solo dall'interno della classe.</span><span class="sxs-lookup"><span data-stu-id="24828-169">Private members can only be accessed from within the class.</span></span> <span data-ttu-id="24828-170">Tuttavia, eccezione esiste uno: Core EF deve impostare anche questi campi.</span><span class="sxs-lookup"><span data-stu-id="24828-170">However, there one exception: EF Core needs to set these fields as well.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1 OR LATER
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    // DDD Patterns comment
    // Using private fields, allowed since EF Core 1.1, is a much better
    // encapsulation aligned with DDD aggregates and domain entities (instead of
    // properties and property collections)
    private bool _someOrderInternalState;
    private DateTime _orderDate;
    public Address Address { get; private set; }
    public Buyer Buyer { get; private set; }
    private int _buyerId;
    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    // DDD patterns comment
    // Using a private collection field is better for DDD aggregate encapsulation.
    // OrderItem objects cannot be added from outside the aggregate root
    // directly to the collection, but only through the
    // OrderAggrergateRoot.AddOrderItem method, which includes behavior.
    private readonly List<OrderItem> _orderItems;
    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();
    // Using List<>.AsReadOnly()
    // This will create a read-only wrapper around the private list so it is
    // protected against external updates. It's much cheaper than .ToList(),
    // because it will not have to copy all items in a new collection.
    // (Just one heap alloc for the wrapper instance)
    // https://msdn.microsoft.com/en-us/library/e78dcd75(v=vs.110).aspx
    public PaymentMethod PaymentMethod { get; private set; }
    private int _paymentMethodId;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.InProcess.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;
    }

    // DDD patterns comment
    // The Order aggregate root method AddOrderitem() should be the only way
    // to add items to the Order object, so that any behavior (discounts, etc.)
    // and validations are controlled by the aggregate root in order to
    // maintain consistency within the whole aggregate.
    public void AddOrderItem(int productId, string productName, decimal unitPrice,
        decimal discount, string pictureUrl, int units = 1)
    {
        // ...
        // Domain rules/logic here for adding OrderItem objects to the order
        // ...
        OrderItem item = new OrderItem(this.Id, productId, productName,
            pictureUrl, unitPrice, discount, units);
        OrderItems.Add(item);
    }

    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a><span data-ttu-id="24828-171">Il mapping delle proprietà solo con funzioni di accesso get per i campi nella tabella di database</span><span class="sxs-lookup"><span data-stu-id="24828-171">Mapping properties with only get accessors to the fields in the database table</span></span>

<span data-ttu-id="24828-172">Mapping di proprietà alle colonne della tabella di database non è una responsabilità di dominio, ma parte del livello di infrastruttura e la persistenza.</span><span class="sxs-lookup"><span data-stu-id="24828-172">Mapping properties to the database table columns is not a domain responsibility, but part of the infrastructure and persistence layer.</span></span> <span data-ttu-id="24828-173">È importante tenere presente questo qui solo per essere compatibile con le nuove funzionalità di Entity Framework 1.1 relativi a come è possibile modellare le entità.</span><span class="sxs-lookup"><span data-stu-id="24828-173">We mention this here just so you are aware of the new capabilities in EF 1.1 related to how you can model entities.</span></span> <span data-ttu-id="24828-174">Altre informazioni su questo argomento sono illustrati nella sezione dell'infrastruttura e la persistenza.</span><span class="sxs-lookup"><span data-stu-id="24828-174">Additional details on this topic are explained in the infrastructure and persistence section.</span></span>

<span data-ttu-id="24828-175">Quando si utilizza Entity Framework 1.0, all'interno di DbContext è necessario eseguire il mapping di proprietà che sono definite solo con metodi di richiamo ai campi effettivi nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="24828-175">When you use EF 1.0, within the DbContext you need to map the properties that are defined only with getters to the actual fields in the database table.</span></span> <span data-ttu-id="24828-176">Questa operazione viene eseguita con il metodo HasField della classe PropertyBuilder.</span><span class="sxs-lookup"><span data-stu-id="24828-176">This is done with the HasField method of the PropertyBuilder class.</span></span>

### <a name="mapping-fields-without-properties"></a><span data-ttu-id="24828-177">Mapping dei campi senza proprietà</span><span class="sxs-lookup"><span data-stu-id="24828-177">Mapping fields without properties</span></span>

<span data-ttu-id="24828-178">Con la nuova funzionalità di Entity Framework 1.1 di Core per eseguire il mapping di colonne a campi, è anche possibile non usare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="24828-178">With the new feature in EF Core 1.1 to map columns to fields, it is also possible to not use properties.</span></span> <span data-ttu-id="24828-179">In alternativa, è possibile mappare solo colonne di una tabella ai campi.</span><span class="sxs-lookup"><span data-stu-id="24828-179">Instead, you can just map columns from a table to fields.</span></span> <span data-ttu-id="24828-180">Un caso di utilizzo comune per questo oggetto è campi privati per uno stato interno che non devono essere accessibili all'esterno dell'entità.</span><span class="sxs-lookup"><span data-stu-id="24828-180">A common use case for this is private fields for an internal state that does not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="24828-181">Ad esempio, nell'esempio di codice precedente, il \_someOrderInternalState campo non dispone di alcuna proprietà correlate per un getter o setter.</span><span class="sxs-lookup"><span data-stu-id="24828-181">For example, in the preceding code example, the \_someOrderInternalState field has no related property for either a setter or getter.</span></span> <span data-ttu-id="24828-182">Tale campo verrà inoltre calcolato all'interno di logica di business dell'ordine e utilizzato dai metodi dell'ordine, ma deve essere resa persistente nel database anche.</span><span class="sxs-lookup"><span data-stu-id="24828-182">That field will also be calculated within the order’s business logic and used from the order’s methods, but it needs to be persisted in the database as well.</span></span> <span data-ttu-id="24828-183">In tal caso, in Entity Framework 1.1 è possibile eseguire il mapping di un campo senza una proprietà correlata a una colonna nel database.</span><span class="sxs-lookup"><span data-stu-id="24828-183">So, in EF 1.1 there is a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="24828-184">Anche questo è illustrato il [livello infrastruttura](#the-infrastructure-layer) sezione di questa Guida.</span><span class="sxs-lookup"><span data-stu-id="24828-184">This is also explained in the [Infrastructure layer](#the-infrastructure-layer) section of this guide.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="24828-185">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="24828-185">Additional resources</span></span>

-   <span data-ttu-id="24828-186">**Vaughn Vernon. Funzioni di aggregazione con DDD ed Entity Framework di modellazione.**</span><span class="sxs-lookup"><span data-stu-id="24828-186">**Vaughn Vernon. Modeling Aggregates with DDD and Entity Framework.**</span></span> <span data-ttu-id="24828-187">Si noti che questo *non* Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="24828-187">Note that this is *not* Entity Framework Core.</span></span>
    [<span data-ttu-id="24828-188">*https://vaughnvernon.co/?p=879*</span><span class="sxs-lookup"><span data-stu-id="24828-188">*https://vaughnvernon.co/?p=879*</span></span>](https://vaughnvernon.co/?p=879)

-   <span data-ttu-id="24828-189">**Julie Lerman. Codifica per la progettazione basati su dominio: suggerimenti per gli sviluppatori con stato attivo di dati**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span><span class="sxs-lookup"><span data-stu-id="24828-189">**Julie Lerman. Coding for Domain-Driven Design: Tips for Data-Focused Devs**
[*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span></span>

-   <span data-ttu-id="24828-190">**udi Dahan. Come creare completamente incapsulato i modelli di dominio**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span><span class="sxs-lookup"><span data-stu-id="24828-190">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="24828-191">[Precedente] (microservizio-dominio-model.md) [Avanti] (seedwork-domain-model-base-classes-interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="24828-191">[Previous] (microservice-domain-model.md) [Next] (seedwork-domain-model-base-classes-interfaces.md)</span></span>
