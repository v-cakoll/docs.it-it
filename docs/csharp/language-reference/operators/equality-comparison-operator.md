---
title: Operatore == - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: 6d86348eefc87e847267f262141ff49e5d51faae
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655959"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="25765-102">Operatore == (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="25765-102">== Operator (C# Reference)</span></span>

<span data-ttu-id="25765-103">L'operatore di uguaglianza `==` restituisce `true` se gli operandi sono uguali, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="25765-103">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

## <a name="value-types-equality"></a><span data-ttu-id="25765-104">Uguaglianza dei tipi valore</span><span class="sxs-lookup"><span data-stu-id="25765-104">Value types equality</span></span>

<span data-ttu-id="25765-105">Gli operandi dei [tipi valore predefiniti](../keywords/value-types-table.md) sono uguali se i relativi valori sono uguali:</span><span class="sxs-lookup"><span data-stu-id="25765-105">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="25765-106">Per gli operatori relazionali `==`, `>`, `<` `>=`, e `<=`, se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="25765-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="25765-107">Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`).</span><span class="sxs-lookup"><span data-stu-id="25765-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="25765-108">Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="25765-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="25765-109">Due operandi dello stesso tipo [enum](../keywords/enum.md) sono uguali se i valori corrispondenti del tipo integrale sottostante sono uguali.</span><span class="sxs-lookup"><span data-stu-id="25765-109">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="25765-110">Per impostazione predefinita, l'operatore `==` non è definito per un tipo [struct](../keywords/struct.md) definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="25765-110">By default, the `==` operator is not defined for a user-defined [struct](../keywords/struct.md) type.</span></span> <span data-ttu-id="25765-111">Un tipo definito dall'utente può eseguire l'[overload](#operator-overloadability) dell'operatore `==`.</span><span class="sxs-lookup"><span data-stu-id="25765-111">A user-defined type can [overload](#operator-overloadability) the `==` operator.</span></span>

<span data-ttu-id="25765-112">A partire da C# 7.3, gli operatori `==` e [`!=`](not-equal-operator.md) sono supportati da [tuple](../../tuples.md) C#.</span><span class="sxs-lookup"><span data-stu-id="25765-112">Beginning with C# 7.3, the `==` and [`!=`](not-equal-operator.md) operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="25765-113">Per altre informazioni, vedere la sezione [Uguaglianza e tuple](../../tuples.md#equality-and-tuples) nell'articolo [Tipi tupla in C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="25765-113">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

## <a name="string-equality"></a><span data-ttu-id="25765-114">Uguaglianza di stringhe</span><span class="sxs-lookup"><span data-stu-id="25765-114">String equality</span></span>

<span data-ttu-id="25765-115">Due operandi [stringa](../keywords/string.md) sono uguali quando entrambi sono `null` o entrambe le istanze di stringa sono della stessa lunghezza e contengono caratteri identici in ogni posizione di carattere:</span><span class="sxs-lookup"><span data-stu-id="25765-115">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="25765-116">Questo è un confronto ordinale senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="25765-116">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="25765-117">Per altre informazioni su come confrontare le stringhe, vedere [Come confrontare stringhe in C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="25765-117">For more information about how to compare strings, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

## <a name="reference-types-equality"></a><span data-ttu-id="25765-118">Uguaglianza dei tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="25765-118">Reference types equality</span></span>

<span data-ttu-id="25765-119">Due operandi di tipo riferimento diversi da `string` sono uguali quando fanno riferimento allo stesso oggetto:</span><span class="sxs-lookup"><span data-stu-id="25765-119">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="25765-120">L'esempio mostra che l'operatore `==` è supportato dai tipi riferimento definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="25765-120">The example shows that the `==` operator is supported by user-defined reference types.</span></span> <span data-ttu-id="25765-121">Tuttavia, un tipo riferimento definito dall'utente può eseguire l'overload dell'operatore `==`.</span><span class="sxs-lookup"><span data-stu-id="25765-121">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="25765-122">Se un tipo riferimento esegue l'overload dell'operatore `==`, usare il metodo <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> per verificare se due riferimenti di quel tipo fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="25765-122">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="25765-123">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="25765-123">Operator overloadability</span></span>

<span data-ttu-id="25765-124">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `==`.</span><span class="sxs-lookup"><span data-stu-id="25765-124">User-defined types can [overload](../keywords/operator.md) the `==` operator.</span></span> <span data-ttu-id="25765-125">Se un tipo esegue l'overload dell'operatore di uguaglianza `==`, deve anche eseguire l'overload dell'[operatore di disuguaglianza](not-equal-operator.md) `!=`.</span><span class="sxs-lookup"><span data-stu-id="25765-125">If a type overloads the equality operator `==`, it must also overload the [inequality operator](not-equal-operator.md) `!=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="25765-126">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="25765-126">C# language specification</span></span>

<span data-ttu-id="25765-127">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="25765-127">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="25765-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25765-128">See also</span></span>

- [<span data-ttu-id="25765-129">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="25765-129">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="25765-130">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="25765-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="25765-131">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="25765-131">C# Operators</span></span>](index.md)
- [<span data-ttu-id="25765-132">Confronti di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="25765-132">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
