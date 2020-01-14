---
title: Seedwork (classi di base riutilizzabili e interfacce per il modello di dominio)
description: Architettura dei microservizi .NET per applicazioni .NET in contenitori | Usare il concetto di cartella SeedWork come punto di partenza per avviare l'implementazione di un modello di dominio orientato a DDD.
ms.date: 10/08/2018
ms.openlocfilehash: 491ff39f493a8f5ab192dc4a8376f560a8a7624b
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937165"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="d692e-103">Seedwork (classi di base riutilizzabili e interfacce per il modello di dominio)</span><span class="sxs-lookup"><span data-stu-id="d692e-103">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="d692e-104">La cartella della soluzione contiene una cartella denominata *SeedWork*.</span><span class="sxs-lookup"><span data-stu-id="d692e-104">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="d692e-105">Tale cartella contiene classi di base personalizzate che è possibile usare come base per le entità di dominio e gli oggetti valore.</span><span class="sxs-lookup"><span data-stu-id="d692e-105">This folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="d692e-106">È possibile usare queste classi di base per evitare codice ridondante in ogni classe di oggetti del dominio.</span><span class="sxs-lookup"><span data-stu-id="d692e-106">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="d692e-107">La cartella per questi tipi di classi è denominata *SeedWork* e non *Framework* o qualcosa di simile.</span><span class="sxs-lookup"><span data-stu-id="d692e-107">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="d692e-108">Viene denominata *SeedWork* perché la cartella contiene solo un piccolo subset di classi riutilizzabili che non può effettivamente essere considerato un framework.</span><span class="sxs-lookup"><span data-stu-id="d692e-108">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="d692e-109">Il termine *Seedwork* è stato introdotto da [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) ed è diventato noto grazie a [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html). Questa cartella può tuttavia essere denominata Common, SharedKernel o avere un nome simile.</span><span class="sxs-lookup"><span data-stu-id="d692e-109">*Seedwork* is a term introduced by [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="d692e-110">La figura 7-12 illustra le classi che costituiscono la cartella SeedWork del modello di dominio nel microservizio degli ordini.</span><span class="sxs-lookup"><span data-stu-id="d692e-110">Figure 7-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="d692e-111">La cartella contiene alcune classi di base personalizzate come Entity, ValueObject ed Enumeration e alcune interfacce.</span><span class="sxs-lookup"><span data-stu-id="d692e-111">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="d692e-112">Queste interfacce (IRepository e IUnitOfWork) indicano al livello infrastruttura le implementazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="d692e-112">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="d692e-113">Queste interfacce vengono usate anche dal livello dell'applicazione tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="d692e-113">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

:::image type="complex" source="./media/seedwork-domain-model-base-classes-interfaces/vs-solution-seedwork-classes.png" alt-text="Screenshot delle classi contenute nella cartella seeding.":::
<span data-ttu-id="d692e-115">Contenuto dettagliato della cartella seeding che contiene le classi e le interfacce di base: Entity.cs, Enumeration.cs, IAggregateRoot.cs, IRepository.cs, IUnitOfWork.cs e ValueObject.cs.</span><span class="sxs-lookup"><span data-stu-id="d692e-115">The detailed contents of the SeedWork folder, containing base classes and interfaces: Entity.cs, Enumeration.cs, IAggregateRoot.cs, IRepository.cs, IUnitOfWork.cs, and ValueObject.cs.</span></span>
:::image-end:::

<span data-ttu-id="d692e-116">**Figura 7-12**.</span><span class="sxs-lookup"><span data-stu-id="d692e-116">**Figure 7-12**.</span></span> <span data-ttu-id="d692e-117">Set di esempio di classi di base e interfacce nella cartella"Seedwork" per il modello di dominio</span><span class="sxs-lookup"><span data-stu-id="d692e-117">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="d692e-118">Si tratta di un tipo di riutilizzo che può essere copiato e incollato e che molti sviluppatori condividono nei progetti. Non è un framework formale.</span><span class="sxs-lookup"><span data-stu-id="d692e-118">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="d692e-119">È possibile avere cartelle Seedwork in qualsiasi livello o libreria.</span><span class="sxs-lookup"><span data-stu-id="d692e-119">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="d692e-120">Se il set di classi e interfacce aumenta di dimensioni, potrebbe essere tuttavia necessario creare un'unica libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="d692e-120">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="d692e-121">Classe di base Entity personalizzata</span><span class="sxs-lookup"><span data-stu-id="d692e-121">The custom Entity base class</span></span>

