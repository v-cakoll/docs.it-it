---
title: Enumerazioni C# - Panoramica del linguaggio C#
description: Informazioni sulle enumerazioni, costanti denominate discrete in C#
keywords: .NET, csharp
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 77d315dd87d9cab32605de415674d146eb9115fa
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
    
# <a name="enums"></a><span data-ttu-id="e098e-104">Enumerazioni</span><span class="sxs-lookup"><span data-stu-id="e098e-104">Enums</span></span>

<span data-ttu-id="e098e-105">Un ***tipo enum*** è un tipo valore distinto con un set di costanti denominate.</span><span class="sxs-lookup"><span data-stu-id="e098e-105">An ***enum type*** is a distinct value type with a set of named constants.</span></span> <span data-ttu-id="e098e-106">Le enumerazioni vengono definite quando è necessario specificare un tipo che può avere un set di valori discreti.</span><span class="sxs-lookup"><span data-stu-id="e098e-106">You define enums when you need to define a type that can have a set of discrete values.</span></span> <span data-ttu-id="e098e-107">Le enumerazioni usano uno dei tipi valore integrali come archiviazione sottostante</span><span class="sxs-lookup"><span data-stu-id="e098e-107">They use one of the integral value types as their underlying storage.</span></span> <span data-ttu-id="e098e-108">e offrono significato semantico ai valori discreti.</span><span class="sxs-lookup"><span data-stu-id="e098e-108">They provide semantic meaning to the discrete values.</span></span>

<span data-ttu-id="e098e-109">Nell'esempio seguente viene dichiarato e usato un tipo `enum` denominato `Color` con tre valori di costante, `Red`, `Green` e `Blue`.</span><span class="sxs-lookup"><span data-stu-id="e098e-109">The following example declares and uses an `enum` type named `Color` with three constant values, `Red`, `Green`, and `Blue`.</span></span>

<span data-ttu-id="e098e-110">[!code-csharp[Esempio enum](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]</span><span class="sxs-lookup"><span data-stu-id="e098e-110">[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]</span></span>

<span data-ttu-id="e098e-111">Ogni tipo `enum` ha un tipo integrale corrispondente, denominato ***tipo sottostante*** del tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="e098e-111">Each `enum` type has a corresponding integral type called the ***underlying type*** of the `enum` type.</span></span> <span data-ttu-id="e098e-112">Un tipo `enum` che non dichiara in modo esplicito un tipo sottostante ha un tipo sottostante di `int`.</span><span class="sxs-lookup"><span data-stu-id="e098e-112">An `enum` type that does not explicitly declare an underlying type has an underlying type of `int`.</span></span> <span data-ttu-id="e098e-113">Il formato di archiviazione di un tipo `enum` e l'intervallo di valori possibili sono determinati dal tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="e098e-113">An `enum` type’s storage format and range of possible values are determined by its underlying type.</span></span> <span data-ttu-id="e098e-114">Il set di valori che un tipo `enum` può richiedere non è limitato dai relativi membri `enum`.</span><span class="sxs-lookup"><span data-stu-id="e098e-114">The set of values that an `enum` type can take on is not limited by its `enum` members.</span></span> <span data-ttu-id="e098e-115">In particolare, è possibile eseguire il cast di qualsiasi valore del tipo sottostante di un tipo `enum` al tipo `enum`. Si tratta di un valore valido distinto del tipo `enum` in questione.</span><span class="sxs-lookup"><span data-stu-id="e098e-115">In particular, any value of the underlying type of an `enum` can be cast to the `enum` type and is a distinct valid value of that `enum` type.</span></span>

<span data-ttu-id="e098e-116">Nell'esempio seguente viene dichiarato un tipo `enum` denominato `Alignment` con un tipo sottostante di `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="e098e-116">The following example declares an `enum` type named `Alignment` with an underlying type of `sbyte`.</span></span>

<span data-ttu-id="e098e-117">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]</span><span class="sxs-lookup"><span data-stu-id="e098e-117">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]</span></span>

<span data-ttu-id="e098e-118">Come mostrato dall'esempio precedente, una dichiarazione di membro `enum` può includere un'espressione costante che specifica il valore del membro stesso.</span><span class="sxs-lookup"><span data-stu-id="e098e-118">As shown by the previous example, an `enum` member declaration can include a constant expression that specifies the value of the member.</span></span> <span data-ttu-id="e098e-119">Il valore della costante di ciascun membro `enum` deve essere compreso nell'intervallo del tipo sottostante di `enum`.</span><span class="sxs-lookup"><span data-stu-id="e098e-119">The constant value for each `enum` member must be in the range of the underlying type of the `enum`.</span></span> <span data-ttu-id="e098e-120">Quando una dichiarazione di membro `enum` non specifica in modo esplicito un valore, al membro viene assegnato il valore zero (se è il primo membro del tipo `enum`) o il valore del membro `enum` testualmente precedente più uno.</span><span class="sxs-lookup"><span data-stu-id="e098e-120">When an `enum` member declaration does not explicitly specify a value, the member is given the value zero (if it is the first member in the `enum` type) or the value of the textually preceding `enum` member plus one.</span></span>

<span data-ttu-id="e098e-121">I valori `Enum` possono essere convertiti in valori integrali e viceversa usando i cast di tipo.</span><span class="sxs-lookup"><span data-stu-id="e098e-121">`Enum` values can be converted to integral values and vice versa using type casts.</span></span> <span data-ttu-id="e098e-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e098e-122">For example:</span></span>

<span data-ttu-id="e098e-123">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]</span><span class="sxs-lookup"><span data-stu-id="e098e-123">[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]</span></span>

<span data-ttu-id="e098e-124">Il valore predefinito di qualsiasi tipo `enum` è il valore integrale zero convertito nel tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="e098e-124">The default value of any `enum` type is the integral value zero converted to the `enum` type.</span></span> <span data-ttu-id="e098e-125">Nei casi in cui le variabili vengono inizializzate automaticamente con un valore predefinito, tale valore viene assegnato alle variabili dei tipi `enum`.</span><span class="sxs-lookup"><span data-stu-id="e098e-125">In cases where variables are automatically initialized to a default value, this is the value given to variables of `enum` types.</span></span> <span data-ttu-id="e098e-126">Per rendere facilmente disponibile il valore predefinito di un tipo `enum`, il valore letterale `0` viene implicitamente convertito in qualsiasi tipo `enum`.</span><span class="sxs-lookup"><span data-stu-id="e098e-126">In order for the default value of an `enum` type to be easily available, the literal `0` implicitly converts to any `enum` type.</span></span> <span data-ttu-id="e098e-127">Di conseguenza, quanto riportato di seguito è consentito.</span><span class="sxs-lookup"><span data-stu-id="e098e-127">Thus, the following is permitted.</span></span>

<span data-ttu-id="e098e-128">[!code-csharp[Enum zero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]</span><span class="sxs-lookup"><span data-stu-id="e098e-128">[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e098e-129">[Precedente](interfaces.md)
[Successivo](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="e098e-129">[Previous](interfaces.md)
[Next](delegates.md)</span></span>

