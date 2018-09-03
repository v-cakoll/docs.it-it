---
title: struct (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 7931da2e5f5c493b54eb1f33a1d6f57b38592f6e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399018"
---
# <a name="struct-c-reference"></a><span data-ttu-id="0e53b-102">struct (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0e53b-102">struct (C# Reference)</span></span>
<span data-ttu-id="0e53b-103">Un `struct` è un tipo di valore generalmente usato per incapsulare piccoli gruppi di variabili correlate, ad esempio le coordinate di un rettangolo o le caratteristiche di un articolo in un inventario.</span><span class="sxs-lookup"><span data-stu-id="0e53b-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="0e53b-104">Nell'esempio che segue è illustrata una semplice dichiarazione struct:</span><span class="sxs-lookup"><span data-stu-id="0e53b-104">The following example shows a simple struct declaration:</span></span>  
  
```csharp  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="0e53b-105">Note</span><span class="sxs-lookup"><span data-stu-id="0e53b-105">Remarks</span></span>  
 <span data-ttu-id="0e53b-106">Gli struct possono contenere anche [costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md), [costanti](../../../csharp/programming-guide/classes-and-structs/constants.md), [campi](../../../csharp/programming-guide/classes-and-structs/fields.md), [metodi](../../../csharp/programming-guide/classes-and-structs/methods.md), [proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md), [indicizzatori](../../../csharp/programming-guide/indexers/index.md), [operatori](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [eventi](../../../csharp/programming-guide/events/index.md) e [tipi annidati](../../../csharp/programming-guide/classes-and-structs/nested-types.md), anche se è consigliabile trasformare il tipo in una classe se sono necessari molti di questi membri.</span><span class="sxs-lookup"><span data-stu-id="0e53b-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="0e53b-107">Per i relativi esempi, vedere [Uso di struct](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="0e53b-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="0e53b-108">Gli struct possono implementare un'interfaccia, ma non possono ereditare da altri struct.</span><span class="sxs-lookup"><span data-stu-id="0e53b-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="0e53b-109">Per questo motivo i membri di struct non possono essere dichiarati come `protected`.</span><span class="sxs-lookup"><span data-stu-id="0e53b-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="0e53b-110">Per altre informazioni, vedere [Struct](../../../csharp/programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="0e53b-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0e53b-111">Esempi</span><span class="sxs-lookup"><span data-stu-id="0e53b-111">Examples</span></span>  
 <span data-ttu-id="0e53b-112">Per altre informazioni ed esempi, vedere [Uso di struct](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="0e53b-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0e53b-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0e53b-113">C# Language Specification</span></span>  
 <span data-ttu-id="0e53b-114">Per i relativi esempi, vedere [Uso di struct](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="0e53b-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e53b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e53b-115">See Also</span></span>

- [<span data-ttu-id="0e53b-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0e53b-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="0e53b-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0e53b-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0e53b-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="0e53b-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="0e53b-119">Tabella dei valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="0e53b-119">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
- [<span data-ttu-id="0e53b-120">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="0e53b-120">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="0e53b-121">Tipi</span><span class="sxs-lookup"><span data-stu-id="0e53b-121">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="0e53b-122">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="0e53b-122">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
- [<span data-ttu-id="0e53b-123">class</span><span class="sxs-lookup"><span data-stu-id="0e53b-123">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
- [<span data-ttu-id="0e53b-124">interface</span><span class="sxs-lookup"><span data-stu-id="0e53b-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
- [<span data-ttu-id="0e53b-125">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="0e53b-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
