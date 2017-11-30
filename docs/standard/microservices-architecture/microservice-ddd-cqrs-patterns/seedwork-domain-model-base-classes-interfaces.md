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
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>Seedwork (riutilizzabili classi base e interfacce per il modello di dominio)

La cartella della soluzione contiene un *SeedWork* cartella. Il *SeedWork* cartella contiene le classi base personalizzate che è possibile utilizzare come base per le entità di dominio e gli oggetti di valore. Utilizzare queste classi di base in modo che non sia il codice ridondante nella classe di oggetti di ciascun dominio. La cartella per questi tipi di classi è denominata *SeedWork* e non è *Framework*. Viene chiamato *SeedWork* perché la cartella contiene solo un piccolo subset di classi riutilizzabili che realmente non può essere considerato un framework. *Seedwork* è un termine dovuto [penne Michael](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) e resa nota da [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) ma è anche possibile specificare il nome cartella comune, SharedKernel, o simili.

Figura 9-12 vengono illustrate le classi che costituiscono l'ordinamento microservizio seedwork del modello di dominio. Include alcune classi di base personalizzate come entità, ValueObject e di enumerazione, nonché alcune interfacce. Queste interfacce (IRepository e IUnitOfWork) che indicano il livello infrastruttura sulle operazioni necessarie per essere implementato. Queste interfacce vengono utilizzate anche tramite l'inserimento di dipendenze dal livello dell'applicazione.

![](./media/image13.PNG)

**Figura 9-12**. Un esempio di set di interfacce e classi di base "seedwork" modello di dominio

Questo è il tipo del riutilizzo di copia e Incolla che molti sviluppatori condividono tra progetti, non è un framework formale. È possibile avere seedworks in qualsiasi livello o di una libreria. Tuttavia, se il set di classi e interfacce Ottiene sufficientemente grande, potrebbe essere desiderato creare una libreria di classi singolo.

## <a name="the-custom-entity-base-class"></a>La classe di base di entità personalizzata

Il codice riportato di seguito è riportato un esempio di una classe di base di entità in cui è possibile inserire codice che può essere utilizzato esattamente come per qualsiasi entità di dominio, ad esempio l'ID entità, [gli operatori di uguaglianza](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx)e così via.

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

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>Contratti di repository (interfacce) nel livello del modello di dominio

Contratti di repository sono semplicemente interfacce .NET che esprimono i requisiti del contratto dei repository da utilizzare per ogni funzione di aggregazione. I repository se stessi, con codice di base di Entity Framework o le altre dipendenze dell'infrastruttura e codice, non devono essere implementati all'interno del modello di dominio; i repository devono implementare solo le interfacce definite.

Un modello correlato a questa prassi (ponendo le interfacce di repository nel livello del modello di dominio) è il modello di interfaccia separati. Come [illustrato](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) per Martin Fowler, "interfaccia separati da utilizzare per definire un'interfaccia in un pacchetto ma implementarlo in un altro. In questo modo un client che richiede la dipendenza per l'interfaccia può essere completamente conoscenza dell'implementazione."

Modello di interfaccia separati consente il livello di applicazione (in questo caso, il progetto API Web per il microservizio) abbia una dipendenza per i requisiti definiti nel modello di dominio, ma non una dipendenza diretta per l'infrastruttura/persistenza livello. Inoltre, è possibile utilizzare l'inserimento di dipendenze per isolare l'implementazione, che viene implementata l'infrastruttura del livello di persistenza con repository.

Ad esempio, l'esempio seguente con l'interfaccia IOrderRepository definisce le operazioni che la classe OrderRepository sarà necessario implementare il livello di infrastruttura. Nell'implementazione corrente dell'applicazione, il codice deve semplicemente aggiungere l'ordine nel database, poiché le query sono i seguenti di divisione che approccio CQS e gli aggiornamenti degli ordini non sono implementate.

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

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Martin Fowler. Interfaccia separato. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)


>[!div class="step-by-step"]
[Precedente] (net-core-microservizio-dominio-model.md) [Avanti] (objects.md implementare-valore)
