---
title: "Utilizzo di classi di enumerazione anziché tipi enum"
description: "Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Utilizzo di classi di enumerazione anziché tipi enum"
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1745198720fd12a9d26aab2d2afb2c5dd6b6b49d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a>Utilizzo di classi di enumerazione anziché tipi enum

[Enumerazioni](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*enumerazioni* breve) sono wrapper language sottile per un tipo integrale. Si potrebbe voler limitare il relativo utilizzo per quando si desidera archiviare un valore da un set chiuso di valori. Classificazione basata sulla sesso (ad esempio, male, femmina, sconosciuto), o le dimensioni (S, M, L, XL) sono i buoni esempi. È possibile utilizzare le enumerazioni per il flusso di controllo o astrazioni più affidabile un [codice odore](http://deviq.com/code-smells/). Questo tipo di utilizzo consentono al codice fragili con numerose istruzioni del flusso di controllo verifica i valori dell'enumerazione.

In alternativa, è possibile creare le classi di enumerazione che consentono di tutte le funzionalità avanzate di un linguaggio orientato a oggetti. Tuttavia, non si tratta di un problema critico e in molti casi, per semplicità, è possibile comunque utilizzare enumerazioni regolari se le preferenze.

## <a name="implementing-enumeration-classes"></a>Implementazione di classi di enumerazione

L'ordinamento microservizio in eShopOnContainers fornisce un'implementazione di esempio enumerazione della classe base, come illustrato nell'esempio seguente:

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }
    public int Id { get; private set; }

    protected Enumeration()
    {
    }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString()
    {
        return Name;
    }

    public static IEnumerable<T> GetAll<T>() where T : Enumeration, new()
    {
        var type = typeof(T);
        var fields = type.GetTypeInfo().GetFields(BindingFlags.Public |
            BindingFlags.Static |
            BindingFlags.DeclaredOnly);
        foreach (var info in fields)
        {
            var instance = new T();
            var locatedValue = info.GetValue(instance) as T;
            if (locatedValue != null)
            {
                yield return locatedValue;
            }
        }
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;
        if (otherValue == null)
        {
            return false;
        }
        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);
        return typeMatches && valueMatches;
    }

    public int CompareTo(object other)
    {
        return Id.CompareTo(((Enumeration)other).Id);
    }

    // Other utility methods ...
}
```

È possibile utilizzare questa classe come un tipo in qualsiasi oggetto, entità o un valore per la classe di enumerazione CardType seguente.

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    protected CardType() { }

    public CardType(int id, string name)
        : base(id, name)
    {
    }


    public static IEnumerable<CardType> List()
    {
        return new[] { Amex, Visa, MasterCard };
    }
    // Other util methods
}
```

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Enum sono male: aggiornare**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)

-   **Daniel Hardman. Modalità di distribuzione di malattia enumerazioni e su come risolvere il**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)

-   **Jimmy Bogard. Classi di enumerazione**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)

-   **Steve Smith. Enumerazione alternative in c#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)

-   **Enumeration.cs.** Classe di enumerazione in eShopOnContainers base [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)

-   **CardType.cs**. Classe di enumerazione in eShopOnContainers di esempio.
    [*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
[Precedente] (implementa-valore-objects.md) [Avanti] (dominio modello-livello validations.md)
