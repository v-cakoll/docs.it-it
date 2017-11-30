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
# <a name="implementing-value-objects"></a><span data-ttu-id="8797b-104">Implementazione di oggetti valore</span><span class="sxs-lookup"><span data-stu-id="8797b-104">Implementing value objects</span></span>

<span data-ttu-id="8797b-105">Come descritto nelle sezioni precedenti sulle entità e funzioni di aggregazione, l'identità è fondamentale per le entità.</span><span class="sxs-lookup"><span data-stu-id="8797b-105">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="8797b-106">Tuttavia, esistono numerosi oggetti e gli elementi di dati in un sistema che non richiedono un'identità e rilevamento, ad esempio oggetti valore di identità.</span><span class="sxs-lookup"><span data-stu-id="8797b-106">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="8797b-107">Un oggetto valore può fare riferimento altre entità.</span><span class="sxs-lookup"><span data-stu-id="8797b-107">A value object can reference other entities.</span></span> <span data-ttu-id="8797b-108">Ad esempio, in un'applicazione che genera una route che descrive come ottenere da un punto a altro, tale route sarebbe un oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="8797b-108">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="8797b-109">Sarebbe uno snapshot di punti in un percorso specifico, ma questa route suggerita non avrebbero un'identità, anche se internamente potrebbero fare riferimento alle entità City, strada, ecc.</span><span class="sxs-lookup"><span data-stu-id="8797b-109">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="8797b-110">Figura 9 a 13 mostra l'oggetto di valore indirizzo all'interno dell'aggregazione di ordine.</span><span class="sxs-lookup"><span data-stu-id="8797b-110">Figure 9-13 shows the Address value object within the Order aggregate.</span></span>

![](./media/image14.png)

<span data-ttu-id="8797b-111">**Figura 9 a 13**.</span><span class="sxs-lookup"><span data-stu-id="8797b-111">**Figure 9-13**.</span></span> <span data-ttu-id="8797b-112">Oggetto valore all'interno dell'aggregazione di ordine di indirizzi</span><span class="sxs-lookup"><span data-stu-id="8797b-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="8797b-113">Come illustrato nella figura 9 a 13, un'entità è generalmente composta da più attributi.</span><span class="sxs-lookup"><span data-stu-id="8797b-113">As shown in Figure 9-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="8797b-114">Ad esempio, possibile modellata come entità con un'identità ordine e internamente composto da un set di attributi, ad esempio OrderId OrderDate, OrderItems, e così via. Ma l'indirizzo, che è semplicemente un valore complesso composto paese, strada, città, e così via devono essere modellati e considerato come un oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="8797b-114">For example, Order can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex value composed of country, street, city, etc. must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="8797b-115">Importanti caratteristiche di oggetti</span><span class="sxs-lookup"><span data-stu-id="8797b-115">Important characteristics of value objects</span></span>

<span data-ttu-id="8797b-116">Esistono due caratteristiche principali per gli oggetti di valore:</span><span class="sxs-lookup"><span data-stu-id="8797b-116">There are two main characteristics for value objects:</span></span>

-   <span data-ttu-id="8797b-117">Non dispongono di alcuna identità.</span><span class="sxs-lookup"><span data-stu-id="8797b-117">They have no identity.</span></span>

-   <span data-ttu-id="8797b-118">Essi non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="8797b-118">They are immutable.</span></span>

<span data-ttu-id="8797b-119">La prima caratteristica è stata già descritto.</span><span class="sxs-lookup"><span data-stu-id="8797b-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="8797b-120">Non modificabilità è un requisito importante.</span><span class="sxs-lookup"><span data-stu-id="8797b-120">Immutability is an important requirement.</span></span> <span data-ttu-id="8797b-121">I valori di un oggetto di valore devono essere non modificabili dopo la creazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8797b-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="8797b-122">Pertanto, quando l'oggetto viene costruito, è necessario fornire i valori richiesti, ma non è necessario consentire loro di modificare la durata dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8797b-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="8797b-123">Valore oggetti consentono di eseguire alcuni suggerimenti per le prestazioni, grazie alla loro natura non modificabile.</span><span class="sxs-lookup"><span data-stu-id="8797b-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="8797b-124">Ciò vale soprattutto nei sistemi in cui può essere presenti migliaia di valore istanze di un oggetto, molti dei quali sono gli stessi valori.</span><span class="sxs-lookup"><span data-stu-id="8797b-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="8797b-125">La natura non modificabile consente loro di essere riutilizzata; possono essere oggetti intercambiabili, poiché i relativi valori sono uguali e non dispongono di alcuna identità.</span><span class="sxs-lookup"><span data-stu-id="8797b-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="8797b-126">Questo tipo di ottimizzazione può talvolta fare la differenza tra applicazioni software che viene eseguita lentamente e con prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="8797b-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="8797b-127">Naturalmente, tutti questi casi dipendono l'ambiente dell'applicazione e il contesto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8797b-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="8797b-128">Valore oggetto dell'implementazione in C\#</span><span class="sxs-lookup"><span data-stu-id="8797b-128">Value object implementation in C\#</span></span>

