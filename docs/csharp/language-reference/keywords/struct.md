---
title: struct - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 77d5c83dd4c81b96bc62ace6e609db8bc411dc41
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093162"
---
# <a name="struct-c-reference"></a><span data-ttu-id="2194a-102">struct (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2194a-102">struct (C# Reference)</span></span>

<span data-ttu-id="2194a-103">Un `struct` è un tipo di valore generalmente usato per incapsulare piccoli gruppi di variabili correlate, ad esempio le coordinate di un rettangolo o le caratteristiche di un articolo in un inventario.</span><span class="sxs-lookup"><span data-stu-id="2194a-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="2194a-104">Nell'esempio che segue è illustrata una semplice dichiarazione struct:</span><span class="sxs-lookup"><span data-stu-id="2194a-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="2194a-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2194a-105">Remarks</span></span>

<span data-ttu-id="2194a-106">Gli struct possono contenere anche [costruttori](../../programming-guide/classes-and-structs/constructors.md), [costanti](../../programming-guide/classes-and-structs/constants.md), [campi](../../programming-guide/classes-and-structs/fields.md), [metodi](../../programming-guide/classes-and-structs/methods.md), [proprietà](../../programming-guide/classes-and-structs/properties.md), [indicizzatori](../../programming-guide/indexers/index.md), [operatori](../operators/index.md), [eventi](../../programming-guide/events/index.md) e [tipi annidati](../../programming-guide/classes-and-structs/nested-types.md), anche se è consigliabile trasformare il tipo in una classe se sono necessari molti di questi membri.</span><span class="sxs-lookup"><span data-stu-id="2194a-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../operators/index.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="2194a-107">Per i relativi esempi, vedere [Uso di struct](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="2194a-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="2194a-108">Gli struct possono implementare un'interfaccia, ma non possono ereditare da altri struct.</span><span class="sxs-lookup"><span data-stu-id="2194a-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="2194a-109">Per questo motivo i membri di struct non possono essere dichiarati come `protected`.</span><span class="sxs-lookup"><span data-stu-id="2194a-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="2194a-110">Per altre informazioni, vedere [Struct](../../programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="2194a-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="2194a-111">Esempi</span><span class="sxs-lookup"><span data-stu-id="2194a-111">Examples</span></span>

<span data-ttu-id="2194a-112">Per altre informazioni ed esempi, vedere [Uso di struct](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="2194a-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2194a-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2194a-113">C# language specification</span></span>

<span data-ttu-id="2194a-114">Per i relativi esempi, vedere [Uso di struct](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="2194a-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2194a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2194a-115">See also</span></span>

- [<span data-ttu-id="2194a-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="2194a-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="2194a-117">Parole chiave C#</span><span class="sxs-lookup"><span data-stu-id="2194a-117">C# keywords</span></span>](index.md)
- [<span data-ttu-id="2194a-118">Tipi di valore</span><span class="sxs-lookup"><span data-stu-id="2194a-118">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="2194a-119">class</span><span class="sxs-lookup"><span data-stu-id="2194a-119">class</span></span>](class.md)
- [<span data-ttu-id="2194a-120">interface</span><span class="sxs-lookup"><span data-stu-id="2194a-120">interface</span></span>](interface.md)
- [<span data-ttu-id="2194a-121">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="2194a-121">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
