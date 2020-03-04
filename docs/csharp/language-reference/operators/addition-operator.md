---
title: + Operatori + e += - Riferimenti per C#
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
ms.openlocfilehash: c8452ab1f90bb2873a591b483b5432311a9f9b79
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239626"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="03577-102">Operatori + e += (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="03577-102">+ and += operators (C# reference)</span></span>

<span data-ttu-id="03577-103">Gli operatori `+` e `+=` sono supportati dai tipi numerici [integrali](../builtin-types/integral-numeric-types.md) e a [virgola mobile](../builtin-types/floating-point-numeric-types.md) incorporati, dal tipo di [stringa](../builtin-types/reference-types.md#the-string-type) e dai tipi [delegati](../builtin-types/reference-types.md#the-delegate-type) .</span><span class="sxs-lookup"><span data-stu-id="03577-103">The `+` and `+=` operators are supported by the built-in [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types, the [string](../builtin-types/reference-types.md#the-string-type) type, and [delegate](../builtin-types/reference-types.md#the-delegate-type) types.</span></span>

<span data-ttu-id="03577-104">Per informazioni sull'operatore aritmetico `+`, vedere le sezioni [Operatori più e meno unari](arithmetic-operators.md#unary-plus-and-minus-operators) e [Operatore di addizione +](arithmetic-operators.md#addition-operator-) dell'articolo [Operatori aritmetici](arithmetic-operators.md).</span><span class="sxs-lookup"><span data-stu-id="03577-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="03577-105">Concatenazione stringhe</span><span class="sxs-lookup"><span data-stu-id="03577-105">String concatenation</span></span>

<span data-ttu-id="03577-106">Quando uno o entrambi gli operandi sono di tipo [stringa](../builtin-types/reference-types.md#the-string-type), l'operatore `+` concatena le rappresentazioni di stringa dei due operandi:</span><span class="sxs-lookup"><span data-stu-id="03577-106">When one or both operands are of type [string](../builtin-types/reference-types.md#the-string-type), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionOperator.cs#AddStrings)]

<span data-ttu-id="03577-107">A partire C# da 6, l' [interpolazione di stringhe](../tokens/interpolated.md) rappresenta un modo più pratico per formattare le stringhe:</span><span class="sxs-lookup"><span data-stu-id="03577-107">Beginning with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="03577-108">Combinazione di delegati</span><span class="sxs-lookup"><span data-stu-id="03577-108">Delegate combination</span></span>

<span data-ttu-id="03577-109">Per gli operandi con lo stesso tipo [delegato](../builtin-types/reference-types.md#the-delegate-type), l'operatore `+` restituisce una nuova istanza di delegato che, quando viene chiamata, richiama l'operando di sinistra e quindi quello di destra.</span><span class="sxs-lookup"><span data-stu-id="03577-109">For operands of the same [delegate](../builtin-types/reference-types.md#the-delegate-type) type, the `+` operator returns a new delegate instance that, when invoked, invokes the left-hand operand and then invokes the right-hand operand.</span></span> <span data-ttu-id="03577-110">Se uno degli operandi è `null`, l'operatore `+` restituisce il valore di un altro operando, che può essere anch'esso `null`.</span><span class="sxs-lookup"><span data-stu-id="03577-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="03577-111">L'esempio seguente mostra in che modo è possibile combinare delegati con l'operatore `+`:</span><span class="sxs-lookup"><span data-stu-id="03577-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionOperator.cs#AddDelegates)]

<span data-ttu-id="03577-112">Per eseguire la rimozione dei delegati, usare l'[operatore `-`](subtraction-operator.md#delegate-removal).</span><span class="sxs-lookup"><span data-stu-id="03577-112">To perform delegate removal, use the [`-` operator](subtraction-operator.md#delegate-removal).</span></span>

<span data-ttu-id="03577-113">Per altre informazioni sui tipi delegate, vedere [Delegati](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="03577-113">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="03577-114">Operatore di assegnazione di addizione +=</span><span class="sxs-lookup"><span data-stu-id="03577-114">Addition assignment operator +=</span></span>

<span data-ttu-id="03577-115">Un'espressione che usa l'operatore `+=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="03577-115">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="03577-116">equivale a</span><span class="sxs-lookup"><span data-stu-id="03577-116">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="03577-117">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="03577-117">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="03577-118">Nell'esempio seguente viene illustrato l'uso dell'operatore `+=`:</span><span class="sxs-lookup"><span data-stu-id="03577-118">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionOperator.cs#AddAndAssign)]

<span data-ttu-id="03577-119">È anche possibile usare l'operatore `+=` per specificare un metodo del gestore eventi quando si sottoscrive un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="03577-119">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="03577-120">Per altre informazioni, vedere [Procedura: Sottoscrivere e annullare la sottoscrizione di eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="03577-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="03577-121">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="03577-121">Operator overloadability</span></span>

<span data-ttu-id="03577-122">Un tipo definito dall'utente può eseguire l'[overload](operator-overloading.md) dell'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="03577-122">A user-defined type can [overload](operator-overloading.md) the `+` operator.</span></span> <span data-ttu-id="03577-123">Quando viene eseguito l'overload di un operatore `+` binario, viene eseguito in modo implicito anche l'overload dell'operatore `+=`.</span><span class="sxs-lookup"><span data-stu-id="03577-123">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="03577-124">Un tipo definito dall'utente non può eseguire l'overload dell'operatore `+=` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="03577-124">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="03577-125">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="03577-125">C# language specification</span></span>

<span data-ttu-id="03577-126">Per altre informazioni, vedere le sezioni [Operatore + unario](~/_csharplang/spec/expressions.md#unary-plus-operator) e [Operatore addizione](~/_csharplang/spec/expressions.md#addition-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="03577-126">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="03577-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03577-127">See also</span></span>

- [<span data-ttu-id="03577-128">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="03577-128">C# reference</span></span>](../index.md)
- [<span data-ttu-id="03577-129">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="03577-129">C# operators</span></span>](index.md)
- [<span data-ttu-id="03577-130">Come concatenare più stringhe</span><span class="sxs-lookup"><span data-stu-id="03577-130">How to concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="03577-131">Eventi</span><span class="sxs-lookup"><span data-stu-id="03577-131">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="03577-132">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="03577-132">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="03577-133">Operatori - e -=</span><span class="sxs-lookup"><span data-stu-id="03577-133">- and -= operators</span></span>](subtraction-operator.md)
