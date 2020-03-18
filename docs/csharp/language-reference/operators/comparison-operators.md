---
title: Operatori di confronto - Riferimenti per C#
description: Informazioni sugli operatori di confronto C# che è possibile usare per controllare l'ordine dei valori numerici.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: 68502205193a1fc8ab7410053e13274560ffffb0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399245"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="bf34d-103">Operatori di confronto (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="bf34d-103">Comparison operators (C# reference)</span></span>

<span data-ttu-id="bf34d-104">Gli [ `<` operatori (minore di)](#less-than-operator-), [ `>` (maggiore di)](#greater-than-operator-), [ `<=` (minore o uguale a)](#less-than-or-equal-operator-)e [ `>=` (maggiore o uguale a)](#greater-than-or-equal-operator-) confronto, noti anche come operatori relazionali, confrontano i relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="bf34d-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="bf34d-105">Tali operatori sono supportati da tutti i tipi [numerici integrali](../builtin-types/integral-numeric-types.md) e [a virgola mobile.](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="bf34d-105">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="bf34d-106">Per gli operatori `==`, `<`, `>`, `<=` e `>=`, se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="bf34d-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="bf34d-107">Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`.</span><span class="sxs-lookup"><span data-stu-id="bf34d-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="bf34d-108">Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf34d-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="bf34d-109">Anche i tipi di enumerazione supportano gli operatori di confronto.</span><span class="sxs-lookup"><span data-stu-id="bf34d-109">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="bf34d-110">Per gli operandi dello stesso tipo [enum](../builtin-types/enum.md), i valori corrispondenti del tipo integrale sottostante vengono confrontati.</span><span class="sxs-lookup"><span data-stu-id="bf34d-110">For operands of the same [enum](../builtin-types/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="bf34d-111">Gli [ `==` `!=` operatori e](equality-operators.md) controllano se i relativi operandi sono uguali o meno.</span><span class="sxs-lookup"><span data-stu-id="bf34d-111">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="bf34d-112">Operatore "minore di" \<</span><span class="sxs-lookup"><span data-stu-id="bf34d-112">Less than operator \<</span></span>

<span data-ttu-id="bf34d-113">L'operatore `<` restituisce `true` se l'operando di sinistra è minore dell'operando di destra, `false` in caso contrario:</span><span class="sxs-lookup"><span data-stu-id="bf34d-113">The `<` operator returns `true` if its left-hand operand is less than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](snippets/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="bf34d-114">Operatore "maggiore di" ></span><span class="sxs-lookup"><span data-stu-id="bf34d-114">Greater than operator ></span></span>

<span data-ttu-id="bf34d-115">L'operatore `>` restituisce `true` se l'operando di sinistra è maggiore dell'operando di destra, `false` in caso contrario:</span><span class="sxs-lookup"><span data-stu-id="bf34d-115">The `>` operator returns `true` if its left-hand operand is greater than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](snippets/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="bf34d-116">Operatore "minore o uguale a" \<=</span><span class="sxs-lookup"><span data-stu-id="bf34d-116">Less than or equal operator \<=</span></span>

<span data-ttu-id="bf34d-117">L'operatore `<=` restituisce `true` se l'operando di sinistra è minore o uguale all'operatore di destra, `false` in caso contrario:</span><span class="sxs-lookup"><span data-stu-id="bf34d-117">The `<=` operator returns `true` if its left-hand operand is less than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](snippets/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="bf34d-118">Operatore "maggiore o uguale a" >=</span><span class="sxs-lookup"><span data-stu-id="bf34d-118">Greater than or equal operator >=</span></span>

<span data-ttu-id="bf34d-119">L'operatore `>=` restituisce `true` se l'operando di sinistra è maggiore o uguale all'operatore di destra, `false` in caso contrario:</span><span class="sxs-lookup"><span data-stu-id="bf34d-119">The `>=` operator returns `true` if its left-hand operand is greater than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](snippets/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="bf34d-120">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="bf34d-120">Operator overloadability</span></span>

<span data-ttu-id="bf34d-121">Un tipo definito dall'utente `>` `<=`può `>=` [eseguire l'overload](operator-overloading.md) degli `<`operatori , , e .</span><span class="sxs-lookup"><span data-stu-id="bf34d-121">A user-defined type can [overload](operator-overloading.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="bf34d-122">Se un tipo esegue l'overload di uno degli operatori `<` o `>`, deve eseguire l'overload sia di `<` che di `>`.</span><span class="sxs-lookup"><span data-stu-id="bf34d-122">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="bf34d-123">Se un tipo esegue l'overload di uno degli operatori `<=` o `>=`, deve eseguire l'overload sia di `<=` che di `>=`.</span><span class="sxs-lookup"><span data-stu-id="bf34d-123">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bf34d-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bf34d-124">C# language specification</span></span>

<span data-ttu-id="bf34d-125">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="bf34d-125">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf34d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf34d-126">See also</span></span>

- [<span data-ttu-id="bf34d-127">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="bf34d-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bf34d-128">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="bf34d-128">C# operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="bf34d-129">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="bf34d-129">Equality operators</span></span>](equality-operators.md)
