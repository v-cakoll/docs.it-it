---
title: Implementazione di oggetti valore
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione di oggetti valore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: 4ba2e48e742e580a1c96743fa89e413c488b8dc7
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106723"
---
# <a name="implementing-value-objects"></a><span data-ttu-id="3479a-103">Implementazione di oggetti valore</span><span class="sxs-lookup"><span data-stu-id="3479a-103">Implementing value objects</span></span>

<span data-ttu-id="3479a-104">Come descritto nelle sezioni precedenti relative a entità e aggregazioni, l'identità è un elemento fondamentale per le entità.</span><span class="sxs-lookup"><span data-stu-id="3479a-104">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="3479a-105">Tuttavia, esistono numerosi oggetti ed elementi di dati in un sistema che non richiedono un'identità e la verifica dell'identità, ad esempio gli oggetti valore.</span><span class="sxs-lookup"><span data-stu-id="3479a-105">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="3479a-106">Un oggetto valore può fare riferimento ad altre entità.</span><span class="sxs-lookup"><span data-stu-id="3479a-106">A value object can reference other entities.</span></span> <span data-ttu-id="3479a-107">Ad esempio, in un'applicazione che genera una route che descrive come passare da un punto a altro, questa route sarebbe un oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="3479a-107">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="3479a-108">Corrisponderebbe a uno snapshot di punti in una route specifica, tuttavia la route suggerita non avrebbe un'identità, anche se internamente potrebbe fare riferimento a entità come City, Road e così via.</span><span class="sxs-lookup"><span data-stu-id="3479a-108">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="3479a-109">La figura 9-13 mostra l'oggetto valore Address all'interno dell'aggregazione Order.</span><span class="sxs-lookup"><span data-stu-id="3479a-109">Figure 9-13 shows the Address value object within the Order aggregate.</span></span>

![](./media/image14.png)

<span data-ttu-id="3479a-110">**Figura 9-13**.</span><span class="sxs-lookup"><span data-stu-id="3479a-110">**Figure 9-13**.</span></span> <span data-ttu-id="3479a-111">Oggetto valore Address all'interno dell'aggregazione Order</span><span class="sxs-lookup"><span data-stu-id="3479a-111">Address value object within the Order aggregate</span></span>

<span data-ttu-id="3479a-112">Come illustrato nella figura 9-13, un'entità è generalmente composta da più attributi.</span><span class="sxs-lookup"><span data-stu-id="3479a-112">As shown in Figure 9-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="3479a-113">Ad esempio, l'entità `Order` può essere modellata come entità con un'identità, composta internamente da un set di attributi come OrderId, OrderDate, OrderItems e così via. Invece l'indirizzo, che è semplicemente un valore complesso costituito da paese, strada, città e così via, e che non ha un'identità in questo dominio, deve essere modellato e gestito come oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="3479a-113">For example, the `Order` entity can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex value composed of country, street, city, etc. and has no identity in this domain,  must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="3479a-114">Caratteristiche importanti degli oggetti valore</span><span class="sxs-lookup"><span data-stu-id="3479a-114">Important characteristics of value objects</span></span>

<span data-ttu-id="3479a-115">Esistono due caratteristiche principali proprie degli oggetti valore:</span><span class="sxs-lookup"><span data-stu-id="3479a-115">There are two main characteristics for value objects:</span></span>

-   <span data-ttu-id="3479a-116">Non hanno identità.</span><span class="sxs-lookup"><span data-stu-id="3479a-116">They have no identity.</span></span>

-   <span data-ttu-id="3479a-117">Non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="3479a-117">They are immutable.</span></span>

