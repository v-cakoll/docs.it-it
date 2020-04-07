---
title: Implementazione di oggetti valore
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Informazioni su dettagli e opzioni per implementare oggetti valore con le nuove funzionalità di Entity Framework.
ms.date: 01/30/2020
ms.openlocfilehash: 4a8a92a8dabcf09654ecd0e5dea2a7df25d7abf7
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805744"
---
# <a name="implement-value-objects"></a>Implementare oggetti valore

Come descritto nelle sezioni precedenti relative a entità e aggregazioni, l'identità è un elemento fondamentale per le entità. Tuttavia, esistono numerosi oggetti ed elementi di dati in un sistema che non richiedono un'identità e la verifica dell'identità, ad esempio gli oggetti valore.

Un oggetto valore può fare riferimento ad altre entità. Ad esempio, in un'applicazione che genera una route che descrive come passare da un punto a altro, questa route sarebbe un oggetto valore. Corrisponderebbe a uno snapshot di punti in una route specifica, tuttavia la route suggerita non avrebbe un'identità, anche se internamente potrebbe fare riferimento a entità come City, Road e così via.

La figura 7-13 illustra l'oggetto valore Address all'interno dell'aggregazione Order.

![Diagramma che mostra l'oggetto valore Indirizzo all'interno dell'aggregazione dell'ordine.](./media/implement-value-objects/value-object-within-aggregate.png)

**Figura 7-13**. Oggetto valore Address all'interno dell'aggregazione Order

Come illustrato nella figura 7-13, un'entità è generalmente composta da più attributi. Ad esempio, `Order` l'entità può essere modellata come un'entità con un'identità e composta internamente da un set di attributi, ad esempio OrderId, OrderDate, OrderItems e così via. Ma l'indirizzo, che è semplicemente un valore complesso composto da paese / regione, strada, città, ecc e non ha identità in questo dominio, deve essere modellato e trattato come un oggetto valore.

## <a name="important-characteristics-of-value-objects"></a>Caratteristiche importanti degli oggetti valore

Esistono due caratteristiche principali proprie degli oggetti valore:

- Non hanno identità.

- Non sono modificabili.

La prima caratteristica è già stata descritta. L'immutabilità è un requisito importante. Dopo aver creato l'oggetto, i valori di un oggetto valore non devono essere modificabili. Pertanto, quando l'oggetto viene costruito, è necessario fornire i valori necessari, ma non è necessario consentire loro di modificare durante la durata dell'oggetto.

Gli oggetti valore consentono di eseguire alcune operazioni per migliorare le prestazioni, grazie alla loro natura non modificabile. Ciò vale soprattutto nei sistemi in cui possono essere presenti migliaia di istanze di un oggetto valore, molte delle quali contengono gli stessi valori. La natura non modificabile di questi oggetti ne consente il riutilizzo. Sono anche intercambiabili perché i loro valori sono uguali e non hanno alcuna identità. A volte, questo tipo di ottimizzazione può fare la differenza tra un software eseguito lentamente e uno con prestazioni ottimali. Naturalmente, tutti questi casi dipendono l'ambiente dell'applicazione e dal contesto di distribuzione.

## <a name="value-object-implementation-in-c"></a>Implementazione dell'oggetto valore in C\#