<span data-ttu-id="8797b-129">In termini di implementazione, è possibile avere una classe di base oggetto valore contenente i metodi di utilità di base come basato sul confronto tra tutti gli attributi (poiché un oggetto valore non deve essere basato sull'identità) e altre caratteristiche fondamentali di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="8797b-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="8797b-130">Nell'esempio seguente viene illustrata una classe di base oggetto valore utilizzata con l'ordinamento microservizio da eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8797b-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

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

<span data-ttu-id="8797b-131">È possibile utilizzare questa classe quando si implementa l'oggetto valore effettivo, come con l'oggetto valore mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8797b-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

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

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a><span data-ttu-id="8797b-132">Nascondere la caratteristica di identità quando si usa Entity Framework Core in modo permanente gli oggetti di valore</span><span class="sxs-lookup"><span data-stu-id="8797b-132">Hiding the identity characteristic when using EF Core to persist value objects</span></span>

<span data-ttu-id="8797b-133">Una limitazione quando si utilizza Entity Framework Core è la versione corrente (Entity Framework Core 1.1) non è possibile utilizzare [tipi complessi](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) come definito in Entity Framework 6. x.</span><span class="sxs-lookup"><span data-stu-id="8797b-133">A limitation when using EF Core is that in its current version (EF Core 1.1) you cannot use [complex types](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) as defined in EF 6.x.</span></span> <span data-ttu-id="8797b-134">Pertanto, è necessario archiviare l'oggetto di valore come un'entità di Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="8797b-134">Therefore, you must store your value object as an EF entity.</span></span> <span data-ttu-id="8797b-135">Tuttavia, è possibile nascondere il relativo ID in modo da chiarire che l'identità non è importante nel modello di oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="8797b-135">However, you can hide its ID so you make clear that the identity is not important in the model that the value object is part of.</span></span> <span data-ttu-id="8797b-136">Si nasconde l'ID è usando l'ID come una proprietà di ombreggiatura.</span><span class="sxs-lookup"><span data-stu-id="8797b-136">You hide the ID is by using the ID as a shadow property.</span></span> <span data-ttu-id="8797b-137">Dal momento che la configurazione per nascondere l'ID del modello viene impostata nel livello di infrastruttura, sarà trasparente per il modello di dominio e l'implementazione di infrastrutture potrebbe cambiare in futuro.</span><span class="sxs-lookup"><span data-stu-id="8797b-137">Since that configuration for hiding the ID in the model is set up in the infrastructure level, it will be transparent for your domain model, and its infrastructure implementation could change in the future.</span></span>

<span data-ttu-id="8797b-138">In eShopOnContainers, l'ID nascosto necessario per l'infrastruttura di base di Entity Framework viene implementato nel modo seguente nel livello DbContext, utilizzando l'API Fluent di progetto di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="8797b-138">In eShopOnContainers, the hidden ID needed by EF Core infrastructure is implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span>

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

<span data-ttu-id="8797b-139">Pertanto, l'ID è nascosta dal dominio modello punto di vista e in futuro, l'infrastruttura di oggetto valore potrebbe anche essere implementato come un tipo complesso o un altro modo.</span><span class="sxs-lookup"><span data-stu-id="8797b-139">Therefore, the ID is hidden from the domain model point of view, and in the future, the value object infrastructure could also be implemented as a complex type or another way.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8797b-140">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8797b-140">Additional resources</span></span>

-   <span data-ttu-id="8797b-141">**Martin Fowler. Modello ValueObject**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="8797b-141">**Martin Fowler. ValueObject pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="8797b-142">**Eric Evans. Progettazione basati su dominio: Affrontare complessità il cuore del Software.**</span><span class="sxs-lookup"><span data-stu-id="8797b-142">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="8797b-143">(Una cartella di lavoro e include una descrizione di oggetti valore) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="8797b-143">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="8797b-144">**Vaughn Vernon. Implementazione della progettazione basati su dominio.**</span><span class="sxs-lookup"><span data-stu-id="8797b-144">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="8797b-145">(Una cartella di lavoro e include una descrizione di oggetti valore) [ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="8797b-145">(Book; includes a discussion of value objects) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="8797b-146">**Nascondere le proprietà**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="8797b-146">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="8797b-147">**Tipi complessi e/o oggetti con valore**.</span><span class="sxs-lookup"><span data-stu-id="8797b-147">**Complex types and/or value objects**.</span></span> <span data-ttu-id="8797b-148">Discussione nel repository GitHub Core EF (scheda problemi) [ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span><span class="sxs-lookup"><span data-stu-id="8797b-148">Discussion in the EF Core GitHub repo (Issues tab) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span></span>

-   <span data-ttu-id="8797b-149">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="8797b-149">**ValueObject.cs.**</span></span> <span data-ttu-id="8797b-150">Classe di oggetti valore di base in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8797b-150">Base value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="8797b-151">*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span><span class="sxs-lookup"><span data-stu-id="8797b-151">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   <span data-ttu-id="8797b-152">**Classe di indirizzo.**</span><span class="sxs-lookup"><span data-stu-id="8797b-152">**Address class.**</span></span> <span data-ttu-id="8797b-153">Esempio valore oggetto classe eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8797b-153">Sample value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="8797b-154">*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span><span class="sxs-lookup"><span data-stu-id="8797b-154">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
<span data-ttu-id="8797b-155">[Precedente] [Avanti] (enumerazione-classi-over-enum-types.md) (seedwork-domain-model-base-classes-interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="8797b-155">[Previous] (seedwork-domain-model-base-classes-interfaces.md) [Next] (enumeration-classes-over-enum-types.md)</span></span>