<span data-ttu-id="3479a-118">La prima caratteristica è già stata descritta.</span><span class="sxs-lookup"><span data-stu-id="3479a-118">The first characteristic was already discussed.</span></span> <span data-ttu-id="3479a-119">L'immutabilità è un requisito importante.</span><span class="sxs-lookup"><span data-stu-id="3479a-119">Immutability is an important requirement.</span></span> <span data-ttu-id="3479a-120">Dopo aver creato l'oggetto, i valori di un oggetto valore non devono essere modificabili.</span><span class="sxs-lookup"><span data-stu-id="3479a-120">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="3479a-121">Quindi, quando l'oggetto viene costruito, è necessario fornire i valori richiesti, ma non se ne deve consentire la modifica per l'intera durata dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3479a-121">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="3479a-122">Gli oggetti valore consentono di eseguire alcune operazioni per migliorare le prestazioni, grazie alla loro natura non modificabile.</span><span class="sxs-lookup"><span data-stu-id="3479a-122">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="3479a-123">Ciò vale soprattutto nei sistemi in cui possono essere presenti migliaia di istanze di un oggetto valore, molte delle quali contengono gli stessi valori.</span><span class="sxs-lookup"><span data-stu-id="3479a-123">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="3479a-124">La natura non modificabile di questi oggetti ne consente il riutilizzo. Sono anche intercambiabili perché i loro valori sono uguali e non hanno alcuna identità.</span><span class="sxs-lookup"><span data-stu-id="3479a-124">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="3479a-125">A volte, questo tipo di ottimizzazione può fare la differenza tra un software eseguito lentamente e uno con prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="3479a-125">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="3479a-126">Naturalmente, tutti questi casi dipendono l'ambiente dell'applicazione e dal contesto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3479a-126">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="3479a-127">Implementazione dell'oggetto valore in C\#</span><span class="sxs-lookup"><span data-stu-id="3479a-127">Value object implementation in C\#</span></span>

