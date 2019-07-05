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
ms.openlocfilehash: 5b6668e20e4d69b7d6bdf3e6283574f1b974ef54
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423960"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="03a7e-103">Operatori di confronto (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="03a7e-103">Comparison operators (C# reference)</span></span>

<span data-ttu-id="03a7e-104">Gli operatori di confronto [`<` (minore di)](#less-than-operator-), [`>` (maggiore di)](#greater-than-operator-), [`<=` (minore o uguale a)](#less-than-or-equal-operator-) e [`>=` (maggiore o uguale a)](#greater-than-or-equal-operator-), noti anche come operatori relazionali, confrontano gli operandi.</span><span class="sxs-lookup"><span data-stu-id="03a7e-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="03a7e-105">Questi operatori supportano tutti i tipi numerici [integrali](../builtin-types/integral-numeric-types.md) e [a virgola mobile](../keywords/floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="03a7e-105">Those operators support all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../keywords/floating-point-types-table.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="03a7e-106">Per gli operatori `==`, `<`, `>`, `<=` e `>=`, se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="03a7e-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="03a7e-107">Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`.</span><span class="sxs-lookup"><span data-stu-id="03a7e-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="03a7e-108">Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="03a7e-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="03a7e-109">Anche i tipi di enumerazione supportano gli operatori di confronto.</span><span class="sxs-lookup"><span data-stu-id="03a7e-109">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="03a7e-110">Per gli operandi dello stesso tipo [enum](../keywords/enum.md), i valori corrispondenti del tipo integrale sottostante vengono confrontati.</span><span class="sxs-lookup"><span data-stu-id="03a7e-110">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="03a7e-111">Gli operatori [`==` e `!=`](equality-operators.md) controllano se i relativi operandi sono uguali oppure no.</span><span class="sxs-lookup"><span data-stu-id="03a7e-111">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="03a7e-112">Operatore "minore di" \<</span><span class="sxs-lookup"><span data-stu-id="03a7e-112">Less than operator \<</span></span>

<span data-ttu-id="03a7e-113">L'operatore `<` restituisce `true` se l'operando di sinistra è minore dell'operando di destra, `false` in caso contrario:</span><span class="sxs-lookup"><span data-stu-id="03a7e-113">The `<` operator returns `true` if its left-hand operand is less than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="03a7e-114">Operatore "maggiore di" ></span><span class="sxs-lookup"><span data-stu-id="03a7e-114">Greater than operator ></span></span>

<span data-ttu-id="03a7e-115">L'operatore `>` restituisce `true` se l'operando di sinistra è maggiore dell'operando di destra, `false` in caso contrario:</span><span class="sxs-lookup"><span data-stu-id="03a7e-115">The `>` operator returns `true` if its left-hand operand is greater than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="03a7e-116">Operatore "minore o uguale a" \<=</span><span class="sxs-lookup"><span data-stu-id="03a7e-116">Less than or equal operator \<=</span></span>

<span data-ttu-id="03a7e-117">L'operatore `<=` restituisce `true` se l'operando di sinistra è minore o uguale all'operatore di destra, `false` in caso contrario:</span><span class="sxs-lookup"><span data-stu-id="03a7e-117">The `<=` operator returns `true` if its left-hand operand is less than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="03a7e-118">Operatore "maggiore o uguale a" >=</span><span class="sxs-lookup"><span data-stu-id="03a7e-118">Greater than or equal operator >=</span></span>

<span data-ttu-id="03a7e-119">L'operatore `>=` restituisce `true` se l'operando di sinistra è maggiore o uguale all'operatore di destra, `false` in caso contrario:</span><span class="sxs-lookup"><span data-stu-id="03a7e-119">The `>=` operator returns `true` if its left-hand operand is greater than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="03a7e-120">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="03a7e-120">Operator overloadability</span></span>

<span data-ttu-id="03a7e-121">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) degli operatori `<`, `>`, `<=` e `>=`.</span><span class="sxs-lookup"><span data-stu-id="03a7e-121">A user-defined type can [overload](../keywords/operator.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="03a7e-122">Se un tipo esegue l'overload di uno degli operatori `<` o `>`, deve eseguire l'overload sia di `<` che di `>`.</span><span class="sxs-lookup"><span data-stu-id="03a7e-122">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="03a7e-123">Se un tipo esegue l'overload di uno degli operatori `<=` o `>=`, deve eseguire l'overload sia di `<=` che di `>=`.</span><span class="sxs-lookup"><span data-stu-id="03a7e-123">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="03a7e-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="03a7e-124">C# language specification</span></span>

<span data-ttu-id="03a7e-125">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="03a7e-125">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="03a7e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03a7e-126">See also</span></span>

- [<span data-ttu-id="03a7e-127">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="03a7e-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="03a7e-128">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="03a7e-128">C# operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="03a7e-129">Operatori di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="03a7e-129">Equality operators</span></span>](equality-operators.md)
