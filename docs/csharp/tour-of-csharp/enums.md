---
title: Enumerazioni C# - Panoramica del linguaggio C#
description: Informazioni sulle enumerazioni, costanti denominate discrete in C#
ms.date: 08/10/2016
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: 7fe2626381cb90e55842e3be17dd450eb73d5a5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353354"
---
# <a name="enums"></a><span data-ttu-id="e5b1a-103">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="e5b1a-103">Enums</span></span>

<span data-ttu-id="e5b1a-104">Un ***tipo enum*** è un tipo valore distinto con un set di costanti denominate.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-104">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="e5b1a-105">Le enumerazioni vengono definite quando è necessario specificare un tipo che può avere un set di valori discreti.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-105">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="e5b1a-106">Le enumerazioni usano uno dei tipi valore integrali come archiviazione sottostante</span><span class="sxs-lookup"><span data-stu-id="e5b1a-106">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="e5b1a-107">e offrono significato semantico ai valori discreti.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-107">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="e5b1a-108">Nell'esempio seguente viene dichiarato e usato un tipo `enum` denominato `Color` con tre valori di costante, `Red`, `Green` e `Blue`.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-108">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

<span data-ttu-id="e5b1a-109">Ogni tipo `enum` ha un tipo integrale corrispondente, denominato ***tipo sottostante*** del tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-109">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="e5b1a-110">Un tipo `enum` che non dichiara in modo esplicito un tipo sottostante ha un tipo sottostante di `int`.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-110">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="e5b1a-111">Il formato di archiviazione di un tipo `enum` e l'intervallo di valori possibili sono determinati dal tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-111">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="e5b1a-112">Il set di valori che un tipo `enum` può richiedere non è limitato dai relativi membri `enum`.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-112">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="e5b1a-113">In particolare, è possibile eseguire il cast di qualsiasi valore del tipo sottostante di un tipo `enum` al tipo `enum`. Si tratta di un valore valido distinto del tipo `enum` in questione.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-113">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="e5b1a-114">Nell'esempio seguente viene dichiarato un tipo `enum` denominato `Alignment` con un tipo sottostante di `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-114">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

<span data-ttu-id="e5b1a-115">Come mostrato dall'esempio precedente, una dichiarazione di membro `enum` può includere un'espressione costante che specifica il valore del membro stesso.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-115">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="e5b1a-116">Il valore della costante di ciascun membro `enum` deve essere compreso nell'intervallo del tipo sottostante di `enum`.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-116">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="e5b1a-117">Quando una dichiarazione di membro `enum` non specifica in modo esplicito un valore, al membro viene assegnato il valore zero (se è il primo membro del tipo `enum`) o il valore del membro `enum` testualmente precedente più uno.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-117">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="e5b1a-118">I valori `Enum` possono essere convertiti in valori integrali e viceversa usando i cast di tipo.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-118">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="e5b1a-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5b1a-119">For example:</span></span>

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

<span data-ttu-id="e5b1a-120">Il valore predefinito di qualsiasi tipo `enum` è il valore integrale zero convertito nel tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-120">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="e5b1a-121">Nei casi in cui le variabili vengono inizializzate automaticamente con un valore predefinito, tale valore viene assegnato alle variabili dei tipi `enum`.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-121">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="e5b1a-122">Per rendere facilmente disponibile il valore predefinito di un tipo `enum`, il valore letterale `0` viene implicitamente convertito in qualsiasi tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-122">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="e5b1a-123">Di conseguenza, quanto riportato di seguito è consentito.</span><span class="sxs-lookup"><span data-stu-id="e5b1a-123">Thus, the following is permitted.</span></span>

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
<span data-ttu-id="e5b1a-124">[Precedente](interfaces.md)
[Successivo](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="e5b1a-124">[Previous](interfaces.md)
[Next](delegates.md)</span></span>