<span data-ttu-id="3479a-128">In termini di implementazione, è possibile avere una classe di base di oggetti valore contenente metodi di utilità di base come l'uguaglianza basata sul confronto tra tutti gli attributi (perché un oggetto valore non deve essere basato sull'identità) e altre caratteristiche fondamentali.</span><span class="sxs-lookup"><span data-stu-id="3479a-128">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="3479a-129">L'esempio seguente mostra una classe di base di oggetti valore usata nel microservizio degli ordini di eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="3479a-129">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

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

    public override int GetHashCode()
    {
        return GetAtomicValues()
         .Select(x => x != null ? x.GetHashCode() : 0)
         .Aggregate((x, y) => x ^ y);
    }        
    // Other utilility methods
}
```

<span data-ttu-id="3479a-130">È possibile usare questa classe quando si implementa l'oggetto valore effettivo, ad esempio l'oggetto valore Address mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3479a-130">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; }
    public String City { get; }
    public String State { get; }
    public String Country { get; }
    public String ZipCode { get; }

    private Address() { }

    public Address(string street, string city, string state, string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        // Using a yield return statement to return each element one at a time
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20"></a><span data-ttu-id="3479a-131">Come rendere persistenti gli oggetti valore nel database con EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3479a-131">How to persist value objects in the database with EF Core 2.0</span></span>

<span data-ttu-id="3479a-132">È stato appena descritto come definire un oggetto valore nel modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="3479a-132">You just saw how to define a value object in your domain model.</span></span> <span data-ttu-id="3479a-133">Ma come si può rendere effettivamente persistente un oggetto valore nel database con Entity Framework (EF) Core, che in genere usa entità con identità?</span><span class="sxs-lookup"><span data-stu-id="3479a-133">But, how can you actually persist it into the database through Entity Framework (EF) Core which usually targets entities with identity?</span></span>

### <a name="background-and-older-approaches-using-ef-core-11"></a><span data-ttu-id="3479a-134">Approcci generali e precedenti con l'uso di EF Core 1.1</span><span class="sxs-lookup"><span data-stu-id="3479a-134">Background and older approaches using EF Core 1.1</span></span>

<span data-ttu-id="3479a-135">Una limitazione generale di EF Core 1.0 e 1.1 impediva l'uso dei [tipi complessi](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) definiti in EF 6.x in .NET Framework tradizionale.</span><span class="sxs-lookup"><span data-stu-id="3479a-135">As background, a limitation when using EF Core 1.0 and 1.1 was that you cannot use  [complex types](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) as defined in EF 6.x in the traditional .NET Framework.</span></span> <span data-ttu-id="3479a-136">Quindi, se si usava EF Core 1.0 o 1.1, era necessario archiviare l'oggetto di valore come entità EF con un campo ID.</span><span class="sxs-lookup"><span data-stu-id="3479a-136">Therefore, if using EF Core 1.0 or 1.1, you needed to store your value object as an EF entity with an ID field.</span></span> <span data-ttu-id="3479a-137">Successivamente, per farlo somigliare di più a un oggetto valore senza identità, era possibile nascondere l'ID per indicare che l'identità di un oggetto valore non è importante nel modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="3479a-137">Then, so it looked more like a value object with no identity, you could hide its ID so you make clear that the identity of a value object is not important in the domain model.</span></span> <span data-ttu-id="3479a-138">L'ID poteva essere nascosto trasformandolo in una [proprietà shadow](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span><span class="sxs-lookup"><span data-stu-id="3479a-138">You could hide that ID by using the ID as a [shadow property](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span></span> <span data-ttu-id="3479a-139">Dal momento che la configurazione per nascondere l'ID del modello viene configurata nel livello di infrastruttura di EF, risulterebbe trasparente per il modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="3479a-139">Since that configuration for hiding the ID in the model is set up in the EF infrastructure level, it would be kind of transparent for your domain model.</span></span>

<span data-ttu-id="3479a-140">Nella versione iniziale di eShopOnContainers (.NET Core 1.1), l'ID nascosto necessario per l'infrastruttura EF Core era implementato nel modo seguente nel livello DbContext, usando l'API Fluent nel progetto di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="3479a-140">In the initial version of eShopOnContainers (.NET Core 1.1), the hidden ID needed by EF Core infrastructure was implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span> <span data-ttu-id="3479a-141">Quindi, l'ID risultava nascosto per il modello di dominio, ma era ancora presente nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="3479a-141">Therefore, the ID was hidden from the domain model point of view, but still present in the infrastructure.</span></span>

```csharp
// Old approach with EF Core 1.1
// Fluent API within the OrderingContext:DbContext in the Infrastructure project
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration) 
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA); 

    addressConfiguration.Property<int>("Id")  // Id is a shadow property
        .IsRequired();
    addressConfiguration.HasKey("Id");   // Id is a shadow property
}
```

<span data-ttu-id="3479a-142">La persistenza dell'oggetto valore nel database era comunque assicurata usando un'entità normale in un'altra tabella.</span><span class="sxs-lookup"><span data-stu-id="3479a-142">However, the persistence of that value object into the database was performed like a regular entity in a different table.</span></span>

<span data-ttu-id="3479a-143">In EF Core 2.0 vengono forniti modi nuovi e ottimizzati per rendere persistenti gli oggetti valore.</span><span class="sxs-lookup"><span data-stu-id="3479a-143">With EF Core 2.0, there are new and better ways to persist value objects.</span></span>

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20"></a><span data-ttu-id="3479a-144">Rendere persistenti gli oggetti valore come tipi di entità di proprietà in EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3479a-144">Persist value objects as owned entity types in EF Core 2.0</span></span>

<span data-ttu-id="3479a-145">Anche se ci sono alcune discrepanze tra lo schema dell'oggetto valore canonico in DDD e il tipo di entità di proprietà in EF Core, questo è attualmente il modo migliore per rendere persistenti gli oggetti valore con EF Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="3479a-145">Even with some gaps between the canonical value object pattern in DDD and the owned entity type in EF Core, it's currently the best way to persist value objects with EF Core 2.0.</span></span> <span data-ttu-id="3479a-146">È possibile vedere le limitazioni alla fine di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3479a-146">You can see limitations at the end of this section.</span></span>

<span data-ttu-id="3479a-147">La funzionalità dei tipi di entità di proprietà è stata aggiunta a EF Core a partire dalla versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="3479a-147">The owned entity type feature was added to EF Core since version 2.0.</span></span>

<span data-ttu-id="3479a-148">Un tipo di entità di proprietà consente di eseguire il mapping dei tipi che non hanno un'identità definita in modo esplicito nel modello di dominio e che vengono usati come proprietà, ad esempio un oggetto valore, all'interno di qualsiasi entità.</span><span class="sxs-lookup"><span data-stu-id="3479a-148">An owned entity type allows you to map types that do not have their own identity explicitely defined in the domain model and are used as properties, such as a value object, within any of your entities.</span></span> <span data-ttu-id="3479a-149">Un tipo di entità di proprietà condivide lo stesso tipo CLR con un altro tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="3479a-149">An owned entity type shares the same CLR type with another entity type.</span></span> <span data-ttu-id="3479a-150">L'entità contenente la navigazione che lo definisce è l'entità del proprietario.</span><span class="sxs-lookup"><span data-stu-id="3479a-150">The entity containing the defining navigation is the owner entity.</span></span> <span data-ttu-id="3479a-151">Quando si esegue una query sul proprietario, i tipi di proprietà vengono inclusi per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3479a-151">When querying the owner, the owned types are included by default.</span></span>

<span data-ttu-id="3479a-152">Osservando semplicemente il modello di dominio, un tipo di proprietà sembra non avere alcuna identità,</span><span class="sxs-lookup"><span data-stu-id="3479a-152">Just by looking at the domain model, an owned type looks like it doesn’t have any identity.</span></span>
<span data-ttu-id="3479a-153">invece la ha, ma la proprietà di navigazione del proprietario fa parte di questa identità.</span><span class="sxs-lookup"><span data-stu-id="3479a-153">However, under the covers, owned types do have identity, but the owner navigation property is part of this identity.</span></span>

<span data-ttu-id="3479a-154">L'identità delle istanze dei tipi di proprietà non è del tutto esclusiva,</span><span class="sxs-lookup"><span data-stu-id="3479a-154">The identity of instances of own types is not completely their own.</span></span> <span data-ttu-id="3479a-155">ma è costituita da tre componenti:</span><span class="sxs-lookup"><span data-stu-id="3479a-155">It consists of three components:</span></span>

- <span data-ttu-id="3479a-156">L'identità del proprietario</span><span class="sxs-lookup"><span data-stu-id="3479a-156">The identity of the owner</span></span>

- <span data-ttu-id="3479a-157">La proprietà di navigazione che punta alle istanze</span><span class="sxs-lookup"><span data-stu-id="3479a-157">The navigation property pointing to them</span></span>

- <span data-ttu-id="3479a-158">Per le raccolte di tipi di proprietà, un componente indipendente (non ancora supportato in EF Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="3479a-158">In the case of collections of owned types, an independent component (not yet supported in EF Core 2.0).</span></span>

<span data-ttu-id="3479a-159">Ad esempio, nel modello di dominio degli ordini in eShopOnContainers, all'interno dell'entità Order, l'oggetto valore Address viene implementato come un tipo di entità di proprietà all'interno dell'entità del proprietario, ovvero l'entità Order.</span><span class="sxs-lookup"><span data-stu-id="3479a-159">For example, in the Ordering domain model at eShopOnContainers, as part of the Order entity, the Address value object is implemented as an owned entity type within the owner entity, which is the Order entity.</span></span> <span data-ttu-id="3479a-160">Address è un tipo la cui proprietà identità non è definita nel modello di dominio.</span><span class="sxs-lookup"><span data-stu-id="3479a-160">Address is a type with no identity property defined in the domain model.</span></span> <span data-ttu-id="3479a-161">Viene usato come proprietà del tipo Order per specificare l'indirizzo di spedizione per uno specifico ordine.</span><span class="sxs-lookup"><span data-stu-id="3479a-161">It is used as a property of the Order type to specify the shipping address for a particular order.</span></span>

<span data-ttu-id="3479a-162">Per convenzione viene creata una chiave primaria shadow per il tipo di proprietà e ne viene eseguito il mapping alla stessa tabella del proprietario usando la suddivisione di tabelle.</span><span class="sxs-lookup"><span data-stu-id="3479a-162">By convention, a shadow primary key is created for the owned type and it will be mapped to the same table as the owner by using table splitting.</span></span> <span data-ttu-id="3479a-163">Ciò consente di usare i tipi di proprietà in modo simile ai tipi complessi in EF6 in .NET Framework tradizionale.</span><span class="sxs-lookup"><span data-stu-id="3479a-163">This allows to use owned types similarly to how complex types are used in EF6 in the traditional .NET Framework.</span></span>

<span data-ttu-id="3479a-164">È importante notare che, per convenzione, i tipi di proprietà non vengono mai individuati in EF Core, quindi è necessario dichiararli in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="3479a-164">It is important to note that owned types are never discovered by convention in EF Core, so you have to declare them explicitly.</span></span>

<span data-ttu-id="3479a-165">Nel metodo OnModelCreating() di OrderingContext.cs in eShopOnContainers vengono applicate più configurazioni dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="3479a-165">In eShopOnContainers, at the OrderingContext.cs, within the OnModelCreating() method, there are multiple infrastructure configuration being applied.</span></span> <span data-ttu-id="3479a-166">Una di esse è correlata all'entità Order.</span><span class="sxs-lookup"><span data-stu-id="3479a-166">One of them is related to the Order entity.</span></span>

```csharp
// Part of the OrderingContext.cs class at the Ordering.Infrastructure project
// 
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.ApplyConfiguration(new ClientRequestEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new PaymentMethodEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderItemEntityTypeConfiguration());
    //...Additional type configurations
}
```

<span data-ttu-id="3479a-167">Nel codice seguente l'infrastruttura di persistenza è definita per l'entità Order:</span><span class="sxs-lookup"><span data-stu-id="3479a-167">In the following code, the persistence infrastructure is defined for the Order entity:</span></span>

```csharp
// Part of the OrderEntityTypeConfiguration.cs class 
// 
public void Configure(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Ignore(b => b.DomainEvents);
    orderConfiguration.Property(o => o.Id)
        .ForSqlServerUseSequenceHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

    //Address value object persisted as owned entity in EF Core 2.0
    orderConfiguration.OwnsOne(o => o.Address);

    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
    
    //...Additional validations, constraints and code...
    //...
}
```

<span data-ttu-id="3479a-168">Nel codice precedente il metodo `orderConfiguration.OwnsOne(o => o.Address)` specifica che la proprietà `Address` è un'entità di proprietà del tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="3479a-168">In the previous code, the `orderConfiguration.OwnsOne(o => o.Address)` method specifies that the `Address` property is an owned entity of the `Order` type.</span></span>

<span data-ttu-id="3479a-169">Per impostazione predefinita, le convenzioni di EF Core nome le colonne del database per le proprietà del tipo di entità di proprietà come `EntityProperty_OwnedEntityProperty`.</span><span class="sxs-lookup"><span data-stu-id="3479a-169">By default, EF Core conventions name the database columns for the properties of the owned entity type as `EntityProperty_OwnedEntityProperty`.</span></span> <span data-ttu-id="3479a-170">Quindi, le proprietà interne di `Address` verranno visualizzate nella tabella `Orders` con i nomi `Address_Street`, `Address_City` (e così via per `State`, `Country` e `ZipCode`).</span><span class="sxs-lookup"><span data-stu-id="3479a-170">Therefore, the internal properties of `Address` will appear in the `Orders` table with the names `Address_Street`, `Address_City` (and so on for `State`, `Country` and `ZipCode`).</span></span>

<span data-ttu-id="3479a-171">È possibile aggiungere il metodo Fluent `Property().HasColumnName()` per rinominare le colonne.</span><span class="sxs-lookup"><span data-stu-id="3479a-171">You can append the `Property().HasColumnName()` fluent method to rename those columns.</span></span> <span data-ttu-id="3479a-172">Se `Address` è una proprietà pubblica, i mapping sono simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="3479a-172">In the case where `Address` is a public property, the mappings would be like the following:</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

<span data-ttu-id="3479a-173">È possibile concatenare il metodo `OwnsOne` in un mapping Fluent.</span><span class="sxs-lookup"><span data-stu-id="3479a-173">It is possible to chain the `OwnsOne` method in a fluent mapping.</span></span> <span data-ttu-id="3479a-174">Nell'esempio ipotetico seguente `OrderDetails` è proprietario di `BillingAddress` e `ShippingAddress`, che sono entrambi tipi `Address`.</span><span class="sxs-lookup"><span data-stu-id="3479a-174">In the following hypothetical example, `OrderDetails` owns `BillingAddress` and `ShippingAddress`, which are both `Address` types.</span></span> <span data-ttu-id="3479a-175">Quindi `OrderDetails` è di proprietà del tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="3479a-175">Then `OrderDetails` is owned by the `Order` type.</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.OrderDetails, cb =>
    {
        cb.OwnsOne(c => c.BillingAddress);
        cb.OwnsOne(c => c.ShippingAddress);
    });
//...
//...
public class Order
{
    public int Id { get; set; }
    public OrderDetails OrderDetails { get; set; }
}

public class OrderDetails
{
    public Address BillingAddress { get; set; }
    public Address ShippingAddress { get; set; }
}

public class Address
{
    public string Street { get; set; }
    public string City { get; set; }
}
```

