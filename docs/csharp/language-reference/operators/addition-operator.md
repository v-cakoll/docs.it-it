---
title: + (operatore) - Riferimenti per C#
ms.custom: seodec18
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 92e20dad8ae6358f71137e955bb80e3641a66a54
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237753"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="cc36c-102">Operatore + (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cc36c-102">+ Operator (C# Reference)</span></span>

<span data-ttu-id="cc36c-103">L'operatore `+` è supportato in due forme: un operatore + unario o un operatore addizione binario.</span><span class="sxs-lookup"><span data-stu-id="cc36c-103">The `+` operator is supported in two forms: a unary plus operator or a binary addition operator.</span></span>

## <a name="unary-plus-operator"></a><span data-ttu-id="cc36c-104">Operatore più unario</span><span class="sxs-lookup"><span data-stu-id="cc36c-104">Unary plus operator</span></span>

<span data-ttu-id="cc36c-105">L'operatore `+` unario restituisce il valore del proprio operando.</span><span class="sxs-lookup"><span data-stu-id="cc36c-105">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="cc36c-106">È supportato da tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="cc36c-106">It's supported by all numeric types.</span></span>

## <a name="numeric-addition"></a><span data-ttu-id="cc36c-107">Addizione numerica</span><span class="sxs-lookup"><span data-stu-id="cc36c-107">Numeric addition</span></span>

<span data-ttu-id="cc36c-108">Per i tipi numerici, l'operatore `+` calcola la somma dei due operandi:</span><span class="sxs-lookup"><span data-stu-id="cc36c-108">For numeric types, the `+` operator computes the sum of its operands:</span></span>

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

## <a name="string-concatenation"></a><span data-ttu-id="cc36c-109">Concatenazione stringhe</span><span class="sxs-lookup"><span data-stu-id="cc36c-109">String concatenation</span></span>

<span data-ttu-id="cc36c-110">Quando uno o entrambi gli operandi sono di tipo [stringa](../keywords/string.md), l'operatore `+` concatena le rappresentazioni di stringa dei due operandi:</span><span class="sxs-lookup"><span data-stu-id="cc36c-110">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="cc36c-111">A partire da C# 6, l'[interpolazione di stringhe](../tokens/interpolated.md) offre un pratico strumento per formattare le stringhe:</span><span class="sxs-lookup"><span data-stu-id="cc36c-111">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="cc36c-112">Combinazione di delegati</span><span class="sxs-lookup"><span data-stu-id="cc36c-112">Delegate combination</span></span>

<span data-ttu-id="cc36c-113">Per i tipi [delegate](../keywords/delegate.md), l'operatore `+` restituisce una nuova istanza di delegato che, quando viene richiamata, richiama il primo operando e quindi il secondo.</span><span class="sxs-lookup"><span data-stu-id="cc36c-113">For [delegate](../keywords/delegate.md) types, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="cc36c-114">Se uno degli operandi è `null`, l'operatore `+` restituisce il valore di un altro operando, che può essere anch'esso `null`.</span><span class="sxs-lookup"><span data-stu-id="cc36c-114">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="cc36c-115">L'esempio seguente mostra in che modo è possibile combinare delegati con l'operatore `+`:</span><span class="sxs-lookup"><span data-stu-id="cc36c-115">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="cc36c-116">Per altre informazioni sui tipi delegate, vedere [Delegati](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="cc36c-116">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="cc36c-117">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="cc36c-117">Operator overloadability</span></span>

<span data-ttu-id="cc36c-118">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) degli operatori `+` unario e binario.</span><span class="sxs-lookup"><span data-stu-id="cc36c-118">User-defined types can [overload](../keywords/operator.md) the unary and binary `+` operators.</span></span> <span data-ttu-id="cc36c-119">Quando viene eseguito l'overload di un operatore `+`, viene anche aggiunto l'[operatore di assegnazione di addizione](addition-assignment-operator.md) `+=`.</span><span class="sxs-lookup"><span data-stu-id="cc36c-119">When a binary `+` operator is overloaded, the [addition assignment operator](addition-assignment-operator.md) `+=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="cc36c-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cc36c-120">C# language specification</span></span>

<span data-ttu-id="cc36c-121">Per altre informazioni, vedere le sezioni [Operatore + unario](~/_csharplang/spec/expressions.md#unary-plus-operator) e [Operatore addizione](~/_csharplang/spec/expressions.md#addition-operator) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="cc36c-121">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cc36c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc36c-122">See also</span></span>

- [<span data-ttu-id="cc36c-123">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="cc36c-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cc36c-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cc36c-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cc36c-125">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="cc36c-125">C# Operators</span></span>](index.md)
- [<span data-ttu-id="cc36c-126">Interpolazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="cc36c-126">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="cc36c-127">Procedura: Concatenare più stringhe</span><span class="sxs-lookup"><span data-stu-id="cc36c-127">How to: Concatenate Multiple Strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="cc36c-128">Delegati</span><span class="sxs-lookup"><span data-stu-id="cc36c-128">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="cc36c-129">Checked e Unchecked</span><span class="sxs-lookup"><span data-stu-id="cc36c-129">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
