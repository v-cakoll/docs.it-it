---
title: Uso delle classi di enumerazione anziché dei tipi enum
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Uso delle classi di enumerazione anziché dei tipi enum
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 57ff60ea01421f1a2a0466b7de9716b72b02d2c1
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2018
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="f002b-104">Uso delle classi di enumerazione anziché dei tipi enum</span><span class="sxs-lookup"><span data-stu-id="f002b-104">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="f002b-105">Le [enumerazioni](../../../../docs/csharp/language-reference/keywords/enum.md) (o *tipi enum*) sono un sottile wrapper del linguaggio per un tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="f002b-105">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="f002b-106">È possibile limitarne l'uso quando si archivia un valore da un set di valori chiuso.</span><span class="sxs-lookup"><span data-stu-id="f002b-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="f002b-107">La classificazione in base al sesso, ad esempio uomo, donna, sconosciuto, o alle taglie, come Small, Medium e Large, costituisce un ottimo esempio.</span><span class="sxs-lookup"><span data-stu-id="f002b-107">Classification based on gender (for example, male, female, unknown) or sizes (small, medium, large) are good examples.</span></span> <span data-ttu-id="f002b-108">L'uso delle enumerazioni per il flusso di controllo o per astrazioni più potenti può indicare difetti di programmazione noti come [code smell](http://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="f002b-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="f002b-109">Questo tipo di utilizzo determina un codice fragile con molte istruzioni del flusso di controllo che verificano i valori dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f002b-109">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="f002b-110">In alternativa, è possibile creare classi di enumerazione che abilitano tutte le funzionalità avanzate di un linguaggio orientato a oggetti.</span><span class="sxs-lookup"><span data-stu-id="f002b-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="f002b-111">Tuttavia, questo non è un argomento strategico e in molti casi, per semplicità è comunque possibile continuare a usare i normali [tipi enum](../../../../docs/csharp/language-reference/keywords/enum.md) se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="f002b-111">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="f002b-112">Implementazione di una classe di base di enumerazione</span><span class="sxs-lookup"><span data-stu-id="f002b-112">Implementing an Enumeration base class</span></span>

<span data-ttu-id="f002b-113">Il microservizio degli ordini nell'app eShopOnContainers fornisce un'implementazione della classe di base di enumerazione di esempio, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f002b-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; }
    public int Id { get; }

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

<span data-ttu-id="f002b-114">È possibile usare questa classe come un tipo in qualsiasi entità o oggetto valore, come per la classe di enumerazione CardType seguente:</span><span class="sxs-lookup"><span data-stu-id="f002b-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="f002b-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f002b-115">Additional resources</span></span>

-   <span data-ttu-id="f002b-116">**Enum's are evil—update**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/) (Gli enum sono il male: aggiornamento)</span><span class="sxs-lookup"><span data-stu-id="f002b-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="f002b-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/) (In che modo gli enum diffondono malattie, e come curarle)</span><span class="sxs-lookup"><span data-stu-id="f002b-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="f002b-118">**Jimmy Bogard. Enumeration classes**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/) (Classi di enumerazione)</span><span class="sxs-lookup"><span data-stu-id="f002b-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="f002b-119">**Steve Smith. Enum Alternatives in C#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c) (Alternative agli enum in C#)</span><span class="sxs-lookup"><span data-stu-id="f002b-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="f002b-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="f002b-120">**Enumeration.cs.**</span></span> <span data-ttu-id="f002b-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs) (Classe di enumerazione di base in eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="f002b-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="f002b-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="f002b-122">**CardType.cs**.</span></span> <span data-ttu-id="f002b-123">Classe di enumerazione di esempio in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="f002b-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="f002b-124">[Indietro] (implement-value-objects.md) [Avanti] (domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="f002b-124">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