### <a name="additional-details-on-owned-entity-types"></a><span data-ttu-id="3479a-176">Altre informazioni sui tipi di entità di proprietà</span><span class="sxs-lookup"><span data-stu-id="3479a-176">Additional details on owned entity types</span></span>

<span data-ttu-id="3479a-177">• I tipi di proprietà vengono definiti quando si configura una proprietà di navigazione per un particolare tipo usando l'API Fluent OwnsOne.</span><span class="sxs-lookup"><span data-stu-id="3479a-177">•   Owned types are defined when you configure a navigation property to a particular type using the OwnsOne fluent API.</span></span>

<span data-ttu-id="3479a-178">• La definizione di un tipo di proprietà nel modello di metadati è composta da: tipo di proprietario, proprietà di navigazione e tipo CLR del tipo di proprietà.</span><span class="sxs-lookup"><span data-stu-id="3479a-178">•   The definition of an owned type in our metadata model is a composite of: the owner type, the navigation property, and the CLR type of the owned type.</span></span>

<span data-ttu-id="3479a-179">• L'identità (chiave) di un'istanza del tipo di proprietà in questo stack è composta dall'identità del tipo di proprietario e dalla definizione del tipo di proprietà.</span><span class="sxs-lookup"><span data-stu-id="3479a-179">•   The identity (key) of an owned type instance in our stack is a composite of the identity of the owner type and the definition of the owned type.</span></span>

