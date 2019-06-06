---
title: + Operatori + e += (Riferimenti per C#)
ms.custom: seodec18
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d03743bad47c60925462d027d18445047ebc0fc9
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300110"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="06a5e-102">Operatori + e += (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="06a5e-102">+ and += operators (C# Reference)</span></span>

<span data-ttu-id="06a5e-103">L'operatore `+` è supportato dai tipi numerici predefiniti, dai tipi [stringa](../keywords/string.md) e dai tipi [delegato](../keywords/delegate.md).</span><span class="sxs-lookup"><span data-stu-id="06a5e-103">The `+` operator is supported by the built-in numeric types, [string](../keywords/string.md) type, and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="06a5e-104">Per informazioni sull'operatore aritmetico `+`, vedere le sezioni [Operatori più e meno unari](arithmetic-operators.md#unary-plus-and-minus-operators) e [Operatore di addizione +](arithmetic-operators.md#addition-operator-) dell'articolo [Operatori aritmetici](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="06a5e-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="06a5e-105">Concatenazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="06a5e-105">String concatenation</span></span>

<span data-ttu-id="06a5e-106">Quando uno o entrambi gli operandi sono di tipo [stringa](../keywords/string.md), l'operatore `+` concatena le rappresentazioni di stringa dei due operandi:</span><span class="sxs-lookup"><span data-stu-id="06a5e-106">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="06a5e-107">A partire da C# 6, l'[interpolazione di stringhe](../tokens/interpolated.md) offre un pratico strumento per formattare le stringhe:</span><span class="sxs-lookup"><span data-stu-id="06a5e-107">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="06a5e-108">Combinazione di delegati</span><span class="sxs-lookup"><span data-stu-id="06a5e-108">Delegate combination</span></span>

<span data-ttu-id="06a5e-109">Per gli operandi con lo stesso tipo [delegato](../keywords/delegate.md), l'operatore `+` restituisce una nuova istanza di delegato che, quando viene richiamata, richiama il primo operando e quindi il secondo.</span><span class="sxs-lookup"><span data-stu-id="06a5e-109">For operands of the same [delegate](../keywords/delegate.md) type, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="06a5e-110">Se uno degli operandi è `null`, l'operatore `+` restituisce il valore di un altro operando, che può essere anch'esso `null`.</span><span class="sxs-lookup"><span data-stu-id="06a5e-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="06a5e-111">L'esempio seguente mostra in che modo è possibile combinare delegati con l'operatore `+`:</span><span class="sxs-lookup"><span data-stu-id="06a5e-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="06a5e-112">Per altre informazioni sui tipi delegate, vedere [Delegati](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="06a5e-112">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="06a5e-113">Operatore di assegnazione di addizione +=</span><span class="sxs-lookup"><span data-stu-id="06a5e-113">Addition assignment operator +=</span></span>

<span data-ttu-id="06a5e-114">Un'espressione che usa l'operatore `+=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="06a5e-114">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="06a5e-115">equivale a</span><span class="sxs-lookup"><span data-stu-id="06a5e-115">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="06a5e-116">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="06a5e-116">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="06a5e-117">Nell'esempio seguente viene illustrato l'uso dell'operatore `+=`:</span><span class="sxs-lookup"><span data-stu-id="06a5e-117">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

<span data-ttu-id="06a5e-118">È anche possibile usare l'operatore `+=` per specificare un metodo del gestore eventi quando si sottoscrive un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="06a5e-118">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="06a5e-119">Per altre informazioni, vedere [Procedura: Sottoscrivere e annullare la sottoscrizione di eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="06a5e-119">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="06a5e-120">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="06a5e-120">Operator overloadability</span></span>

<span data-ttu-id="06a5e-121">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) dell'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="06a5e-121">A user-defined type can [overload](../keywords/operator.md) the `+` operator.</span></span> <span data-ttu-id="06a5e-122">Quando viene eseguito l'overload di un operatore `+` binario, viene eseguito in modo implicito anche l'overload dell'operatore `+=`.</span><span class="sxs-lookup"><span data-stu-id="06a5e-122">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="06a5e-123">Un tipo definito dall'utente non può eseguire l'overload dell'operatore `+=` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="06a5e-123">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="06a5e-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="06a5e-124">C# language specification</span></span>

<span data-ttu-id="06a5e-125">Per altre informazioni, vedere le sezioni [Operatore + unario](~/_csharplang/spec/expressions.md#unary-plus-operator) e [Operatore addizione](~/_csharplang/spec/expressions.md#addition-operator) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="06a5e-125">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="06a5e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06a5e-126">See also</span></span>

- [<span data-ttu-id="06a5e-127">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="06a5e-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="06a5e-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="06a5e-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="06a5e-129">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="06a5e-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="06a5e-130">Interpolazione di stringhe</span><span class="sxs-lookup"><span data-stu-id="06a5e-130">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="06a5e-131">Procedura: Concatenare più stringhe</span><span class="sxs-lookup"><span data-stu-id="06a5e-131">How to: concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="06a5e-132">Delegati</span><span class="sxs-lookup"><span data-stu-id="06a5e-132">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="06a5e-133">Eventi</span><span class="sxs-lookup"><span data-stu-id="06a5e-133">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="06a5e-134">Checked e Unchecked</span><span class="sxs-lookup"><span data-stu-id="06a5e-134">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="06a5e-135">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="06a5e-135">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="06a5e-136">Operatori - e -=</span><span class="sxs-lookup"><span data-stu-id="06a5e-136">- and -= operators</span></span>](subtraction-operator.md)
