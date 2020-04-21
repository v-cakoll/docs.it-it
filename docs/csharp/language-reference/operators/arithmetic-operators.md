---
title: Operatori aritmetici - Riferimenti per C#
description: Informazioni sugli operatori C# che eseguono operazioni di moltiplicazione, divisione, resto, addizione e sottrazione con i tipi numerici.
ms.date: 03/27/2019
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: ea9bf9e065b2953fd20e0503a19d1dc143064c5d
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738738"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="1ec9c-103">Operatori aritmetici (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1ec9c-103">Arithmetic operators (C# reference)</span></span>

<span data-ttu-id="1ec9c-104">Gli operatori seguenti eseguono operazioni aritmetiche con operandi di tipi numerici:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-104">The following operators perform arithmetic operations with operands of numeric types:</span></span>

- <span data-ttu-id="1ec9c-105">Operatori unario [ `++` (incremento),](#increment-operator-) [ `--` (decremento)](#decrement-operator---), [ `+` (più)](#unary-plus-and-minus-operators)e [ `-` (meno)](#unary-plus-and-minus-operators)</span><span class="sxs-lookup"><span data-stu-id="1ec9c-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators</span></span>
- <span data-ttu-id="1ec9c-106">Operatori binari [ `*` (moltiplicazione)](#multiplication-operator-), [ `/` (divisione)](#division-operator-), [ `%` (resto),](#remainder-operator-) [ `+` (addizione)](#addition-operator-)e [ `-` (sottrazione)](#subtraction-operator--)</span><span class="sxs-lookup"><span data-stu-id="1ec9c-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators</span></span>

<span data-ttu-id="1ec9c-107">Tali operatori sono supportati da tutti i tipi [numerici integrali](../builtin-types/integral-numeric-types.md) e [a virgola mobile.](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="1ec9c-107">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="1ec9c-108">Operatore di incremento ++</span><span class="sxs-lookup"><span data-stu-id="1ec9c-108">Increment operator ++</span></span>

<span data-ttu-id="1ec9c-109">L'operatore di incremento unario `++` incrementa il suo operando di 1.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-109">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="1ec9c-110">L'operando deve essere una variabile, un accesso a una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un accesso a un [indicizzatore](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="1ec9c-110">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="1ec9c-111">L'operatore di incremento è supportato in due forme: l'operatore di incremento suffisso, `x++`, e l'operatore di incremento prefisso, `++x`.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-111">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="1ec9c-112">Operatore di incremento suffisso</span><span class="sxs-lookup"><span data-stu-id="1ec9c-112">Postfix increment operator</span></span>

<span data-ttu-id="1ec9c-113">Il risultato di `x++` è il valore di `x` *prima* dell'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-113">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](snippets/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="1ec9c-114">Operatore di incremento prefisso</span><span class="sxs-lookup"><span data-stu-id="1ec9c-114">Prefix increment operator</span></span>

<span data-ttu-id="1ec9c-115">Il risultato di `++x` è il valore di `x` *dopo* l'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-115">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](snippets/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="1ec9c-116">Operatore di decremento --</span><span class="sxs-lookup"><span data-stu-id="1ec9c-116">Decrement operator --</span></span>

<span data-ttu-id="1ec9c-117">L'operatore di decremento unario `--` decrementa il proprio operando di 1.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-117">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="1ec9c-118">L'operando deve essere una variabile, un accesso a una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un accesso a un [indicizzatore](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="1ec9c-118">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="1ec9c-119">L'operatore di decremento è supportato in due forme: l'operatore di decremento suffisso, `x--`, e l'operatore di decremento prefisso, `--x`.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-119">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="1ec9c-120">Operatore di decremento suffisso</span><span class="sxs-lookup"><span data-stu-id="1ec9c-120">Postfix decrement operator</span></span>

<span data-ttu-id="1ec9c-121">Il risultato di `x--` è il valore di `x` *prima* dell'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-121">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](snippets/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="1ec9c-122">Operatore di decremento prefisso</span><span class="sxs-lookup"><span data-stu-id="1ec9c-122">Prefix decrement operator</span></span>

<span data-ttu-id="1ec9c-123">Il risultato di `--x` è il valore di `x` *dopo* l'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-123">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](snippets/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="1ec9c-124">Operatori più e meno unari</span><span class="sxs-lookup"><span data-stu-id="1ec9c-124">Unary plus and minus operators</span></span>

<span data-ttu-id="1ec9c-125">L'operatore `+` unario restituisce il valore del proprio operando.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-125">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="1ec9c-126">L'operatore `-` unario calcola la negazione numerica del proprio operando.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-126">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](snippets/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="1ec9c-127">Il tipo [ulong](../builtin-types/integral-numeric-types.md) non supporta `-` l'operatore unario.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-127">The [ulong](../builtin-types/integral-numeric-types.md) type doesn't support the unary `-` operator.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="1ec9c-128">Operatore di moltiplicazione \*</span><span class="sxs-lookup"><span data-stu-id="1ec9c-128">Multiplication operator \*</span></span>

<span data-ttu-id="1ec9c-129">L'operatore di moltiplicazione `*` calcola il prodotto degli operandi:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-129">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](snippets/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="1ec9c-130">L'operatore `*` unario è l'[operatore di riferimento indiretto a puntatore](pointer-related-operators.md#pointer-indirection-operator-).</span><span class="sxs-lookup"><span data-stu-id="1ec9c-130">The unary `*` operator is the [pointer indirection operator](pointer-related-operators.md#pointer-indirection-operator-).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="1ec9c-131">Operatore di divisione /</span><span class="sxs-lookup"><span data-stu-id="1ec9c-131">Division operator /</span></span>

<span data-ttu-id="1ec9c-132">L'operatore di divisione `/` divide l'operando di sinistra per l'operando di destra.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-132">The division operator `/` divides its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="1ec9c-133">Divisione di interi</span><span class="sxs-lookup"><span data-stu-id="1ec9c-133">Integer division</span></span>

<span data-ttu-id="1ec9c-134">Per gli operandi di tipo Integer, il risultato dell'operatore `/` è di tipo Integer ed è uguale al quoziente dei due operandi arrotondato allo zero:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-134">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](snippets/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="1ec9c-135">Per ottenere il quoziente dei due operandi come numero a virgola mobile, usare il tipo `float`, `double`,o `decimal`:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-135">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](snippets/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="1ec9c-136">Divisione a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="1ec9c-136">Floating-point division</span></span>

<span data-ttu-id="1ec9c-137">Per i tipi `float`, `double` e `decimal`, il risultato dell'operatore `/` è il quoziente dei due operandi:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-137">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](snippets/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="1ec9c-138">Se uno degli operandi è `decimal`, un altro operando non può essere né `float` né `double`, perché né `float` né `double` è convertibile implicitamente in `decimal`.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-138">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="1ec9c-139">È necessario convertire esplicitamente l'operando `float` o `double` nel tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-139">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="1ec9c-140">Per ulteriori informazioni sulle conversioni tra tipi numerici, vedere [Conversioni numeriche predefinite](../builtin-types/numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="1ec9c-140">For more information about conversions between numeric types, see [Built-in numeric conversions](../builtin-types/numeric-conversions.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="1ec9c-141">Operatore di resto %</span><span class="sxs-lookup"><span data-stu-id="1ec9c-141">Remainder operator %</span></span>

<span data-ttu-id="1ec9c-142">L'operatore di resto `%` calcola il resto dopo aver diviso l'operando di sinistra per l'operando di destra.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-142">The remainder operator `%` computes the remainder after dividing its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="1ec9c-143">Resto intero</span><span class="sxs-lookup"><span data-stu-id="1ec9c-143">Integer remainder</span></span>

<span data-ttu-id="1ec9c-144">Per gli operandi di tipi interi, il risultato di `a % b` è il valore prodotto da `a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-144">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="1ec9c-145">Il segno del resto diverso da zero è uguale a quello dell'operando di sinistra, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-145">The sign of the non-zero remainder is the same as that of the left-hand operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](snippets/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="1ec9c-146">Usare il metodo <xref:System.Math.DivRem%2A?displayProperty=nameWithType> per calcolare sia la divisione di numeri interi, sia i risultati del resto.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-146">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="1ec9c-147">Resto a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="1ec9c-147">Floating-point remainder</span></span>

<span data-ttu-id="1ec9c-148">Per gli operandi `float` e `double`, il risultato di `x % y` per `x` e `y` finiti è il valore `z` tale che</span><span class="sxs-lookup"><span data-stu-id="1ec9c-148">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="1ec9c-149">Il segno di `z`, se diverso da zero, è uguale a quello di `x`.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-149">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="1ec9c-150">Il valore assoluto di `z` è il valore prodotto da `|x| - n * |y|` in cui `n` è l'intero più grande possibile, che è minore o uguale a `|x| / |y|` e `|x|` e `|y|` sono i valori assoluti di `x` e `y`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-150">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec9c-151">Questo metodo di calcolo del resto è analogo a quello utilizzato per gli operandi interi, ma diverso dalla specifica IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-151">This method of computing the remainder is analogous to that used for integer operands, but different from the IEEE 754 specification.</span></span> <span data-ttu-id="1ec9c-152">Se è necessaria l'operazione di resto conforme alla specifica IEEE 754, utilizzare il <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> metodo .</span><span class="sxs-lookup"><span data-stu-id="1ec9c-152">If you need the remainder operation that complies with the IEEE 754 specification, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1ec9c-153">Per informazioni sul comportamento dell'operatore `%` in caso di operandi non finiti, vedere la sezione [Operatore di resto](~/_csharplang/spec/expressions.md#remainder-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="1ec9c-153">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="1ec9c-154">Per gli operandi `decimal`, l'operatore di resto `%` equivale all'[operatore di resto](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) di tipo <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-154">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="1ec9c-155">L'esempio seguente illustra il comportamento dell'operatore di resto con operandi a virgola mobile:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-155">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](snippets/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="1ec9c-156">Operatore di addizione +</span><span class="sxs-lookup"><span data-stu-id="1ec9c-156">Addition operator +</span></span>

<span data-ttu-id="1ec9c-157">L'operatore di addizione `+` calcola la somma degli operandi:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-157">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](snippets/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="1ec9c-158">È inoltre possibile `+` utilizzare l'operatore per la concatenazione di stringhe e la combinazione di delegati.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-158">You can also use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="1ec9c-159">Per altre informazioni, vedere l'articolo [ `+` operatori and. `+=` ](addition-operator.md)</span><span class="sxs-lookup"><span data-stu-id="1ec9c-159">For more information, see the [`+` and `+=` operators](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="1ec9c-160">Operatore di sottrazione -</span><span class="sxs-lookup"><span data-stu-id="1ec9c-160">Subtraction operator -</span></span>

<span data-ttu-id="1ec9c-161">L'operatore di sottrazione `-` sottrae l'operando di destra dall'operando di sinistra:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-161">The subtraction operator `-` subtracts its right-hand operand from its left-hand operand:</span></span>

[!code-csharp-interactive[subtraction operator](snippets/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="1ec9c-162">È inoltre possibile `-` utilizzare l'operatore per delegare la rimozione.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-162">You can also use the `-` operator for delegate removal.</span></span> <span data-ttu-id="1ec9c-163">Per altre informazioni, vedere l'articolo [ `-` operatori and. `-=` ](subtraction-operator.md)</span><span class="sxs-lookup"><span data-stu-id="1ec9c-163">For more information, see the [`-` and `-=` operators](subtraction-operator.md) article.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="1ec9c-164">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="1ec9c-164">Compound assignment</span></span>

<span data-ttu-id="1ec9c-165">Per un operatore binario `op`, un'espressione di assegnazione composta in formato</span><span class="sxs-lookup"><span data-stu-id="1ec9c-165">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="1ec9c-166">equivale a</span><span class="sxs-lookup"><span data-stu-id="1ec9c-166">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="1ec9c-167">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-167">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="1ec9c-168">L'esempio seguente illustra l'uso dell'assegnazione composta con gli operatori aritmetici:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-168">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](snippets/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="1ec9c-169">A causa delle [promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions) il risultato dell'operazione `op` potrebbe non essere convertibile in modo implicito nel tipo `T` di `x`.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-169">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="1ec9c-170">In questo caso, se `op` è un operatore già definito e il risultato dell'operazione è convertibile in modo esplicito nel tipo `T` di `x`, un'espressione di assegnazione composta nel formato `x op= y` equivale a `x = (T)(x op y)`, con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-170">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="1ec9c-171">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-171">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](snippets/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

<span data-ttu-id="1ec9c-172">È inoltre `+=` possibile `-=` utilizzare gli operatori e per sottoscrivere e annullare la sottoscrizione a un [evento,](../keywords/event.md)rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-172">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from an [event](../keywords/event.md), respectively.</span></span> <span data-ttu-id="1ec9c-173">Per ulteriori informazioni, vedere [Come sottoscrivere e annullare la sottoscrizione agli eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="1ec9c-173">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="1ec9c-174">Precedenza e associatività degli operatori</span><span class="sxs-lookup"><span data-stu-id="1ec9c-174">Operator precedence and associativity</span></span>

<span data-ttu-id="1ec9c-175">Nell'elenco seguente gli operatori aritmetici sono ordinati dalla precedenza più elevata a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-175">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="1ec9c-176">Operatori di incremento `x++` e decremento `x--` in forma suffissa</span><span class="sxs-lookup"><span data-stu-id="1ec9c-176">Postfix increment `x++` and decrement `x--` operators</span></span>
- <span data-ttu-id="1ec9c-177">Operatori di incremento `++x` e decremento `--x` e unari `+` e `-`</span><span class="sxs-lookup"><span data-stu-id="1ec9c-177">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators</span></span>
- <span data-ttu-id="1ec9c-178">Operatori moltiplicativi `*`, `/` e `%`</span><span class="sxs-lookup"><span data-stu-id="1ec9c-178">Multiplicative `*`, `/`, and `%` operators</span></span>
- <span data-ttu-id="1ec9c-179">Operatori di addizione `+` e `-`</span><span class="sxs-lookup"><span data-stu-id="1ec9c-179">Additive `+` and `-` operators</span></span>

<span data-ttu-id="1ec9c-180">Gli operatori aritmetici binari prevedono l'associazione all'operando sinistro.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-180">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="1ec9c-181">Ciò significa che gli operatori con lo stesso livello di precedenza vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-181">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="1ec9c-182">Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza e dall'associatività degli operatori.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](snippets/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="1ec9c-183">Per l'elenco completo degli operatori di C, ordinati in base al livello di precedenza, vedere la sezione [Precedenza](index.md#operator-precedence) degli operatori dell'articolo Operatori di [C.](index.md)</span><span class="sxs-lookup"><span data-stu-id="1ec9c-183">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="1ec9c-184">Overflow aritmetico e divisione per zero</span><span class="sxs-lookup"><span data-stu-id="1ec9c-184">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="1ec9c-185">Quando il risultato di un'operazione aritmetica non rientra nell'intervallo di valori finiti possibili del tipo numerico interessato, il comportamento di un operatore aritmetico dipende dal tipo dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-185">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="1ec9c-186">Overflow aritmetico di numeri interi</span><span class="sxs-lookup"><span data-stu-id="1ec9c-186">Integer arithmetic overflow</span></span>

<span data-ttu-id="1ec9c-187">La divisione di interi per zero genera sempre un'eccezione <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-187">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="1ec9c-188">In caso di overflow aritmetico di interi, un contesto di verifica overflow, che può essere [verificato o non verificato](../keywords/checked-and-unchecked.md), controlla il comportamento risultante:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-188">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="1ec9c-189">In un contesto verificato, se l'overflow si verifica in un'espressione costante, verrà restituito un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-189">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="1ec9c-190">Quando invece l'operazione avviene in fase di esecuzione, viene generata una <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-190">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="1ec9c-191">In un contesto non verificato, il risultato viene troncato tramite la rimozione dei bit più significativi che non rientrano nel tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-191">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="1ec9c-192">Oltre alle istruzioni [checked e unchecked](../keywords/checked-and-unchecked.md), è possibile usare gli operatori `checked` e `unchecked` per controllare il contesto di verifica overflow in cui viene valutata un'espressione:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-192">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](snippets/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="1ec9c-193">Per impostazione predefinita, le operazioni aritmetiche vengono eseguite in un contesto *non verificato*.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-193">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="1ec9c-194">Overflow aritmetico di numeri a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="1ec9c-194">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="1ec9c-195">Le operazioni aritmetiche con i tipi `float` e `double` non generano mai un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-195">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="1ec9c-196">Il risultato delle operazioni aritmetiche con questi tipi può essere uno dei valori speciali che rappresentano un numero infinito e non un numero:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-196">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](snippets/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="1ec9c-197">Per gli operandi di tipo `decimal`, l'overflow aritmetico genera sempre una <xref:System.OverflowException> e la divisione per zero genera sempre una <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-197">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="1ec9c-198">Errori di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="1ec9c-198">Round-off errors</span></span>

<span data-ttu-id="1ec9c-199">A causa delle limitazioni generali della rappresentazione a virgola mobile dei numeri reali e dell'aritmetica a virgola mobile, potrebbero verificarsi errori di arrotondamento nei calcoli con tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-199">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="1ec9c-200">Ossia, il risultato prodotto di un'espressione può essere diverso dal risultato matematico previsto.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-200">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="1ec9c-201">L'esempio seguente illustra molti di questi casi:</span><span class="sxs-lookup"><span data-stu-id="1ec9c-201">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](snippets/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="1ec9c-202">Per ulteriori informazioni, vedere le osservazioni nelle pagine di riferimento [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks)o [System.Decimal](/dotnet/api/system.decimal#remarks) .</span><span class="sxs-lookup"><span data-stu-id="1ec9c-202">For more information, see remarks at the [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="1ec9c-203">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="1ec9c-203">Operator overloadability</span></span>

<span data-ttu-id="1ec9c-204">Un tipo definito dall'utente può`++` `--`eseguire `+` `-``*`l'overload degli `/`operatori `%` `+`aritmetici `-`unari ( , , , e ) e binary ( , , , , e ). [overload](operator-overloading.md)</span><span class="sxs-lookup"><span data-stu-id="1ec9c-204">A user-defined type can [overload](operator-overloading.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="1ec9c-205">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione composta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-205">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="1ec9c-206">Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="1ec9c-206">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1ec9c-207">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1ec9c-207">C# language specification</span></span>

<span data-ttu-id="1ec9c-208">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="1ec9c-208">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="1ec9c-209">Operatori di incremento e decremento suffissi</span><span class="sxs-lookup"><span data-stu-id="1ec9c-209">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="1ec9c-210">Operatori di incremento e decremento dei prefissiPrefix increment and decrement operators</span><span class="sxs-lookup"><span data-stu-id="1ec9c-210">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="1ec9c-211">Operatore più unario</span><span class="sxs-lookup"><span data-stu-id="1ec9c-211">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="1ec9c-212">Operatore meno unario</span><span class="sxs-lookup"><span data-stu-id="1ec9c-212">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="1ec9c-213">Operatore di moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="1ec9c-213">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="1ec9c-214">Operatore di divisione</span><span class="sxs-lookup"><span data-stu-id="1ec9c-214">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="1ec9c-215">Operatore di residuo</span><span class="sxs-lookup"><span data-stu-id="1ec9c-215">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="1ec9c-216">Operatore addizione</span><span class="sxs-lookup"><span data-stu-id="1ec9c-216">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="1ec9c-217">Operatore di sottrazione</span><span class="sxs-lookup"><span data-stu-id="1ec9c-217">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="1ec9c-218">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="1ec9c-218">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="1ec9c-219">Operatori Checked e Unchecked</span><span class="sxs-lookup"><span data-stu-id="1ec9c-219">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [<span data-ttu-id="1ec9c-220">Promozioni numeriche</span><span class="sxs-lookup"><span data-stu-id="1ec9c-220">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="1ec9c-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ec9c-221">See also</span></span>

- [<span data-ttu-id="1ec9c-222">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="1ec9c-222">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1ec9c-223">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="1ec9c-223">C# operators</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="1ec9c-224">Valori numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="1ec9c-224">Numerics in .NET</span></span>](../../../standard/numerics.md)