#### <a name="owned-entities-capabilities"></a><span data-ttu-id="3479a-180">Funzionalità delle entità di proprietà:</span><span class="sxs-lookup"><span data-stu-id="3479a-180">Owned entities capabilities:</span></span>

<span data-ttu-id="3479a-181">• Il tipo di proprietà può fare riferimento ad altre entità, sia di proprietà (tipi di proprietà annidati) che non (proprietà di navigazione con normale riferimento ad altre entità).</span><span class="sxs-lookup"><span data-stu-id="3479a-181">•   Owned type can reference other entities, either owned (nested owned types) or non-owned (regular reference navigation properties to other entities).</span></span>

<span data-ttu-id="3479a-182">• È possibile eseguire il mapping dello stesso tipo CLR come tipi di proprietà diversi nella stessa entità del proprietario usando proprietà di navigazione distinte.</span><span class="sxs-lookup"><span data-stu-id="3479a-182">•   You can map the same CLR type as different owned types in the same owner entity through separate navigation properties.</span></span>

<span data-ttu-id="3479a-183">• La suddivisione di tabelle è configurata per convenzione, ma è possibile rifiutare esplicitamente eseguendo il mapping del tipo di proprietà in una tabella diversa usando ToTable.</span><span class="sxs-lookup"><span data-stu-id="3479a-183">•   Table splitting is setup by convention, but you can opt out by mapping the owned type to a different table using ToTable.</span></span>