<span data-ttu-id="d692e-122">Il codice seguente è un esempio di una classe di base Entity in cui è possibile inserire il codice che può essere usato allo stesso modo da qualsiasi entità di dominio, ad esempio dall'ID entità, dagli [operatori di uguaglianza](../../../csharp/language-reference/operators/equality-operators.md), da un elenco di eventi di dominio per ogni entità e così via.</span><span class="sxs-lookup"><span data-stu-id="d692e-122">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](../../../csharp/language-reference/operators/equality-operators.md), a domain event list per entity, etc.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE (1.1 and later)
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;
    private List<INotification> _domainEvents;
    public virtual int Id
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public List<INotification> DomainEvents => _domainEvents;
    public void AddDomainEvent(INotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<INotification>();
        _domainEvents.Add(eventItem);
    }
    public void RemoveDomainEvent(INotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }

    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() ^ 31;
            // XOR for random distribution. See:
            // https://docs.microsoft.com/archive/blogs/ericlippert/guidelines-and-rules-for-gethashcode
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }
    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null));
        else
            return left.Equals(right);
    }
    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

<span data-ttu-id="d692e-123">Il codice precedente che usa un elenco di eventi di dominio per ogni entità viene spiegato nelle prossime sezioni che riguardano gli eventi di dominio.</span><span class="sxs-lookup"><span data-stu-id="d692e-123">The previous code using a domain event list per entity will be explained in the next sections when focusing on domain events.</span></span>

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="d692e-124">Contratti di repository (interfacce) nel livello del modello di dominio</span><span class="sxs-lookup"><span data-stu-id="d692e-124">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="d692e-125">I contratti di repository sono semplicemente interfacce .NET che esprimono i requisiti di contratto dei repository da usare per ogni aggregato.</span><span class="sxs-lookup"><span data-stu-id="d692e-125">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span>

<span data-ttu-id="d692e-126">I repository con codice di Entity Framework Core o qualsiasi altra dipendenza da infrastruttura e codice (Linq, SQL e così via), non devono essere implementati all'interno del modello di dominio, ma devono soltanto implementare le interfacce definite nel modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="d692e-126">The repositories themselves, with EF Core code or any other infrastructure dependencies and code (Linq, SQL, etc.), must not be implemented within the domain model; the repositories should only implement the interfaces you define in the domain model.</span></span>

<span data-ttu-id="d692e-127">Un modello che spiega questa pratica, vale a dire l'inserimento delle interfacce di repository nel livello del modello di dominio, è il modello noto come "Interfaccia separata".</span><span class="sxs-lookup"><span data-stu-id="d692e-127">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="d692e-128">Secondo quanto [spiega](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) Martin Fowler è importante "usare il modello Interfaccia separata per definire un'interfaccia in un pacchetto, ma implementarla in un altro pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d692e-128">As [explained](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="d692e-129">In questo modo il client che richiede la dipendenza all'interfaccia può essere totalmente ignaro dell'implementazione."</span><span class="sxs-lookup"><span data-stu-id="d692e-129">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="d692e-130">Il modello "Interfaccia separata" consente al livello dell'applicazione (in questo caso il progetto API Web per il microservizio) di dipendere dai requisiti definiti nel modello di dominio, ma di non avere una dipendenza diretta al livello infrastruttura/persistenza.</span><span class="sxs-lookup"><span data-stu-id="d692e-130">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="d692e-131">È anche possibile usare l'inserimento delle dipendenze per isolare l'implementazione, che viene definita nel livello infrastruttura/persistenza tramite i repository.</span><span class="sxs-lookup"><span data-stu-id="d692e-131">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="d692e-132">Nell'esempio seguente con l'interfaccia IOrderRepository vengono definite le operazioni che la classe OrderRepository deve implementare al livello di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="d692e-132">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="d692e-133">Nell'implementazione corrente dell'applicazione il codice deve soltanto aggiungere o aggiornare gli ordini nel database, poiché le query vengono suddivise in base all'approccio CQRS semplificato.</span><span class="sxs-lookup"><span data-stu-id="d692e-133">In the current implementation of the application, the code just needs to add or update orders to the database, since queries are split following the simplified CQRS approach.</span></span>

```csharp
// Defined at IOrderRepository.cs
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);

    void Update(Order order);

    Task<Order> GetAsync(int orderId);
}

// Defined at IRepository.cs (Part of the Domain Seedwork)
public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="d692e-134">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d692e-134">Additional resources</span></span>

- <span data-ttu-id="d692e-135">**Martin Fowler. Interfaccia separata.**</span><span class="sxs-lookup"><span data-stu-id="d692e-135">**Martin Fowler. Separated Interface.**</span></span> \
  <https://www.martinfowler.com/eaaCatalog/separatedInterface.html>

>[!div class="step-by-step"]
><span data-ttu-id="d692e-136">[Precedente](net-core-microservice-domain-model.md)
>[Successivo](implement-value-objects.md)</span><span class="sxs-lookup"><span data-stu-id="d692e-136">[Previous](net-core-microservice-domain-model.md)
[Next](implement-value-objects.md)</span></span>
