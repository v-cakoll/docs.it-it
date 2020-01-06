---
title: Uso delle classi di enumerazione anziché dei tipi enum
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Informazioni su come è possibile usare le classi di enumerazione anziché i tipi enum per risolvere alcune limitazioni di questi tipi.
ms.date: 10/08/2018
ms.openlocfilehash: 6752adb28b1bd0982c66fa2d021b04b999447c6e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337684"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a>Usare le classi di enumerazione anziché i tipi enum

Le [enumerazioni](../../../csharp/language-reference/builtin-types/enum.md) (o *tipi enum*) sono un sottile wrapper del linguaggio per un tipo integrale. È possibile limitarne l'uso quando si archivia un valore da un set di valori chiuso. La classificazione in base alle dimensioni (piccole, medie e grandi) rappresenta un buon esempio. L'uso delle enumerazioni per il flusso di controllo o per astrazioni più potenti può indicare difetti di programmazione noti come [code smell](https://deviq.com/code-smells/). Questo tipo di utilizzo determina un codice fragile con molte istruzioni del flusso di controllo che verificano i valori dell'enumerazione.

In alternativa, è possibile creare classi di enumerazione che abilitano tutte le funzionalità avanzate di un linguaggio orientato a oggetti.

Tuttavia, questo non è un argomento strategico e in molti casi, per semplicità è comunque possibile continuare a usare i normali [tipi enum](../../../csharp/language-reference/builtin-types/enum.md) se si preferisce. Comunque, l'uso delle classi di enumerazione è più strettamente correlato a concetti aziendali.

## <a name="implement-an-enumeration-base-class"></a>Implementare una classe di base di enumerazione

Il microservizio degli ordini nell'app eShopOnContainers fornisce un'implementazione della classe di base di enumerazione di esempio, come mostrato di seguito:

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString() => Name;

    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public |
                                         BindingFlags.Static |
                                         BindingFlags.DeclaredOnly);

        return fields.Select(f => f.GetValue(null)).Cast<T>();
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;

        if (otherValue == null)
            return false;

        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);

        return typeMatches && valueMatches;
    }

    public int CompareTo(object other) => Id.CompareTo(((Enumeration)other).Id);

    // Other utility methods ...
}
```

È possibile usare questa classe come un tipo in qualsiasi entità o oggetto valore, come per la classe `CardType` : `Enumeration` seguente:

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    public CardType(int id, string name)
        : base(id, name)
    {
    }
}
```

## <a name="additional-resources"></a>Risorse aggiuntive

- **Enum's are evil—update** \ (Gli enum sono il male: aggiornamento)
  <https://www.planetgeek.ch/2009/07/01/enums-are-evil/>

- **Daniel Harder. Come le enumerazioni diffondono la malattia e come curarla** \
  <https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/>

- **Jimmy Bogard. Classi di enumerazione** \
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- **Steve Smith. Alternative enum in C#**  \
  <https://ardalis.com/enum-alternatives-in-c>

- **Enumeration.cs.** Base Enumeration class in eShopOnContainers \ (Classe di enumerazione di base in eShopOnContainers)
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- **CardType.cs**. Classe di enumerazione di esempio in eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>

- **SmartEnum**. Ardalis - Classi che consentono di produrre enum fortemente tipizzati e più intelligenti in .NET. \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
>[Precedente](implement-value-objects.md)
>[Successivo](domain-model-layer-validations.md)
