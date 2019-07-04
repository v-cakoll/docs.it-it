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
ms.openlocfilehash: f60d62d1823a8bd06b0417638719a81e95d7438b
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267694"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="3ca6e-103">Operatori di uguaglianza (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3ca6e-103">Equality operators (C# reference)</span></span>

<span data-ttu-id="3ca6e-104">Gli operatori [`==` (uguaglianza)](#equality-operator-) e [`!=` (disuguaglianza)](#inequality-operator-) controllano se i relativi operandi sono uguali oppure no.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-104">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="3ca6e-105">Operatore di uguaglianza ==</span><span class="sxs-lookup"><span data-stu-id="3ca6e-105">Equality operator ==</span></span>

<span data-ttu-id="3ca6e-106">L'operatore di uguaglianza `==` restituisce `true` se gli operandi sono uguali, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-106">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="3ca6e-107">Uguaglianza dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="3ca6e-107">Value types equality</span></span>

<span data-ttu-id="3ca6e-108">Gli operandi dei [tipi valore predefiniti](../keywords/value-types-table.md) sono uguali se i relativi valori sono uguali:</span><span class="sxs-lookup"><span data-stu-id="3ca6e-108">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="3ca6e-109">Per gli operatori `==`, [`<`, `>`, `<=` e `>=`](comparison-operators.md) se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-109">For the `==`, [`<`, `>`, `<=`, and `>=`](comparison-operators.md) operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="3ca6e-110">Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-110">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="3ca6e-111">Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-111">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="3ca6e-112">Due operandi dello stesso tipo [enum](../keywords/enum.md) sono uguali se i valori corrispondenti del tipo integrale sottostante sono uguali.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-112">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="3ca6e-113">I tipi [struct](../keywords/struct.md) definiti dall'utente non supportano l'operatore `==` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-113">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="3ca6e-114">Per supportare l'operatore `==`, un tipo struct definito dall'utente deve eseguirne l'[overload](#operator-overloadability).</span><span class="sxs-lookup"><span data-stu-id="3ca6e-114">To support the `==` operator, a user-defined struct must [overload](#operator-overloadability) it.</span></span>

<span data-ttu-id="3ca6e-115">A partire da C# 7.3, gli operatori `==` e `!=` sono supportati dalle [tuple](../../tuples.md) C#.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-115">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="3ca6e-116">Per altre informazioni, vedere la sezione [Uguaglianza e tuple](../../tuples.md#equality-and-tuples) nell'articolo [Tipi tupla in C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6e-116">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="string-equality"></a><span data-ttu-id="3ca6e-117">Uguaglianza di stringhe</span><span class="sxs-lookup"><span data-stu-id="3ca6e-117">String equality</span></span>

<span data-ttu-id="3ca6e-118">Due operandi [stringa](../keywords/string.md) sono uguali quando entrambi sono `null` o entrambe le istanze di stringa sono della stessa lunghezza e contengono caratteri identici in ogni posizione di carattere:</span><span class="sxs-lookup"><span data-stu-id="3ca6e-118">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#StringEquality)]

<span data-ttu-id="3ca6e-119">Questo è un confronto ordinale senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-119">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="3ca6e-120">Per altre informazioni sul confronto di stringhe, vedere [Come confrontare stringhe in C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6e-120">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="3ca6e-121">Uguaglianza dei tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="3ca6e-121">Reference types equality</span></span>

<span data-ttu-id="3ca6e-122">Due operandi di tipo riferimento diversi da `string` sono uguali quando fanno riferimento allo stesso oggetto:</span><span class="sxs-lookup"><span data-stu-id="3ca6e-122">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp[reference type equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ReferenceTypesEquality)]

<span data-ttu-id="3ca6e-123">Come illustrato nell'esempio, i tipi riferimento definiti dall'utente supportano l'operatore `==` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-123">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="3ca6e-124">Tuttavia, un tipo riferimento definito dall'utente può eseguire l'overload dell'operatore `==`.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-124">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="3ca6e-125">Se un tipo riferimento esegue l'overload dell'operatore `==`, usare il metodo <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> per verificare se due riferimenti di quel tipo fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-125">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="inequality-operator-"></a><span data-ttu-id="3ca6e-126">Operatore di disuguaglianza !=</span><span class="sxs-lookup"><span data-stu-id="3ca6e-126">Inequality operator !=</span></span>

<span data-ttu-id="3ca6e-127">L'operatore di disuguaglianza `!=` restituisce `true` se gli operandi sono diversi, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-127">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="3ca6e-128">Per gli operandi dei [tipi predefiniti](../keywords/built-in-types-table.md), l'espressione `x != y` produce lo stesso risultato dell'espressione `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-128">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="3ca6e-129">Per altre informazioni sull'uguaglianza dei tipi, vedere la sezione [Operatore di uguaglianza](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="3ca6e-129">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="3ca6e-130">Nell'esempio seguente viene illustrato l'uso dell'operatore `!=`:</span><span class="sxs-lookup"><span data-stu-id="3ca6e-130">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/csharp/language-reference/operators/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="3ca6e-131">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="3ca6e-131">Operator overloadability</span></span>

<span data-ttu-id="3ca6e-132">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) degli operatori `==` e `!=`.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-132">A user-defined type can [overload](../keywords/operator.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="3ca6e-133">Se un tipo esegue l'overload di uno dei due operatori, deve eseguire l'overload anche di un altro operatore.</span><span class="sxs-lookup"><span data-stu-id="3ca6e-133">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3ca6e-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3ca6e-134">C# language specification</span></span>

<span data-ttu-id="3ca6e-135">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="3ca6e-135">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ca6e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ca6e-136">See also</span></span>

- [<span data-ttu-id="3ca6e-137">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3ca6e-137">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3ca6e-138">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="3ca6e-138">C# operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3ca6e-139">Confronti di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="3ca6e-139">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [<span data-ttu-id="3ca6e-140">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="3ca6e-140">Comparison operators</span></span>](comparison-operators.md)
