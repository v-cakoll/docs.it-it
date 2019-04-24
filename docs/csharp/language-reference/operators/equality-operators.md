---
title: Operatori di uguaglianza - Riferimenti per C#
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 297285ccb9aba7eae1d70a7d28a62241646a023c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334159"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="1d8b1-102">Operatori di uguaglianza (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1d8b1-102">Equality operators (C# Reference)</span></span>

<span data-ttu-id="1d8b1-103">Gli operatori [`==` (uguaglianza)](#equality-operator-) e [`!=` (disuguaglianza)](#inequality-operator-) controllano se i relativi operandi sono uguali oppure no.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-103">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="1d8b1-104">Operatore di uguaglianza ==</span><span class="sxs-lookup"><span data-stu-id="1d8b1-104">Equality operator ==</span></span>

<span data-ttu-id="1d8b1-105">L'operatore di uguaglianza `==` restituisce `true` se gli operandi sono uguali, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-105">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="1d8b1-106">Uguaglianza dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="1d8b1-106">Value types equality</span></span>

<span data-ttu-id="1d8b1-107">Gli operandi dei [tipi valore predefiniti](../keywords/value-types-table.md) sono uguali se i relativi valori sono uguali:</span><span class="sxs-lookup"><span data-stu-id="1d8b1-107">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="1d8b1-108">Per gli operatori di uguaglianza e relazionali `==`, `>`, `<`, `>=` e `<=`, se uno qualsiasi degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), il risultato dell'operazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-108">For equality and relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="1d8b1-109">Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-109">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="1d8b1-110">Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-110">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="1d8b1-111">Due operandi dello stesso tipo [enum](../keywords/enum.md) sono uguali se i valori corrispondenti del tipo integrale sottostante sono uguali.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-111">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="1d8b1-112">I tipi [struct](../keywords/struct.md) definiti dall'utente non supportano l'operatore `==` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-112">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="1d8b1-113">Per supportare l'operatore `==`, un tipo struct definito dall'utente deve eseguirne l'[overload](#operator-overloadability).</span><span class="sxs-lookup"><span data-stu-id="1d8b1-113">To support the `==` operator, a user-defined struct must [overload](#operator-overloadability) it.</span></span>

<span data-ttu-id="1d8b1-114">A partire da C# 7.3, gli operatori `==` e `!=` sono supportati dalle [tuple](../../tuples.md) C#.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-114">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="1d8b1-115">Per altre informazioni, vedere la sezione [Uguaglianza e tuple](../../tuples.md#equality-and-tuples) nell'articolo [Tipi tupla in C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="1d8b1-115">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="string-equality"></a><span data-ttu-id="1d8b1-116">Uguaglianza di stringhe</span><span class="sxs-lookup"><span data-stu-id="1d8b1-116">String equality</span></span>

<span data-ttu-id="1d8b1-117">Due operandi [stringa](../keywords/string.md) sono uguali quando entrambi sono `null` o entrambe le istanze di stringa sono della stessa lunghezza e contengono caratteri identici in ogni posizione di carattere:</span><span class="sxs-lookup"><span data-stu-id="1d8b1-117">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="1d8b1-118">Questo è un confronto ordinale senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-118">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="1d8b1-119">Per altre informazioni sul confronto di stringhe, vedere [Come confrontare stringhe in C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="1d8b1-119">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="1d8b1-120">Uguaglianza dei tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="1d8b1-120">Reference types equality</span></span>

<span data-ttu-id="1d8b1-121">Due operandi di tipo riferimento diversi da `string` sono uguali quando fanno riferimento allo stesso oggetto:</span><span class="sxs-lookup"><span data-stu-id="1d8b1-121">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="1d8b1-122">Come illustrato nell'esempio, i tipi riferimento definiti dall'utente supportano l'operatore `==` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-122">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="1d8b1-123">Tuttavia, un tipo riferimento definito dall'utente può eseguire l'overload dell'operatore `==`.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-123">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="1d8b1-124">Se un tipo riferimento esegue l'overload dell'operatore `==`, usare il metodo <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> per verificare se due riferimenti di quel tipo fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-124">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="inequality-operator-"></a><span data-ttu-id="1d8b1-125">Operatore di disuguaglianza !=</span><span class="sxs-lookup"><span data-stu-id="1d8b1-125">Inequality operator !=</span></span>

<span data-ttu-id="1d8b1-126">L'operatore di disuguaglianza `!=` restituisce `true` se gli operandi sono diversi, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-126">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="1d8b1-127">Per gli operandi dei [tipi predefiniti](../keywords/built-in-types-table.md), l'espressione `x != y` produce lo stesso risultato dell'espressione `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-127">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="1d8b1-128">Per altre informazioni sull'uguaglianza dei tipi, vedere la sezione [Operatore di uguaglianza](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="1d8b1-128">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="1d8b1-129">Nell'esempio seguente viene illustrato l'uso dell'operatore `!=`:</span><span class="sxs-lookup"><span data-stu-id="1d8b1-129">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="1d8b1-130">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="1d8b1-130">Operator overloadability</span></span>

<span data-ttu-id="1d8b1-131">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) degli operatori `==` e `!=`.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-131">A user-defined type can [overload](../keywords/operator.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="1d8b1-132">Se un tipo esegue l'overload di uno dei due operatori, deve eseguire l'overload anche di un altro operatore.</span><span class="sxs-lookup"><span data-stu-id="1d8b1-132">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1d8b1-133">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1d8b1-133">C# language specification</span></span>

<span data-ttu-id="1d8b1-134">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="1d8b1-134">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d8b1-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d8b1-135">See also</span></span>

- [<span data-ttu-id="1d8b1-136">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1d8b1-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1d8b1-137">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1d8b1-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1d8b1-138">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="1d8b1-138">C# Operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1d8b1-139">Confronti di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="1d8b1-139">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
