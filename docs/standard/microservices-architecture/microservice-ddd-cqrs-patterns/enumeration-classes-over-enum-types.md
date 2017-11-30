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
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="5e844-104">Utilizzo di classi di enumerazione anziché tipi enum</span><span class="sxs-lookup"><span data-stu-id="5e844-104">Using Enumeration classes instead of enum types</span></span>

<span data-ttu-id="5e844-105">[Enumerazioni](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*enumerazioni* breve) sono wrapper language sottile per un tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="5e844-105">[Enumerations](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*enums* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="5e844-106">Si potrebbe voler limitare il relativo utilizzo per quando si desidera archiviare un valore da un set chiuso di valori.</span><span class="sxs-lookup"><span data-stu-id="5e844-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="5e844-107">Classificazione basata sulla sesso (ad esempio, male, femmina, sconosciuto), o le dimensioni (S, M, L, XL) sono i buoni esempi.</span><span class="sxs-lookup"><span data-stu-id="5e844-107">Classification based on gender (for example, male, female, unknown), or sizes (S, M, L, XL) are good examples.</span></span> <span data-ttu-id="5e844-108">È possibile utilizzare le enumerazioni per il flusso di controllo o astrazioni più affidabile un [codice odore](http://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="5e844-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="5e844-109">Questo tipo di utilizzo consentono al codice fragili con numerose istruzioni del flusso di controllo verifica i valori dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5e844-109">This type of usage will lead to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="5e844-110">In alternativa, è possibile creare le classi di enumerazione che consentono di tutte le funzionalità avanzate di un linguaggio orientato a oggetti.</span><span class="sxs-lookup"><span data-stu-id="5e844-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span> <span data-ttu-id="5e844-111">Tuttavia, non si tratta di un problema critico e in molti casi, per semplicità, è possibile comunque utilizzare enumerazioni regolari se le preferenze.</span><span class="sxs-lookup"><span data-stu-id="5e844-111">However, this is not a critical issue and in many cases, for simplicity, you can still use regular enums if that is your preference.</span></span>

## <a name="implementing-enumeration-classes"></a><span data-ttu-id="5e844-112">Implementazione di classi di enumerazione</span><span class="sxs-lookup"><span data-stu-id="5e844-112">Implementing Enumeration classes</span></span>

<span data-ttu-id="5e844-113">L'ordinamento microservizio in eShopOnContainers fornisce un'implementazione di esempio enumerazione della classe base, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5e844-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

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

<span data-ttu-id="5e844-114">È possibile utilizzare questa classe come un tipo in qualsiasi oggetto, entità o un valore per la classe di enumerazione CardType seguente.</span><span class="sxs-lookup"><span data-stu-id="5e844-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="5e844-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5e844-115">Additional resources</span></span>

-   <span data-ttu-id="5e844-116">**Enum sono male: aggiornare**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="5e844-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="5e844-117">**Daniel Hardman. Modalità di distribuzione di malattia enumerazioni e su come risolvere il**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="5e844-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="5e844-118">**Jimmy Bogard. Classi di enumerazione**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="5e844-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="5e844-119">**Steve Smith. Enumerazione alternative in c#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="5e844-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="5e844-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="5e844-120">**Enumeration.cs.**</span></span> <span data-ttu-id="5e844-121">Classe di enumerazione in eShopOnContainers base [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="5e844-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="5e844-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="5e844-122">**CardType.cs**.</span></span> <span data-ttu-id="5e844-123">Classe di enumerazione in eShopOnContainers di esempio.</span><span class="sxs-lookup"><span data-stu-id="5e844-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [<span data-ttu-id="5e844-124">*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span><span class="sxs-lookup"><span data-stu-id="5e844-124">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="5e844-125">[Precedente] (implementa-valore-objects.md) [Avanti] (dominio modello-livello validations.md)</span><span class="sxs-lookup"><span data-stu-id="5e844-125">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
