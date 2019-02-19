---
title: Operatore << - Riferimenti per C#
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: deea2d0f720ba7f096e65c67378586bc88f24673
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219437"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3a05f-102">Operatore \<\< (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3a05f-102">\<\< operator (C# Reference)</span></span>

<span data-ttu-id="3a05f-103">L'operatore di scorrimento a sinistra (`<<`) scorre verso sinistra il primo operando del numero di bit definito dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="3a05f-103">The left-shift operator `<<` shifts its first operand left by the number of bits defined by its second operand.</span></span> <span data-ttu-id="3a05f-104">Tutti i tipi integer supportano l'operatore `<<`.</span><span class="sxs-lookup"><span data-stu-id="3a05f-104">All integer types support the `<<` operator.</span></span> <span data-ttu-id="3a05f-105">Il tipo del secondo operando deve essere tuttavia [int](../keywords/int.md) o un tipo con una [conversione numerica implicita predefinita](../keywords/implicit-numeric-conversions-table.md) in `int`.</span><span class="sxs-lookup"><span data-stu-id="3a05f-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="3a05f-106">I bit più significativi che non rientrano nell'intervallo del tipo di risultato vengono rimossi e le posizioni dei bit vuoti meno significativi vengono impostate su zero, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3a05f-106">The high-order bits that are outside the range of the result type are discarded, and the low-order empty bit positions are set to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShift)]

## <a name="shift-count"></a><span data-ttu-id="3a05f-107">Conteggio degli scorrimenti</span><span class="sxs-lookup"><span data-stu-id="3a05f-107">Shift count</span></span>

<span data-ttu-id="3a05f-108">Per l'espressione `x << count`, il conteggio degli scorrimenti effettivo dipende dal tipo di `x` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3a05f-108">For the expression `x << count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="3a05f-109">Se il tipo di `x` è [int](../keywords/int.md) o [uint](../keywords/uint.md), il conteggio degli scorrimenti è dato dai *cinque* bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="3a05f-109">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="3a05f-110">Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x1F` (o `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="3a05f-110">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="3a05f-111">Se il tipo di `x` è [long](../keywords/long.md) o [ulong](../keywords/ulong.md), il conteggio degli scorrimenti è dato dai *sei* bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="3a05f-111">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="3a05f-112">Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x3F` (o `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="3a05f-112">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="3a05f-113">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="3a05f-113">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="3a05f-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3a05f-114">Remarks</span></span>

<span data-ttu-id="3a05f-115">Le operazioni di scorrimento non causano mai overflow e producono gli stessi risultati nei contesti [checked e unchecked](../keywords/checked-and-unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="3a05f-115">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="3a05f-116">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="3a05f-116">Operator overloadability</span></span>

<span data-ttu-id="3a05f-117">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `<<`.</span><span class="sxs-lookup"><span data-stu-id="3a05f-117">User-defined types can [overload](../keywords/operator.md) the `<<` operator.</span></span> <span data-ttu-id="3a05f-118">Se un tipo definito dall'utente `T` esegue l'overload dell'operatore `<<`, il tipo del primo operando deve essere `T` e il tipo del secondo operando deve essere `int`.</span><span class="sxs-lookup"><span data-stu-id="3a05f-118">If a user-defined type `T` overloads the `<<` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="3a05f-119">Quando viene eseguito l'overload dell'operatore `<<`, viene eseguito in modo implicito anche l'overload dell'[operatore di assegnazione di scorrimento a sinistra](left-shift-assignment-operator.md) `<<=`.</span><span class="sxs-lookup"><span data-stu-id="3a05f-119">When the `<<` operator is overloaded, the [left-shift assignment operator](left-shift-assignment-operator.md) `<<=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3a05f-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3a05f-120">C# language specification</span></span>

<span data-ttu-id="3a05f-121">Per altre informazioni, vedere la sezione [Operatori di scorrimento](~/_csharplang/spec/expressions.md#shift-operators) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a05f-121">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a05f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a05f-122">See also</span></span>

- [<span data-ttu-id="3a05f-123">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3a05f-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3a05f-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3a05f-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3a05f-125">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="3a05f-125">C# Operators</span></span>](index.md)
- [<span data-ttu-id="3a05f-126">Operatore >></span><span class="sxs-lookup"><span data-stu-id="3a05f-126">>> operator</span></span>](right-shift-operator.md)
