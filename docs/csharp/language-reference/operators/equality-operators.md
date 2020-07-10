---
title: Operatori di uguaglianza - Riferimenti per C#
description: Informazioni sugli operatori di confronto delle uguaglianze C# e sull'uguaglianza dei tipi C#.
ms.date: 06/26/2019
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
ms.openlocfilehash: 011ef8b570a0bbbc38ec71df4286c3b08c3109da
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174783"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="f036a-103">Operatori di uguaglianza (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f036a-103">Equality operators (C# reference)</span></span>

<span data-ttu-id="f036a-104">Gli operatori [ `==` (uguaglianza)](#equality-operator-) e [ `!=` (disuguaglianza)](#inequality-operator-) verificano se gli operandi sono uguali o meno.</span><span class="sxs-lookup"><span data-stu-id="f036a-104">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="f036a-105">Operatore di uguaglianza ==</span><span class="sxs-lookup"><span data-stu-id="f036a-105">Equality operator ==</span></span>

<span data-ttu-id="f036a-106">L'operatore di uguaglianza `==` restituisce `true` se gli operandi sono uguali, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f036a-106">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="f036a-107">Uguaglianza dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="f036a-107">Value types equality</span></span>

<span data-ttu-id="f036a-108">Gli operandi dei [tipi valore predefiniti](../builtin-types/value-types.md#built-in-value-types) sono uguali se i relativi valori sono uguali:</span><span class="sxs-lookup"><span data-stu-id="f036a-108">Operands of the [built-in value types](../builtin-types/value-types.md#built-in-value-types) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](snippets/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="f036a-109">Per gli `==` operatori, [ `<` , `>` , `<=` e `>=` ](comparison-operators.md) , se uno degli operandi non è un numero ( <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType> ), il risultato dell'operazione è `false` .</span><span class="sxs-lookup"><span data-stu-id="f036a-109">For the `==`, [`<`, `>`, `<=`, and `>=`](comparison-operators.md) operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="f036a-110">Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`.</span><span class="sxs-lookup"><span data-stu-id="f036a-110">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="f036a-111">Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f036a-111">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="f036a-112">Due operandi dello stesso tipo [enum](../builtin-types/enum.md) sono uguali se i valori corrispondenti del tipo integrale sottostante sono uguali.</span><span class="sxs-lookup"><span data-stu-id="f036a-112">Two operands of the same [enum](../builtin-types/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="f036a-113">I tipi [struct](../builtin-types/struct.md) definiti dall'utente non supportano l'operatore `==` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f036a-113">User-defined [struct](../builtin-types/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="f036a-114">Per supportare l'operatore `==`, un tipo struct definito dall'utente deve eseguirne l'[overload](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="f036a-114">To support the `==` operator, a user-defined struct must [overload](operator-overloading.md) it.</span></span>

<span data-ttu-id="f036a-115">A partire da C# 7.3, gli operatori `==` e `!=` sono supportati da [tuple](../builtin-types/value-tuples.md) C#.</span><span class="sxs-lookup"><span data-stu-id="f036a-115">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../builtin-types/value-tuples.md).</span></span> <span data-ttu-id="f036a-116">Per altre informazioni, vedere la sezione [uguaglianza di Tuple](../builtin-types/value-tuples.md#tuple-equality) nell'articolo [tipi di tupla](../builtin-types/value-tuples.md) .</span><span class="sxs-lookup"><span data-stu-id="f036a-116">For more information, see the [Tuple equality](../builtin-types/value-tuples.md#tuple-equality) section of the [Tuple types](../builtin-types/value-tuples.md) article.</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="f036a-117">Uguaglianza dei tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="f036a-117">Reference types equality</span></span>

<span data-ttu-id="f036a-118">Per impostazione predefinita, due operandi di tipo riferimento sono uguali se fanno riferimento allo stesso oggetto:</span><span class="sxs-lookup"><span data-stu-id="f036a-118">By default, two reference-type operands are equal if they refer to the same object:</span></span>

[!code-csharp[reference type equality](snippets/EqualityOperators.cs#ReferenceTypesEquality)]

<span data-ttu-id="f036a-119">Come illustrato nell'esempio, i tipi riferimento definiti dall'utente supportano l'operatore `==` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f036a-119">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="f036a-120">Tuttavia, un tipo riferimento può eseguire l'overload dell'operatore `==`.</span><span class="sxs-lookup"><span data-stu-id="f036a-120">However, a reference type can overload the `==` operator.</span></span> <span data-ttu-id="f036a-121">Se un tipo riferimento esegue l'overload dell'operatore `==`, usare il metodo <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> per verificare se due riferimenti di quel tipo fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="f036a-121">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

### <a name="string-equality"></a><span data-ttu-id="f036a-122">Uguaglianza di stringhe</span><span class="sxs-lookup"><span data-stu-id="f036a-122">String equality</span></span>

<span data-ttu-id="f036a-123">Due operandi [stringa](../builtin-types/reference-types.md#the-string-type) sono uguali quando entrambi sono `null` o entrambe le istanze di stringa sono della stessa lunghezza e contengono caratteri identici in ogni posizione di carattere:</span><span class="sxs-lookup"><span data-stu-id="f036a-123">Two [string](../builtin-types/reference-types.md#the-string-type) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](snippets/EqualityOperators.cs#StringEquality)]

<span data-ttu-id="f036a-124">Si tratta di un confronto ordinale con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f036a-124">That is a case-sensitive ordinal comparison.</span></span> <span data-ttu-id="f036a-125">Per altre informazioni sul confronto di stringhe, vedere [Come confrontare stringhe in C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="f036a-125">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="delegate-equality"></a><span data-ttu-id="f036a-126">Delegare l'uguaglianza</span><span class="sxs-lookup"><span data-stu-id="f036a-126">Delegate equality</span></span>

<span data-ttu-id="f036a-127">Due operandi [delegati](../../programming-guide/delegates/index.md) dello stesso tipo di runtime sono uguali quando entrambi sono `null` o i relativi elenchi di chiamate hanno la stessa lunghezza e voci uguali in ogni posizione:</span><span class="sxs-lookup"><span data-stu-id="f036a-127">Two [delegate](../../programming-guide/delegates/index.md) operands of the same runtime type are equal when both of them are `null` or their invocation lists are of the same length and have equal entries in each position:</span></span>

[!code-csharp-interactive[delegate equality](snippets/EqualityOperators.cs#DelegateEquality)]

<span data-ttu-id="f036a-128">Per altre informazioni, vedere la sezione [Delegare gli operatori di uguaglianza](~/_csharplang/spec/expressions.md#delegate-equality-operators) dell'articolo [Specifiche del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f036a-128">For more information, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="f036a-129">I delegati prodotti dalla valutazione di [espressioni lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) semanticamente identiche non sono uguali, come mostra l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f036a-129">Delegates that are produced from evaluation of semantically identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal, as the following example shows:</span></span>

[!code-csharp-interactive[from identical lambdas](snippets/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a><span data-ttu-id="f036a-130">Operatore di disuguaglianza !=</span><span class="sxs-lookup"><span data-stu-id="f036a-130">Inequality operator !=</span></span>

<span data-ttu-id="f036a-131">L'operatore di disuguaglianza `!=` restituisce `true` se gli operandi sono diversi, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f036a-131">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="f036a-132">Per gli operandi dei [tipi predefiniti](../builtin-types/built-in-types.md), l'espressione `x != y` produce lo stesso risultato dell'espressione `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="f036a-132">For the operands of the [built-in types](../builtin-types/built-in-types.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="f036a-133">Per altre informazioni sull'uguaglianza dei tipi, vedere la sezione [Operatore di uguaglianza](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="f036a-133">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="f036a-134">Nell'esempio seguente viene illustrato l'uso dell'operatore `!=`:</span><span class="sxs-lookup"><span data-stu-id="f036a-134">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](snippets/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="f036a-135">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="f036a-135">Operator overloadability</span></span>

<span data-ttu-id="f036a-136">Un tipo definito dall'utente può eseguire l'[overload](operator-overloading.md) degli operatori `==` e `!=`.</span><span class="sxs-lookup"><span data-stu-id="f036a-136">A user-defined type can [overload](operator-overloading.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="f036a-137">Se un tipo sovraccarica uno dei due operatori, deve anche eseguire l'overload dell'altro.</span><span class="sxs-lookup"><span data-stu-id="f036a-137">If a type overloads one of the two operators, it must also overload the other one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f036a-138">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f036a-138">C# language specification</span></span>

<span data-ttu-id="f036a-139">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f036a-139">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f036a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f036a-140">See also</span></span>

- [<span data-ttu-id="f036a-141">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="f036a-141">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f036a-142">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="f036a-142">C# operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f036a-143">Confronti di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="f036a-143">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [<span data-ttu-id="f036a-144">Operatori di confronto</span><span class="sxs-lookup"><span data-stu-id="f036a-144">Comparison operators</span></span>](comparison-operators.md)
