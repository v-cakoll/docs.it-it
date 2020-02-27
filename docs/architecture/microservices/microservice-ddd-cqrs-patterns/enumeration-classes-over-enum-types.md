---
title: Uso delle classi di enumerazione anziché dei tipi enum
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Informazioni su come è possibile usare le classi di enumerazione anziché i tipi enum per risolvere alcune limitazioni di questi tipi.
ms.date: 10/08/2018
ms.openlocfilehash: 82bd80d19b3b73eb2f45ede8cc7ad4593c688277
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628462"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="8ae54-103">Usare le classi di enumerazione anziché i tipi enum</span><span class="sxs-lookup"><span data-stu-id="8ae54-103">Use enumeration classes instead of enum types</span></span>

<span data-ttu-id="8ae54-104">Le [enumerazioni](../../../csharp/language-reference/builtin-types/enum.md) (o *tipi enum*) sono un sottile wrapper del linguaggio per un tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="8ae54-104">[Enumerations](../../../csharp/language-reference/builtin-types/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="8ae54-105">È possibile limitarne l'uso quando si archivia un valore da un set di valori chiuso.</span><span class="sxs-lookup"><span data-stu-id="8ae54-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="8ae54-106">La classificazione in base alle dimensioni (piccole, medie e grandi) rappresenta un buon esempio.</span><span class="sxs-lookup"><span data-stu-id="8ae54-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="8ae54-107">L'uso delle enumerazioni per il flusso di controllo o per astrazioni più potenti può indicare difetti di programmazione noti come [code smell](https://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="8ae54-107">Using enums for control flow or more robust abstractions can be a [code smell](https://deviq.com/code-smells/).</span></span> <span data-ttu-id="8ae54-108">Questo tipo di utilizzo determina un codice fragile con molte istruzioni del flusso di controllo che verificano i valori dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="8ae54-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="8ae54-109">In alternativa, è possibile creare classi di enumerazione che abilitano tutte le funzionalità avanzate di un linguaggio orientato a oggetti.</span><span class="sxs-lookup"><span data-stu-id="8ae54-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="8ae54-110">Tuttavia, questo non è un argomento strategico e in molti casi, per semplicità è comunque possibile continuare a usare i normali [tipi enum](../../../csharp/language-reference/builtin-types/enum.md) se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="8ae54-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../csharp/language-reference/builtin-types/enum.md) if that's your preference.</span></span> <span data-ttu-id="8ae54-111">Comunque, l'uso delle classi di enumerazione è più strettamente correlato a concetti aziendali.</span><span class="sxs-lookup"><span data-stu-id="8ae54-111">Anyway, the use of enumeration classes is more related to business-related concepts.</span></span>

## <a name="implement-an-enumeration-base-class"></a><span data-ttu-id="8ae54-112">Implementare una classe di base di enumerazione</span><span class="sxs-lookup"><span data-stu-id="8ae54-112">Implement an Enumeration base class</span></span>

<span data-ttu-id="8ae54-113">Il microservizio degli ordini nell'app eShopOnContainers fornisce un'implementazione della classe di base di enumerazione di esempio, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8ae54-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

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

<span data-ttu-id="8ae54-114">È possibile usare questa classe come un tipo in qualsiasi entità o oggetto valore, come per la classe `CardType` : `Enumeration` seguente:</span><span class="sxs-lookup"><span data-stu-id="8ae54-114">You can use this class as a type in any entity or value object, as for the following `CardType` : `Enumeration` class:</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="8ae54-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8ae54-115">Additional resources</span></span>

- <span data-ttu-id="8ae54-116">**Jimmy Bogard. Classi di enumerazione** </span><span class="sxs-lookup"><span data-stu-id="8ae54-116">**Jimmy Bogard. Enumeration classes** </span></span>\
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- <span data-ttu-id="8ae54-117">**Steve Smith. Alternative enum in C#**  </span><span class="sxs-lookup"><span data-stu-id="8ae54-117">**Steve Smith. Enum Alternatives in C#** </span></span>\
  <https://ardalis.com/enum-alternatives-in-c>

- <span data-ttu-id="8ae54-118">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="8ae54-118">**Enumeration.cs.**</span></span> <span data-ttu-id="8ae54-119">Base Enumeration class in eShopOnContainers (Classe di enumerazione di base in eShopOnContainers) </span><span class="sxs-lookup"><span data-stu-id="8ae54-119">Base Enumeration class in eShopOnContainers </span></span>\
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- <span data-ttu-id="8ae54-120">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="8ae54-120">**CardType.cs**.</span></span> <span data-ttu-id="8ae54-121">Classe di enumerazione di esempio in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8ae54-121">Sample Enumeration class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>

- <span data-ttu-id="8ae54-122">**SmartEnum**.</span><span class="sxs-lookup"><span data-stu-id="8ae54-122">**SmartEnum**.</span></span> <span data-ttu-id="8ae54-123">Ardalis - Classi che consentono di produrre enum fortemente tipizzati e più intelligenti in .NET.</span><span class="sxs-lookup"><span data-stu-id="8ae54-123">Ardalis - Classes to help produce strongly typed smarter enums in .NET.</span></span> \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
><span data-ttu-id="8ae54-124">[Precedente](implement-value-objects.md)
>[Successivo](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="8ae54-124">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