In termini di implementazione, è possibile avere una classe di base di oggetti valore contenente metodi di utilità di base come l'uguaglianza basata sul confronto tra tutti gli attributi (perché un oggetto valore non deve essere basato sull'identità) e altre caratteristiche fondamentali. L'esempio seguente mostra una classe di base di oggetti valore usata nel microservizio degli ordini di eShopOnContainers.

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
    // Other utility methods
}
```

È possibile usare questa classe quando si implementa l'oggetto valore effettivo, ad esempio l'oggetto valore Address mostrato nell'esempio seguente:

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

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

Si può vedere come questa implementazione dell'oggetto valore di Address non abbia alcuna identità, e quindi alcun campo ID, né a livello della classe Address, né a livello della classe ValueObject.

Non avendo alcun campo ID in una classe da utilizzare da Entity Framework (EF) non era possibile fino a Entity Framework Core 2.0, che consente notevolmente di implementare oggetti di valore migliore senza ID. Tutto ciò viene illustrato nella prossima sezione.

Si potrebbe sostenere che gli oggetti di valore, essendo immutabili, devono essere di sola lettura (vale a dire, hanno proprietà get-only), e questo è davvero. Tuttavia, gli oggetti valore vengono in genere serializzati e deserializzati per passare attraverso le code di messaggi `private set`e l'essere di sola lettura impedisce al deserializzatore di assegnare valori, pertanto è sufficiente lasciarli come , che è sufficientemente di sola lettura per essere pratico.

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20-and-later"></a>Come rendere persistenti gli oggetti valore nel database con EF Core 2.0 e versioni successiveHow to persist value objects in the database with EF Core 2.0 and later

È stato appena descritto come definire un oggetto valore nel modello di dominio. Ma come è effettivamente possibile rendere effettivamente persistente nel database utilizzando Entity Framework Core poiché in genere è destinato alle entità con identità?

### <a name="background-and-older-approaches-using-ef-core-11"></a>Approcci generali e precedenti con l'uso di EF Core 1.1

Come sfondo, una limitazione quando si utilizza EF Core 1.0 e 1.1 era che non è possibile utilizzare [tipi complessi](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) come definito in EF 6.x in .NET Framework tradizionale. Quindi, se si usava EF Core 1.0 o 1.1, era necessario archiviare l'oggetto di valore come entità EF con un campo ID. Successivamente, per farlo somigliare di più a un oggetto valore senza identità, era possibile nascondere l'ID per indicare che l'identità di un oggetto valore non è importante nel modello di dominio. L'ID poteva essere nascosto trasformandolo in una [proprietà shadow](https://docs.microsoft.com/ef/core/modeling/shadow-properties ). Dal momento che la configurazione per nascondere l'ID del modello viene configurata nel livello di infrastruttura di EF, risulterebbe trasparente per il modello di dominio.

Nella versione iniziale di eShopOnContainers (.NET Core 1.1), l'ID nascosto necessario per l'infrastruttura EF Core era implementato nel modo seguente nel livello DbContext, usando l'API Fluent nel progetto di infrastruttura. Quindi, l'ID risultava nascosto per il modello di dominio, ma era ancora presente nell'infrastruttura.

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

La persistenza dell'oggetto valore nel database era comunque assicurata usando un'entità normale in un'altra tabella.

Con EF Core 2.0 e versioni successive, esistono modi nuovi e migliori per rendere persistenti gli oggetti valore.

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20-and-later"></a>Rendere persistenti gli oggetti valore come tipi di entità di proprietà in Entity Framework Core 2.0 e versioni successivePersist value objects as owned entity types in EF Core 2.0 and later

Anche con alcuni spazi tra il modello di oggetto valore canonico in DDD e il tipo di entità di proprietà in Entity Framework Core, è attualmente il modo migliore per rendere persistenti gli oggetti valore con Entity Framework Core 2.0 e versioni successive. È possibile vedere le limitazioni alla fine di questa sezione.

La funzionalità dei tipi di entità di proprietà è stata aggiunta a EF Core a partire dalla versione 2.0.

Un tipo di entità di proprietà consente di eseguire il mapping dei tipi che non hanno un'identità definita in modo esplicito nel modello di dominio e che vengono usati come proprietà, ad esempio un oggetto valore, all'interno di qualsiasi entità. Un tipo di entità di proprietà condivide lo stesso tipo CLR con un altro tipo di entità, ovvero è solo una classe normale. L'entità contenente la navigazione che lo definisce è l'entità del proprietario. Quando si esegue una query sul proprietario, i tipi di proprietà vengono inclusi per impostazione predefinita.

Basta guardare il modello di dominio, un tipo di proprietà sembra che non ha alcuna identità. invece la ha, ma la proprietà di navigazione del proprietario fa parte di questa identità.

L'identità delle istanze dei tipi di proprietà non è del tutto esclusiva, ma è costituita da tre componenti:

- L'identità del proprietario

- La proprietà di navigazione che punta alle istanze

- Nel caso di raccolte di tipi di proprietà, un componente indipendente (supportato in EF Core 2.2 e versioni successive).

Ad esempio, nel modello di dominio degli ordini in eShopOnContainers, all'interno dell'entità Order, l'oggetto valore Address viene implementato come un tipo di entità di proprietà all'interno dell'entità del proprietario, ovvero l'entità Order. Address è un tipo la cui proprietà identità non è definita nel modello di dominio. Viene usato come proprietà del tipo Order per specificare l'indirizzo di spedizione per uno specifico ordine.

Per convenzione viene creata una chiave primaria shadow per il tipo di proprietà e ne viene eseguito il mapping alla stessa tabella del proprietario usando la suddivisione di tabelle. Ciò consente di usare i tipi di proprietà in modo simile ai tipi complessi in EF6 in .NET Framework tradizionale.

È importante notare che, per convenzione, i tipi di proprietà non vengono mai individuati in EF Core, quindi è necessario dichiararli in modo esplicito.

In eShopOnContainers, nel file OrderingContext.cs, all'interno del `OnModelCreating()` metodo, vengono applicate più configurazioni dell'infrastruttura. Una di esse è correlata all'entità Order.

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

Nel codice seguente l'infrastruttura di persistenza è definita per l'entità Order:

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

Nel codice precedente il metodo `orderConfiguration.OwnsOne(o => o.Address)` specifica che la proprietà `Address` è un'entità di proprietà del tipo `Order`.

Per impostazione predefinita, le convenzioni di EF Core nome le colonne del database per le proprietà del tipo di entità di proprietà come `EntityProperty_OwnedEntityProperty`. Di conseguenza, `Address` le proprietà `Orders` interne di `Address_Street`verranno visualizzate nella tabella con i nomi `Address_City` , (e così via per `State`, `Country`, e `ZipCode`).

È possibile aggiungere il metodo Fluent `Property().HasColumnName()` per rinominare le colonne. Se `Address` è una proprietà pubblica, i mapping sono simili ai seguenti:

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

È possibile concatenare `OwnsOne` il metodo in una mappatura fluente. Nell'esempio ipotetico seguente `OrderDetails` è proprietario di `BillingAddress` e `ShippingAddress`, che sono entrambi tipi `Address`. Quindi `OrderDetails` è di proprietà del tipo `Order`.

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

### <a name="additional-details-on-owned-entity-types"></a>Altre informazioni sui tipi di entità di proprietà

- I tipi di proprietà vengono definiti quando si configura una proprietà di navigazione su un tipo particolare usando l'API Fluent OwnsOne.

- La definizione di un tipo di proprietà nel modello di metadati è composta da: tipo di proprietario, proprietà di navigazione e tipo CLR del tipo di proprietà.

- L'identità (chiave) di un'istanza del tipo di proprietà in questo stack è composta dall'identità del tipo di proprietario e dalla definizione del tipo di proprietà.

#### <a name="owned-entities-capabilities"></a>Funzionalità delle entità di proprietà

- I tipi di proprietà possono fare riferimento ad altre entità, sia di proprietà (tipi di proprietà annidati) che non (proprietà di navigazione con normale riferimento ad altre entità).

- È possibile eseguire il mapping dello stesso tipo CLR come tipi di proprietà diversi nella stessa entità del proprietario usando proprietà di navigazione distinte.

- Table splitting is set up by convention, but you can opt out by mapping the owned type to a different table using ToTable.

- Il caricamento rapido viene eseguito automaticamente sui tipi di `.Include()` proprietà, ovvero non è necessario chiamare la query.

- Può essere configurato `[Owned]`con l'attributo , utilizzando EF Core 2.1 e versioni successive.

- Può gestire raccolte di tipi di proprietà (utilizzando la versione 2.2 e successive).

#### <a name="owned-entities-limitations"></a>Limitazioni delle entità di proprietà

- Non è possibile `DbSet<T>` creare un di un tipo di proprietà (in base alla progettazione).

- Non è possibile `ModelBuilder.Entity<T>()` chiamare i tipi di proprietà (attualmente in base alla progettazione).

- Nessun supporto per i tipi di proprietà facoltativi ( ovvero nullable) mappati con il proprietario nella stessa tabella, ovvero utilizzando la suddivisione della tabella. Questo avviene perché il mapping viene eseguito per ogni proprietà, non abbiamo una sentinel separata per il valore complesso null nel suo complesso.

- Nessun supporto per il mapping di ereditarietà per i tipi di proprietà, ma dovrebbe essere possibile eseguire il mapping di due tipi foglia delle stesse gerarchie di ereditarietà dei diversi tipi di proprietà. EF Core non considera il fatto che fanno parte della stessa gerarchia.

#### <a name="main-differences-with-ef6s-complex-types"></a>Principali differenze rispetto ai i tipi complessi di EF6

- La suddivisione delle tabelle è facoltativa, ovvero può essere facoltativamente mappata a una tabella separata ed è comunque di essere di proprietà.

- Possono fare riferimento ad altre entità, ovvero possono fungere da lato dipendente per le relazioni con altri tipi non di proprietà.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Martin Fowler. Modello ValueObject** \
  <https://martinfowler.com/bliki/ValueObject.html>

- **Eric Evans. Progettazione basata su domini: affrontare la complessità nel cuore del software.** (Libro. Include una trattazione sugli oggetti valore) \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- **Vaughn Vernon. Implementazione della progettazione basata su dominio.** (Libro. Include una trattazione sugli oggetti valore) \
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- **Tipi di entità di proprietà** \
  <https://docs.microsoft.com/ef/core/modeling/owned-entities>

- **Proprietà ombra** \
  <https://docs.microsoft.com/ef/core/modeling/shadow-properties>

- **Complex types and/or value objects (Tipi complessi e/o oggetti valore)**. Discussione nel repository GitHub di EF Core (scheda Issues) \
  <https://github.com/dotnet/efcore/issues/246>

- **ValueObject.cs.** Classe oggetti valore di base in eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs>

- **Address class (Classe di indirizzi).** Classe oggetti valore di esempio in eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs>

> [!div class="step-by-step"]
> [Successivo](seedwork-domain-model-base-classes-interfaces.md)
> [precedente](enumeration-classes-over-enum-types.md)
