---
title: '>> Operatore - - Riferimenti per C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 809cd2cab29d3378892ea224cf846e9d0909b073
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219724"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="79bb3-102">Operatore >> (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="79bb3-102">>> operator (C# Reference)</span></span>

<span data-ttu-id="79bb3-103">L'operatore di scorrimento a destra `>>` scorre verso destra il primo operando del numero di bit definito dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="79bb3-103">The right-shift operator `>>` shifts its first operand right by the number of bits defined by its second operand.</span></span> <span data-ttu-id="79bb3-104">Tutti i tipi integer supportano l'operatore `>>`.</span><span class="sxs-lookup"><span data-stu-id="79bb3-104">All integer types support the `>>` operator.</span></span> <span data-ttu-id="79bb3-105">Il tipo del secondo operando deve essere tuttavia [int](../keywords/int.md) o un tipo con una [conversione numerica implicita predefinita](../keywords/implicit-numeric-conversions-table.md) in `int`.</span><span class="sxs-lookup"><span data-stu-id="79bb3-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="79bb3-106">L'operazione di scorrimento a destra rimuove i bit meno significativi.</span><span class="sxs-lookup"><span data-stu-id="79bb3-106">The right-shift operation discards the low-order bits.</span></span> <span data-ttu-id="79bb3-107">Le posizioni dei bit vuoti più significativi vengono impostate in base al tipo del primo operando come segue:</span><span class="sxs-lookup"><span data-stu-id="79bb3-107">The high-order empty bit positions are set based on the type of the first operand as follows:</span></span>

- <span data-ttu-id="79bb3-108">Se il primo operando è di tipo [int](../keywords/int.md) oppure [long](../keywords/long.md), l'operatore di scorrimento a destra esegue uno scorrimento **aritmetico**: il valore del bit più significativo (il bit di segno) del primo operando viene propagato alle posizioni dei bit vuoti più significativi.</span><span class="sxs-lookup"><span data-stu-id="79bb3-108">If the first operand is of type [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift operator performs an **arithmetic** shift: the value of the most significant bit (the sign bit) of the first operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="79bb3-109">Vale a dire, le posizioni dei bit vuoti più significativi vengono impostate su zero se il primo operando è un valore non negativo e impostate su uno se è negativo.</span><span class="sxs-lookup"><span data-stu-id="79bb3-109">That is, the high-order empty bit positions are set to zero if the first operand is non-negative and set to one if it's negative.</span></span>

- <span data-ttu-id="79bb3-110">Se il primo operando è di tipo [uint](../keywords/uint.md) oppure [ulong](../keywords/ulong.md), l'operatore di scorrimento a destra esegue uno scorrimento **logico**: le posizioni dei bit vuoti più significativi vengono sempre impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="79bb3-110">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift operator performs a **logical** shift: the high-order empty bit positions are always set to zero.</span></span>

<span data-ttu-id="79bb3-111">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="79bb3-111">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[right shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShift)]

## <a name="shift-count"></a><span data-ttu-id="79bb3-112">Conteggio degli scorrimenti</span><span class="sxs-lookup"><span data-stu-id="79bb3-112">Shift count</span></span>

<span data-ttu-id="79bb3-113">Per l'espressione `x >> count`, il conteggio degli scorrimenti effettivo dipende dal tipo di `x` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="79bb3-113">For the expression `x >> count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="79bb3-114">Se il tipo di `x` è [int](../keywords/int.md) o [uint](../keywords/uint.md), il conteggio degli scorrimenti è dato dai *cinque* bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="79bb3-114">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="79bb3-115">Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x1F` (o `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="79bb3-115">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="79bb3-116">Se il tipo di `x` è [long](../keywords/long.md) o [ulong](../keywords/ulong.md), il conteggio degli scorrimenti è dato dai *sei* bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="79bb3-116">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="79bb3-117">Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x3F` (o `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="79bb3-117">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="79bb3-118">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="79bb3-118">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="79bb3-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="79bb3-119">Remarks</span></span>

<span data-ttu-id="79bb3-120">Le operazioni di scorrimento non causano mai overflow e producono gli stessi risultati nei contesti [checked e unchecked](../keywords/checked-and-unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="79bb3-120">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="79bb3-121">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="79bb3-121">Operator overloadability</span></span>

<span data-ttu-id="79bb3-122">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `>>`.</span><span class="sxs-lookup"><span data-stu-id="79bb3-122">User-defined types can [overload](../keywords/operator.md) the `>>` operator.</span></span> <span data-ttu-id="79bb3-123">Se un tipo definito dall'utente `T` esegue l'overload dell'operatore `>>`, il tipo del primo operando deve essere `T` e il tipo del secondo operando deve essere `int`.</span><span class="sxs-lookup"><span data-stu-id="79bb3-123">If a user-defined type `T` overloads the `>>` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="79bb3-124">Quando viene eseguito l'overload dell'operatore `>>`, viene eseguito in modo implicito anche l'overload dell'[operatore di assegnazione di scorrimento a destra](right-shift-assignment-operator.md) `>>=`.</span><span class="sxs-lookup"><span data-stu-id="79bb3-124">When the `>>` operator is overloaded, the [right-shift assignment operator](right-shift-assignment-operator.md) `>>=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="79bb3-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="79bb3-125">C# language specification</span></span>

<span data-ttu-id="79bb3-126">Per altre informazioni, vedere la sezione [Operatori di scorrimento](~/_csharplang/spec/expressions.md#shift-operators) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="79bb3-126">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79bb3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79bb3-127">See also</span></span>

- [<span data-ttu-id="79bb3-128">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="79bb3-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="79bb3-129">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="79bb3-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="79bb3-130">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="79bb3-130">C# operators</span></span>](index.md)
- [<span data-ttu-id="79bb3-131">Operatore <<</span><span class="sxs-lookup"><span data-stu-id="79bb3-131"><< operator</span></span>](left-shift-operator.md)