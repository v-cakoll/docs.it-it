---
title: Seedwork (riutilizzabili classi base e interfacce per il modello di dominio)
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Seedwork (riutilizzabili classi base e interfacce per il modello di dominio)
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 17602d94ea167997389a77f0d2358326258a8219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="08877-104">Seedwork (riutilizzabili classi base e interfacce per il modello di dominio)</span><span class="sxs-lookup"><span data-stu-id="08877-104">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="08877-105">La cartella della soluzione contiene un *SeedWork* cartella.</span><span class="sxs-lookup"><span data-stu-id="08877-105">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="08877-106">Il *SeedWork* cartella contiene le classi base personalizzate che è possibile utilizzare come base per le entità di dominio e gli oggetti di valore.</span><span class="sxs-lookup"><span data-stu-id="08877-106">The *SeedWork* folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="08877-107">Utilizzare queste classi di base in modo che non sia il codice ridondante nella classe di oggetti di ciascun dominio.</span><span class="sxs-lookup"><span data-stu-id="08877-107">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="08877-108">La cartella per questi tipi di classi è denominata *SeedWork* e non è *Framework*.</span><span class="sxs-lookup"><span data-stu-id="08877-108">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="08877-109">Viene chiamato *SeedWork* perché la cartella contiene solo un piccolo subset di classi riutilizzabili che realmente non può essere considerato un framework.</span><span class="sxs-lookup"><span data-stu-id="08877-109">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="08877-110">*Seedwork* è un termine dovuto [penne Michael](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) e resa nota da [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) ma è anche possibile specificare il nome cartella comune, SharedKernel, o simili.</span><span class="sxs-lookup"><span data-stu-id="08877-110">*Seedwork* is a term introduced by [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="08877-111">Figura 9-12 vengono illustrate le classi che costituiscono l'ordinamento microservizio seedwork del modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="08877-111">Figure 9-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="08877-112">Include alcune classi di base personalizzate come entità, ValueObject e di enumerazione, nonché alcune interfacce.</span><span class="sxs-lookup"><span data-stu-id="08877-112">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="08877-113">Queste interfacce (IRepository e IUnitOfWork) che indicano il livello infrastruttura sulle operazioni necessarie per essere implementato.</span><span class="sxs-lookup"><span data-stu-id="08877-113">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="08877-114">Queste interfacce vengono utilizzate anche tramite l'inserimento di dipendenze dal livello dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="08877-114">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

![](./media/image13.PNG)

<span data-ttu-id="08877-115">**Figura 9-12**.</span><span class="sxs-lookup"><span data-stu-id="08877-115">**Figure 9-12**.</span></span> <span data-ttu-id="08877-116">Un esempio di set di interfacce e classi di base "seedwork" modello di dominio</span><span class="sxs-lookup"><span data-stu-id="08877-116">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="08877-117">Questo è il tipo del riutilizzo di copia e Incolla che molti sviluppatori condividono tra progetti, non è un framework formale.</span><span class="sxs-lookup"><span data-stu-id="08877-117">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="08877-118">È possibile avere seedworks in qualsiasi livello o di una libreria.</span><span class="sxs-lookup"><span data-stu-id="08877-118">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="08877-119">Tuttavia, se il set di classi e interfacce Ottiene sufficientemente grande, potrebbe essere desiderato creare una libreria di classi singolo.</span><span class="sxs-lookup"><span data-stu-id="08877-119">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="08877-120">La classe di base di entità personalizzata</span><span class="sxs-lookup"><span data-stu-id="08877-120">The custom Entity base class</span></span>

<span data-ttu-id="08877-121">Il codice riportato di seguito è riportato un esempio di una classe di base di entità in cui è possibile inserire codice che può essere utilizzato esattamente come per qualsiasi entità di dominio, ad esempio l'ID entità, [gli operatori di uguaglianza](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx)e così via.</span><span class="sxs-lookup"><span data-stu-id="08877-121">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx), etc.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;

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
                _requestedHashCode = this.Id.GetHashCode() \^ 31;
            // XOR for random distribution. See:
            // http://blogs.msdn.com/b/ericlippert/archive/2011/02/28/guidelines-and-rules-for-gethashcode.aspx
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }

    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null)) ? true : false;
        else
            return left.Equals(right);
    }

    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="08877-122">Contratti di repository (interfacce) nel livello del modello di dominio</span><span class="sxs-lookup"><span data-stu-id="08877-122">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="08877-123">Contratti di repository sono semplicemente interfacce .NET che esprimono i requisiti del contratto dei repository da utilizzare per ogni funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="08877-123">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span> <span data-ttu-id="08877-124">I repository se stessi, con codice di base di Entity Framework o le altre dipendenze dell'infrastruttura e codice, non devono essere implementati all'interno del modello di dominio; i repository devono implementare solo le interfacce definite.</span><span class="sxs-lookup"><span data-stu-id="08877-124">The repositories themselves, with EF Core code or any other infrastructure dependencies and code, must not be implemented within the domain model; the repositories should only implement the interfaces you define.</span></span>

<span data-ttu-id="08877-125">Un modello correlato a questa prassi (ponendo le interfacce di repository nel livello del modello di dominio) è il modello di interfaccia separati.</span><span class="sxs-lookup"><span data-stu-id="08877-125">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="08877-126">Come [illustrato](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) per Martin Fowler, "interfaccia separati da utilizzare per definire un'interfaccia in un pacchetto ma implementarlo in un altro.</span><span class="sxs-lookup"><span data-stu-id="08877-126">As [explained](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="08877-127">In questo modo un client che richiede la dipendenza per l'interfaccia può essere completamente conoscenza dell'implementazione."</span><span class="sxs-lookup"><span data-stu-id="08877-127">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="08877-128">Modello di interfaccia separati consente il livello di applicazione (in questo caso, il progetto API Web per il microservizio) abbia una dipendenza per i requisiti definiti nel modello di dominio, ma non una dipendenza diretta per l'infrastruttura/persistenza livello.</span><span class="sxs-lookup"><span data-stu-id="08877-128">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="08877-129">Inoltre, è possibile utilizzare l'inserimento di dipendenze per isolare l'implementazione, che viene implementata l'infrastruttura del livello di persistenza con repository.</span><span class="sxs-lookup"><span data-stu-id="08877-129">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="08877-130">Ad esempio, l'esempio seguente con l'interfaccia IOrderRepository definisce le operazioni che la classe OrderRepository sarà necessario implementare il livello di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="08877-130">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="08877-131">Nell'implementazione corrente dell'applicazione, il codice deve semplicemente aggiungere l'ordine nel database, poiché le query sono i seguenti di divisione che approccio CQS e gli aggiornamenti degli ordini non sono implementate.</span><span class="sxs-lookup"><span data-stu-id="08877-131">In the current implementation of the application, the code just needs to add the order to the database, since queries are split following the CQS approach, and updates to orders are not implemented.</span></span>

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
}

public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="08877-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="08877-132">Additional resources</span></span>

-   <span data-ttu-id="08877-133">**Martin Fowler. Interfaccia separato. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span><span class="sxs-lookup"><span data-stu-id="08877-133">**Martin Fowler. Separated Interface.**
[*http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="08877-134">[Precedente] (net-core-microservizio-dominio-model.md) [Avanti] (objects.md implementare-valore)</span><span class="sxs-lookup"><span data-stu-id="08877-134">[Previous] (net-core-microservice-domain-model.md) [Next] (implement-value-objects.md)</span></span>
