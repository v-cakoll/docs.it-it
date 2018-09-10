---
title: Uso delle classi di enumerazione anziché dei tipi enum
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Uso delle classi di enumerazione anziché dei tipi enum
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: f1b88d160d6532c2a768684b55cd236417699322
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44194994"
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="455f6-103">Uso delle classi di enumerazione anziché dei tipi enum</span><span class="sxs-lookup"><span data-stu-id="455f6-103">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="455f6-104">Le [enumerazioni](../../../../docs/csharp/language-reference/keywords/enum.md) (o *tipi enum*) sono un sottile wrapper del linguaggio per un tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="455f6-104">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="455f6-105">È possibile limitarne l'uso quando si archivia un valore da un set di valori chiuso.</span><span class="sxs-lookup"><span data-stu-id="455f6-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="455f6-106">La classificazione in base alle dimensioni (piccole, medie e grandi) rappresenta un buon esempio.</span><span class="sxs-lookup"><span data-stu-id="455f6-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="455f6-107">L'uso delle enumerazioni per il flusso di controllo o per astrazioni più potenti può indicare difetti di programmazione noti come [code smell](http://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="455f6-107">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="455f6-108">Questo tipo di utilizzo determina un codice fragile con molte istruzioni del flusso di controllo che verificano i valori dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="455f6-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="455f6-109">In alternativa, è possibile creare classi di enumerazione che abilitano tutte le funzionalità avanzate di un linguaggio orientato a oggetti.</span><span class="sxs-lookup"><span data-stu-id="455f6-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="455f6-110">Tuttavia, questo non è un argomento strategico e in molti casi, per semplicità è comunque possibile continuare a usare i normali [tipi enum](../../../../docs/csharp/language-reference/keywords/enum.md) se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="455f6-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="455f6-111">Implementazione di una classe di base di enumerazione</span><span class="sxs-lookup"><span data-stu-id="455f6-111">Implementing an Enumeration base class</span></span>

<span data-ttu-id="455f6-112">Il microservizio degli ordini nell'app eShopOnContainers fornisce un'implementazione della classe di base di enumerazione di esempio, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="455f6-112">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

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
    
    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public | BindingFlags.Static | BindingFlags.DeclaredOnly);

        return fields.Select(f => f.GetValue(null)).Cast<T>();
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

<span data-ttu-id="455f6-113">È possibile usare questa classe come un tipo in qualsiasi entità o oggetto valore, come per la classe di enumerazione CardType seguente:</span><span class="sxs-lookup"><span data-stu-id="455f6-113">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

```csharp
public abstract class CardType : Enumeration
{
    public static CardType Amex = new AmexCardType();
    public static CardType Visa = new VisaCardType();
    public static CardType MasterCard = new MasterCardType();

    protected CardType(int id, string name)
        : base(id, name)
    {
    }

    private class AmexCardType : CardType
    {
        public AmexCardType(): base(1, "Amex")
        { }
    }
    
    private class VisaCardType : CardType
    {
        public VisaCardType(): base(2, "Visa")
        { }
    }
    
    private class MasterCardType : CardType
    {
        public MasterCardType(): base(3, "MasterCard")
        { }
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="455f6-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="455f6-114">Additional resources</span></span>

-   <span data-ttu-id="455f6-115">**Enum's are evil—update**
    [*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/) (Gli enum sono il male: aggiornamento)</span><span class="sxs-lookup"><span data-stu-id="455f6-115">**Enum’s are evil—update**
[*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="455f6-116">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/) (In che modo gli enum diffondono malattie, e come curarle)</span><span class="sxs-lookup"><span data-stu-id="455f6-116">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="455f6-117">**Jimmy Bogard. Enumeration classes**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/) (Classi di enumerazione)</span><span class="sxs-lookup"><span data-stu-id="455f6-117">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="455f6-118">**Steve Smith. Enum Alternatives in C#**
    [*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c) (Alternative agli enum in C#)</span><span class="sxs-lookup"><span data-stu-id="455f6-118">**Steve Smith. Enum Alternatives in C#**
[*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="455f6-119">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="455f6-119">**Enumeration.cs.**</span></span> <span data-ttu-id="455f6-120">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs) (Classe di enumerazione di base in eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="455f6-120">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="455f6-121">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="455f6-121">**CardType.cs**.</span></span> <span data-ttu-id="455f6-122">Classe di enumerazione di esempio in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="455f6-122">Sample Enumeration class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="455f6-123">[Precedente](implement-value-objects.md)
[Successivo](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="455f6-123">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
