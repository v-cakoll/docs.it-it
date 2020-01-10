---
title: Parola chiave contestuale value - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 84d0c51ddafb59144f4ba8c6e73412642fa8fa28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712897"
---
# <a name="value-c-reference"></a><span data-ttu-id="02c53-102">value (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="02c53-102">value (C# Reference)</span></span>

<span data-ttu-id="02c53-103">La parola chiave contestuale `value` viene utilizzata nella funzione di accesso `set` nelle dichiarazioni di [Proprietà](../../programming-guide/classes-and-structs/properties.md) e [indicizzatori](../../programming-guide/indexers/index.md) .</span><span class="sxs-lookup"><span data-stu-id="02c53-103">The contextual keyword `value` is used in the `set` accessor in [property](../../programming-guide/classes-and-structs/properties.md) and [indexer](../../programming-guide/indexers/index.md) declarations.</span></span> <span data-ttu-id="02c53-104">È simile a un parametro di input di un metodo.</span><span class="sxs-lookup"><span data-stu-id="02c53-104">It is similar to an input parameter of a method.</span></span> <span data-ttu-id="02c53-105">La parola `value` fa riferimento al valore che il codice client sta tentando di assegnare alla proprietà o all'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="02c53-105">The word `value` references the value that client code is attempting to assign to the property or indexer.</span></span> <span data-ttu-id="02c53-106">Nell'esempio seguente, `MyDerivedClass` ha una proprietà denominata `Name` che usa il parametro `value` per assegnare una nuova stringa al campo sottostante `name`.</span><span class="sxs-lookup"><span data-stu-id="02c53-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="02c53-107">Dal punto di vista del codice client, l'operazione viene scritta come assegnazione semplice.</span><span class="sxs-lookup"><span data-stu-id="02c53-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="02c53-108">Per altre informazioni, vedere gli articoli [Proprietà](../../programming-guide/classes-and-structs/properties.md) e [Indexeres](../../programming-guide/indexers/index.md) .</span><span class="sxs-lookup"><span data-stu-id="02c53-108">For more information, see the [Properties](../../programming-guide/classes-and-structs/properties.md) and [Indexeres](../../programming-guide/indexers/index.md) articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="02c53-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="02c53-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="02c53-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02c53-110">See also</span></span>

- [<span data-ttu-id="02c53-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="02c53-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="02c53-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="02c53-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="02c53-113">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="02c53-113">C# Keywords</span></span>](index.md)