<span data-ttu-id="3479a-184">• Il caricamento eager viene eseguito automaticamente sui tipi di proprietà, ad esempio non è necessario chiamare include () per la query.</span><span class="sxs-lookup"><span data-stu-id="3479a-184">•   Eager loading is performed automatically on owned types, i.e. no need to call Include() on the query.</span></span>

#### <a name="owned-entities-limitations"></a><span data-ttu-id="3479a-185">Limitazioni delle entità di proprietà:</span><span class="sxs-lookup"><span data-stu-id="3479a-185">Owned entities limitations:</span></span>

<span data-ttu-id="3479a-186">• Non è possibile creare un elemento DbSet<T> di un tipo di proprietà (per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="3479a-186">•   You cannot create a DbSet<T> of an owned type (by design).</span></span>

<span data-ttu-id="3479a-187">• Non è possibile chiamare ModelBuilder.Entity<T>() nei tipi di proprietà (attualmente per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="3479a-187">•   You cannot call ModelBuilder.Entity<T>() on owned types (currently by design).</span></span>

<span data-ttu-id="3479a-188">• Per ora non sono supportate le raccolte di tipi di proprietà, ma lo saranno nelle versioni dopo EF Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="3479a-188">•   No collections of owned types yet (but they will be supported in versions after EF Core 2.0).</span></span>

<span data-ttu-id="3479a-189">• Nessun supporto per la configurazione con un attributo.</span><span class="sxs-lookup"><span data-stu-id="3479a-189">•   No support for configuring them via an attribute.</span></span>

<span data-ttu-id="3479a-190">• Nessun supporto per i tipi di proprietà facoltativi (ad esempio nullable) di cui viene eseguito il mapping con il proprietario della tabella stessa, ad esempio con la suddivisione di tabelle.</span><span class="sxs-lookup"><span data-stu-id="3479a-190">•   No support for optional (i.e. nullable) owned types that are mapped with the owner in the same table (i.e. using table splitting).</span></span> <span data-ttu-id="3479a-191">Ciò è dovuto al fatto che non è disponibile un sentinel separato per null.</span><span class="sxs-lookup"><span data-stu-id="3479a-191">This is because we don't have a separate sentinel for the null.</span></span>

<span data-ttu-id="3479a-192">• Nessun supporto del mapping di ereditarietà per i tipi di proprietà, ma è possibile eseguire il mapping di due tipi di foglia delle stesse gerarchie di ereditarietà come tipi di proprietà diversi.</span><span class="sxs-lookup"><span data-stu-id="3479a-192">•   No inheritance mapping support for owned types, but you should be able to map two leaf types of the same inheritance hierarchies as different owned types.</span></span> <span data-ttu-id="3479a-193">EF Core non considera il fatto che fanno parte della stessa gerarchia.</span><span class="sxs-lookup"><span data-stu-id="3479a-193">EF Core will not reason about the fact that they are part of the same hierarchy.</span></span>

#### <a name="main-differences-with-ef6s-complex-types"></a><span data-ttu-id="3479a-194">Principali differenze rispetto ai i tipi complessi di EF6</span><span class="sxs-lookup"><span data-stu-id="3479a-194">Main differences with EF6's complex types</span></span>

<span data-ttu-id="3479a-195">• La suddivisione di tabelle è facoltativa, ossia si può scegliere di eseguirne in mapping a una tabella separata mantenendo lo stato di tipi di proprietà.</span><span class="sxs-lookup"><span data-stu-id="3479a-195">•   Table splitting is optional, i.e. they can optionally be mapped to a separate table and still be owned types.</span></span>

<span data-ttu-id="3479a-196">• Possono fare riferimento ad altre entità, ad esempio possono fungere da lato dipendente nelle relazioni con altri tipi non di proprietà.</span><span class="sxs-lookup"><span data-stu-id="3479a-196">•   They can reference other entities (i.e. they can act as the dependent side on relationships to other non-owned types).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="3479a-197">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3479a-197">Additional resources</span></span>

-   <span data-ttu-id="3479a-198">**Martin Fowler. Modello ValueObject**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="3479a-198">**Martin Fowler. ValueObject pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="3479a-199">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software (Progettazione basata su domini: gestire le complessità nel software).**</span><span class="sxs-lookup"><span data-stu-id="3479a-199">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="3479a-200">(Libro. Include una trattazione sugli oggetti valore) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="3479a-200">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="3479a-201">**Vaughn Vernon. Implementing Domain-Driven Design (Implementazione della progettazione basata su domini).**</span><span class="sxs-lookup"><span data-stu-id="3479a-201">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="3479a-202">(Libro. Include una trattazione sugli oggetti valore) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="3479a-202">(Book; includes a discussion of value objects) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="3479a-203">\*\*Proprietà shadow \*\*
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="3479a-203">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="3479a-204">**Complex types and/or value objects (Tipi complessi e/o oggetti valore)**.</span><span class="sxs-lookup"><span data-stu-id="3479a-204">**Complex types and/or value objects**.</span></span> <span data-ttu-id="3479a-205">Discussione nel repository GitHub di EF Core (scheda Issues) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span><span class="sxs-lookup"><span data-stu-id="3479a-205">Discussion in the EF Core GitHub repo (Issues tab) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span></span>

-   <span data-ttu-id="3479a-206">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="3479a-206">**ValueObject.cs.**</span></span> <span data-ttu-id="3479a-207">Classe oggetti valore di base in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="3479a-207">Base value object class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   <span data-ttu-id="3479a-208">**Address class (Classe di indirizzi).**</span><span class="sxs-lookup"><span data-stu-id="3479a-208">**Address class.**</span></span> <span data-ttu-id="3479a-209">Classe oggetti valore di esempio in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="3479a-209">Sample value object class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)



>[!div class="step-by-step"]
<span data-ttu-id="3479a-210">[Precedente](seedwork-domain-model-base-classes-interfaces.md)
[Successivo](enumeration-classes-over-enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="3479a-210">[Previous](seedwork-domain-model-base-classes-interfaces.md)
[Next](enumeration-classes-over-enum-types.md)</span></span>
