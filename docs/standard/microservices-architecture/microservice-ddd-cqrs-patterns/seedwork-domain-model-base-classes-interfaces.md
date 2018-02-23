---
title: Seedwork (classi di base riutilizzabili e interfacce per il modello di dominio)
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Seedwork (classi di base riutilizzabili e interfacce per il modello di dominio)
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: aba336676a558f50a2669eb3ca096effb8387916
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2018
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>Seedwork (classi di base riutilizzabili e interfacce per il modello di dominio)

La cartella della soluzione contiene una cartella denominata *SeedWork*. La cartella *SeedWork* contiene classi di base personalizzate che è possibile usare come base per le entità di dominio e gli oggetti valore. È possibile usare queste classi di base per evitare codice ridondante in ogni classe di oggetti del dominio. La cartella per questi tipi di classi è denominata *SeedWork* e non *Framework* o qualcosa di simile. Viene denominata *SeedWork* perché la cartella contiene solo un piccolo subset di classi riutilizzabili che non può effettivamente essere considerato un framework. Il termine *Seedwork* è stato introdotto da [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) ed è diventato noto grazie a [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html). Questa cartella può tuttavia essere denominata Common, SharedKernel o avere un nome simile.

La figura 9-12 illustra le classi che costituiscono la cartella Seedwork del modello di dominio nel microservizio degli ordini. La cartella contiene alcune classi di base personalizzate come Entity, ValueObject ed Enumeration e alcune interfacce. Queste interfacce (IRepository e IUnitOfWork) indicano al livello infrastruttura le implementazioni necessarie. Queste interfacce vengono usate anche dal livello dell'applicazione tramite l'inserimento delle dipendenze.

![](./media/image13.PNG)

**Figura 9-12**. Set di esempio di classi di base e interfacce nella cartella"Seedwork" per il modello di dominio

Si tratta di un tipo di riutilizzo che può essere copiato e incollato e che molti sviluppatori condividono nei progetti. Non è un framework formale. È possibile avere cartelle Seedwork in qualsiasi livello o libreria. Se il set di classi e interfacce aumenta di dimensioni, potrebbe essere tuttavia necessario creare un'unica libreria di classi.

## <a name="the-custom-entity-base-class"></a>Classe di base Entity personalizzata

Il codice seguente è un esempio di una classe di base Entity in cui è possibile inserire il codice che può essere usato allo stesso modo da qualsiasi entità di dominio, ad esempio dall'ID entità, dagli [operatori di uguaglianza](/cpp/cpp/equality-operators-equal-equal-and-exclpt-equal), da un elenco di eventi di dominio per ogni entità e così via.

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

Il codice precedente che usa un elenco di eventi di dominio per ogni entità viene spiegato nelle prossime sezioni che riguardano gli eventi di dominio. 

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>Contratti di repository (interfacce) nel livello del modello di dominio

I contratti di repository sono semplicemente interfacce .NET che esprimono i requisiti di contratto dei repository da usare per ogni aggregato. 

I repository con codice di Entity Framework Core o qualsiasi altra dipendenza da infrastruttura e codice (Linq, SQL e così via), non devono essere implementati all'interno del modello di dominio, ma devono soltanto implementare le interfacce definite. 

Un modello che spiega questa pratica, vale a dire l'inserimento delle interfacce di repository nel livello del modello di dominio, è il modello noto come "Interfaccia separata". Secondo quanto [spiega](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) Martin Fowler è importante "usare il modello Interfaccia separata per definire un'interfaccia in un pacchetto, ma implementarla in un altro pacchetto. In questo modo il client che richiede la dipendenza all'interfaccia può essere totalmente ignaro dell'implementazione."

Il modello "Interfaccia separata" consente al livello dell'applicazione (in questo caso il progetto API Web per il microservizio) di dipendere dai requisiti definiti nel modello di dominio, ma di non avere una dipendenza diretta al livello infrastruttura/persistenza. È anche possibile usare l'inserimento delle dipendenze per isolare l'implementazione, che viene definita nel livello infrastruttura/persistenza tramite i repository.

Nell'esempio seguente con l'interfaccia IOrderRepository vengono definite le operazioni che la classe OrderRepository deve implementare al livello di infrastruttura. Nell'implementazione corrente dell'applicazione il codice deve soltanto aggiungere o aggiornare gli ordini nel database, poiché le query vengono suddivise in base all'approccio CQRS semplificato.

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

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Martin Fowler. Interfaccia separata. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html)


>[!div class="step-by-step"]
[Precedente] (net-core-microservice-domain-model.md) [Successivo] (implement-value-objects.md)
