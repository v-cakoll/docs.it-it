---
title: Operatori di uguaglianza - Riferimenti per C#
description: Informazioni sugli operatori di confronto uguaglianze C#.
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: b4d3f3c0c6195fef22a33c47ad0b8c498f512f6a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753492"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="f6f4d-103">Operatori di uguaglianza (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f6f4d-103">Equality operators (C# Reference)</span></span>

<span data-ttu-id="f6f4d-104">Gli operatori [`==` (uguaglianza)](#equality-operator-) e [`!=` (disuguaglianza)](#inequality-operator-) controllano se i relativi operandi sono uguali oppure no.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-104">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="f6f4d-105">Operatore di uguaglianza ==</span><span class="sxs-lookup"><span data-stu-id="f6f4d-105">Equality operator ==</span></span>

<span data-ttu-id="f6f4d-106">L'operatore di uguaglianza `==` restituisce `true` se gli operandi sono uguali, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-106">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="f6f4d-107">Uguaglianza dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="f6f4d-107">Value types equality</span></span>

<span data-ttu-id="f6f4d-108">Gli operandi dei [tipi valore predefiniti](../keywords/value-types-table.md) sono uguali se i relativi valori sono uguali:</span><span class="sxs-lookup"><span data-stu-id="f6f4d-108">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="f6f4d-109">Per gli operatori `==`, [`<`, `>`, `<=` e `>=`](comparison-operators.md) se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-109">For the `==`, [`<`, `>`, `<=`, and `>=`](comparison-operators.md) operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="f6f4d-110">Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-110">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="f6f4d-111">Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-111">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="f6f4d-112">Due operandi dello stesso tipo [enum](../keywords/enum.md) sono uguali se i valori corrispondenti del tipo integrale sottostante sono uguali.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-112">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="f6f4d-113">I tipi [struct](../keywords/struct.md) definiti dall'utente non supportano l'operatore `==` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-113">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="f6f4d-114">Per supportare l'operatore `==`, un tipo struct definito dall'utente deve eseguirne l'[overload](#operator-overloadability).</span><span class="sxs-lookup"><span data-stu-id="f6f4d-114">To support the `==` operator, a user-defined struct must [overload](#operator-overloadability) it.</span></span>

<span data-ttu-id="f6f4d-115">A partire da C# 7.3, gli operatori `==` e `!=` sono supportati dalle [tuple](../../tuples.md) C#.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-115">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="f6f4d-116">Per altre informazioni, vedere la sezione [Uguaglianza e tuple](../../tuples.md#equality-and-tuples) nell'articolo [Tipi tupla in C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="f6f4d-116">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="string-equality"></a><span data-ttu-id="f6f4d-117">Uguaglianza di stringhe</span><span class="sxs-lookup"><span data-stu-id="f6f4d-117">String equality</span></span>

<span data-ttu-id="f6f4d-118">Due operandi [stringa](../keywords/string.md) sono uguali quando entrambi sono `null` o entrambe le istanze di stringa sono della stessa lunghezza e contengono caratteri identici in ogni posizione di carattere:</span><span class="sxs-lookup"><span data-stu-id="f6f4d-118">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="f6f4d-119">Questo è un confronto ordinale senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-119">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="f6f4d-120">Per altre informazioni sul confronto di stringhe, vedere [Come confrontare stringhe in C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="f6f4d-120">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="f6f4d-121">Uguaglianza dei tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="f6f4d-121">Reference types equality</span></span>

<span data-ttu-id="f6f4d-122">Due operandi di tipo riferimento diversi da `string` sono uguali quando fanno riferimento allo stesso oggetto:</span><span class="sxs-lookup"><span data-stu-id="f6f4d-122">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="f6f4d-123">Come illustrato nell'esempio, i tipi riferimento definiti dall'utente supportano l'operatore `==` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-123">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="f6f4d-124">Tuttavia, un tipo riferimento definito dall'utente può eseguire l'overload dell'operatore `==`.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-124">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="f6f4d-125">Se un tipo riferimento esegue l'overload dell'operatore `==`, usare il metodo <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> per verificare se due riferimenti di quel tipo fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-125">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="inequality-operator-"></a><span data-ttu-id="f6f4d-126">Operatore di disuguaglianza !=</span><span class="sxs-lookup"><span data-stu-id="f6f4d-126">Inequality operator !=</span></span>

<span data-ttu-id="f6f4d-127">L'operatore di disuguaglianza `!=` restituisce `true` se gli operandi sono diversi, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-127">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="f6f4d-128">Per gli operandi dei [tipi predefiniti](../keywords/built-in-types-table.md), l'espressione `x != y` produce lo stesso risultato dell'espressione `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-128">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="f6f4d-129">Per altre informazioni sull'uguaglianza dei tipi, vedere la sezione [Operatore di uguaglianza](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="f6f4d-129">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="f6f4d-130">Nell'esempio seguente viene illustrato l'uso dell'operatore `!=`:</span><span class="sxs-lookup"><span data-stu-id="f6f4d-130">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="f6f4d-131">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="f6f4d-131">Operator overloadability</span></span>

<span data-ttu-id="f6f4d-132">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) degli operatori `==` e `!=`.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-132">A user-defined type can [overload](../keywords/operator.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="f6f4d-133">Se un tipo esegue l'overload di uno dei due operatori, deve eseguire l'overload anche di un altro operatore.</span><span class="sxs-lookup"><span data-stu-id="f6f4d-133">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f6f4d-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f6f4d-134">C# language specification</span></span>

<span data-ttu-id="f6f4d-135">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f6f4d-135">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6f4d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6f4d-136">See also</span></span>

- [<span data-ttu-id="f6f4d-137">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f6f4d-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f6f4d-138">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f6f4d-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f6f4d-139">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="f6f4d-139">C# Operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f6f4d-140">Confronti di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="f6f4d-140">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [<span data-ttu-id="f6f4d-141">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="f6f4d-141">Comparison operators</span></span>](comparison-operators.md)
