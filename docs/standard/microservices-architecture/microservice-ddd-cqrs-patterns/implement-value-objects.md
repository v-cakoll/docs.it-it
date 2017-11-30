---
title: Implementazione di oggetti valore
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione di oggetti valore
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c20bc80d2ddb864a3a0172beb211974426a278a8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-value-objects"></a>Implementazione di oggetti valore

Come descritto nelle sezioni precedenti sulle entità e funzioni di aggregazione, l'identità è fondamentale per le entità. Tuttavia, esistono numerosi oggetti e gli elementi di dati in un sistema che non richiedono un'identità e rilevamento, ad esempio oggetti valore di identità.

Un oggetto valore può fare riferimento altre entità. Ad esempio, in un'applicazione che genera una route che descrive come ottenere da un punto a altro, tale route sarebbe un oggetto valore. Sarebbe uno snapshot di punti in un percorso specifico, ma questa route suggerita non avrebbero un'identità, anche se internamente potrebbero fare riferimento alle entità City, strada, ecc.

Figura 9 a 13 mostra l'oggetto di valore indirizzo all'interno dell'aggregazione di ordine.

![](./media/image14.png)

**Figura 9 a 13**. Oggetto valore all'interno dell'aggregazione di ordine di indirizzi

Come illustrato nella figura 9 a 13, un'entità è generalmente composta da più attributi. Ad esempio, possibile modellata come entità con un'identità ordine e internamente composto da un set di attributi, ad esempio OrderId OrderDate, OrderItems, e così via. Ma l'indirizzo, che è semplicemente un valore complesso composto paese, strada, città, e così via devono essere modellati e considerato come un oggetto valore.

## <a name="important-characteristics-of-value-objects"></a>Importanti caratteristiche di oggetti

Esistono due caratteristiche principali per gli oggetti di valore:

-   Non dispongono di alcuna identità.

-   Essi non sono modificabili.

La prima caratteristica è stata già descritto. Non modificabilità è un requisito importante. I valori di un oggetto di valore devono essere non modificabili dopo la creazione dell'oggetto. Pertanto, quando l'oggetto viene costruito, è necessario fornire i valori richiesti, ma non è necessario consentire loro di modificare la durata dell'oggetto.

Valore oggetti consentono di eseguire alcuni suggerimenti per le prestazioni, grazie alla loro natura non modificabile. Ciò vale soprattutto nei sistemi in cui può essere presenti migliaia di valore istanze di un oggetto, molti dei quali sono gli stessi valori. La natura non modificabile consente loro di essere riutilizzata; possono essere oggetti intercambiabili, poiché i relativi valori sono uguali e non dispongono di alcuna identità. Questo tipo di ottimizzazione può talvolta fare la differenza tra applicazioni software che viene eseguita lentamente e con prestazioni ottimali. Naturalmente, tutti questi casi dipendono l'ambiente dell'applicazione e il contesto di distribuzione.

## <a name="value-object-implementation-in-c"></a>Valore oggetto dell'implementazione in C\#

In termini di implementazione, è possibile avere una classe di base oggetto valore contenente i metodi di utilità di base come basato sul confronto tra tutti gli attributi (poiché un oggetto valore non deve essere basato sull'identità) e altre caratteristiche fondamentali di uguaglianza. Nell'esempio seguente viene illustrata una classe di base oggetto valore utilizzata con l'ordinamento microservizio da eShopOnContainers.

```csharp
public abstract class ValueObject
{
    protected static bool EqualOperator(ValueObject left, ValueObject right)
    {
        if (ReferenceEquals(left, null) ^ ReferenceEquals(right, null))
        {
            return false;
        }
        return ReferenceEquals(left, null) || left.Equals(right);
    }

    protected static bool NotEqualOperator(ValueObject left, ValueObject right)
    {
        return !(EqualOperator(left, right));
    }

    protected abstract IEnumerable<object> GetAtomicValues();

    public override bool Equals(object obj)
    {
        if (obj == null || obj.GetType() != GetType())
        {
            return false;
        }

        ValueObject other = (ValueObject)obj;
        IEnumerator<object> thisValues = GetAtomicValues().GetEnumerator();
        IEnumerator<object> otherValues = other.GetAtomicValues().GetEnumerator();
        while (thisValues.MoveNext() && otherValues.MoveNext())
        {
            if (ReferenceEquals(thisValues.Current, null) ^
                ReferenceEquals(otherValues.Current, null))
            {
                return false;
            }

            if (thisValues.Current != null &&
                !thisValues.Current.Equals(otherValues.Current))
            {
                return false;
            }
        }
        return !thisValues.MoveNext() && !otherValues.MoveNext();
    }
    // Other utilility methods
}
```

È possibile utilizzare questa classe quando si implementa l'oggetto valore effettivo, come con l'oggetto valore mostrato nell'esempio seguente:

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    public Address(string street, string city, string state,
        string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a>Nascondere la caratteristica di identità quando si usa Entity Framework Core in modo permanente gli oggetti di valore

Una limitazione quando si utilizza Entity Framework Core è la versione corrente (Entity Framework Core 1.1) non è possibile utilizzare [tipi complessi](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) come definito in Entity Framework 6. x. Pertanto, è necessario archiviare l'oggetto di valore come un'entità di Entity Framework. Tuttavia, è possibile nascondere il relativo ID in modo da chiarire che l'identità non è importante nel modello di oggetto valore. Si nasconde l'ID è usando l'ID come una proprietà di ombreggiatura. Dal momento che la configurazione per nascondere l'ID del modello viene impostata nel livello di infrastruttura, sarà trasparente per il modello di dominio e l'implementazione di infrastrutture potrebbe cambiare in futuro.

In eShopOnContainers, l'ID nascosto necessario per l'infrastruttura di base di Entity Framework viene implementato nel modo seguente nel livello DbContext, utilizzando l'API Fluent di progetto di infrastruttura.

```csharp
// Fluent API within the OrderingContext:DbContext in the
// Ordering.Infrastructure project

void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

Pertanto, l'ID è nascosta dal dominio modello punto di vista e in futuro, l'infrastruttura di oggetto valore potrebbe anche essere implementato come un tipo complesso o un altro modo.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Martin Fowler. Modello ValueObject**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Eric Evans. Progettazione basati su dominio: Affrontare complessità il cuore del Software.** (Una cartella di lavoro e include una descrizione di oggetti valore) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Vaughn Vernon. Implementazione della progettazione basati su dominio.** (Una cartella di lavoro e include una descrizione di oggetti valore) [ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **Nascondere le proprietà**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)

-   **Tipi complessi e/o oggetti con valore**. Discussione nel repository GitHub Core EF (scheda problemi) [ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)

-   **ValueObject.cs.** Classe di oggetti valore di base in eShopOnContainers.
    [*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   **Classe di indirizzo.** Esempio valore oggetto classe eShopOnContainers.
    [*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
[Precedente] [Avanti] (enumerazione-classi-over-enum-types.md) (seedwork-domain-model-base-classes-interfaces.md)
