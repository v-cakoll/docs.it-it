---
title: Operatori aritmetici - Riferimenti per C#
description: Informazioni sugli operatori C# che eseguono operazioni di moltiplicazione, divisione, resto, addizione e sottrazione con i tipi numerici.
ms.date: 05/11/2020
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
ms.openlocfilehash: d004ab466bc053ed286d85bcbee2766d8a087286
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207235"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="d1cd3-103">Operatori aritmetici (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d1cd3-103">Arithmetic operators (C# reference)</span></span>

<span data-ttu-id="d1cd3-104">Gli operatori seguenti eseguono operazioni aritmetiche con operandi di tipi numerici:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-104">The following operators perform arithmetic operations with operands of numeric types:</span></span>

- <span data-ttu-id="d1cd3-105">Operatori unari [ `++` (Increment)](#increment-operator-), [ `--` (Decrement)](#decrement-operator---), [ `+` (Plus)](#unary-plus-and-minus-operators)e [ `-` (meno)](#unary-plus-and-minus-operators)</span><span class="sxs-lookup"><span data-stu-id="d1cd3-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators</span></span>
- <span data-ttu-id="d1cd3-106">Operatori binari [ `*` (moltiplicazione)](#multiplication-operator-), [ `/` (divisione)](#division-operator-), [ `%` (resto)](#remainder-operator-), [ `+` (addizione)](#addition-operator-)e [ `-` (sottrazione)](#subtraction-operator--)</span><span class="sxs-lookup"><span data-stu-id="d1cd3-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators</span></span>

<span data-ttu-id="d1cd3-107">Questi operatori sono supportati da tutti i tipi numerici [integrali](../builtin-types/integral-numeric-types.md) e a [virgola mobile](../builtin-types/floating-point-numeric-types.md) .</span><span class="sxs-lookup"><span data-stu-id="d1cd3-107">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

<span data-ttu-id="d1cd3-108">Nel caso dei tipi integrali, gli operatori (ad eccezione degli `++` `--` operatori e) vengono definiti per i `int` `uint` tipi,, `long` e `ulong` .</span><span class="sxs-lookup"><span data-stu-id="d1cd3-108">In the case of integral types, those operators (except the `++` and `--` operators) are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="d1cd3-109">Quando gli operandi sono di altri tipi integrali ( `sbyte` , `byte` , `short` , `ushort` o `char` ), i relativi valori vengono convertiti nel `int` tipo, che è anche il tipo di risultato di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-109">When operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="d1cd3-110">Quando gli operandi sono di tipi integrali o a virgola mobile diversi, i relativi valori vengono convertiti nel tipo contenitore più vicino, se tale tipo esiste.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-110">When operands are of different integral or floating-point types, their values are converted to the closest containing type, if such a type exists.</span></span> <span data-ttu-id="d1cd3-111">Per altre informazioni, vedere la sezione [Promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d1cd3-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span> <span data-ttu-id="d1cd3-112">Gli `++` `--` operatori e sono definiti per tutti i tipi numerici integrali e a virgola mobile e il tipo [char](../builtin-types/char.md) .</span><span class="sxs-lookup"><span data-stu-id="d1cd3-112">The `++` and `--` operators are defined for all integral and floating-point numeric types and the [char](../builtin-types/char.md) type.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="d1cd3-113">Operatore di incremento ++</span><span class="sxs-lookup"><span data-stu-id="d1cd3-113">Increment operator ++</span></span>

<span data-ttu-id="d1cd3-114">L'operatore di incremento unario `++` incrementa il suo operando di 1.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-114">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="d1cd3-115">L'operando deve essere una variabile, un accesso a una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un accesso a un [indicizzatore](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1cd3-115">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="d1cd3-116">L'operatore di incremento è supportato in due forme: l'operatore di incremento suffisso, `x++`, e l'operatore di incremento prefisso, `++x`.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-116">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="d1cd3-117">Operatore di incremento suffisso</span><span class="sxs-lookup"><span data-stu-id="d1cd3-117">Postfix increment operator</span></span>

<span data-ttu-id="d1cd3-118">Il risultato di `x++` è il valore di `x` *prima* dell'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-118">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](snippets/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="d1cd3-119">Operatore di incremento prefisso</span><span class="sxs-lookup"><span data-stu-id="d1cd3-119">Prefix increment operator</span></span>

<span data-ttu-id="d1cd3-120">Il risultato di `++x` è il valore di `x` *dopo* l'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-120">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](snippets/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="d1cd3-121">Operatore di decremento --</span><span class="sxs-lookup"><span data-stu-id="d1cd3-121">Decrement operator --</span></span>

<span data-ttu-id="d1cd3-122">L'operatore di decremento unario `--` decrementa il proprio operando di 1.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-122">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="d1cd3-123">L'operando deve essere una variabile, un accesso a una [proprietà](../../programming-guide/classes-and-structs/properties.md) o un accesso a un [indicizzatore](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1cd3-123">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="d1cd3-124">L'operatore di decremento è supportato in due forme: l'operatore di decremento suffisso, `x--`, e l'operatore di decremento prefisso, `--x`.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-124">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="d1cd3-125">Operatore di decremento suffisso</span><span class="sxs-lookup"><span data-stu-id="d1cd3-125">Postfix decrement operator</span></span>

<span data-ttu-id="d1cd3-126">Il risultato di `x--` è il valore di `x` *prima* dell'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-126">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](snippets/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="d1cd3-127">Operatore di decremento prefisso</span><span class="sxs-lookup"><span data-stu-id="d1cd3-127">Prefix decrement operator</span></span>

<span data-ttu-id="d1cd3-128">Il risultato di `--x` è il valore di `x` *dopo* l'operazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-128">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](snippets/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="d1cd3-129">Operatori più e meno unari</span><span class="sxs-lookup"><span data-stu-id="d1cd3-129">Unary plus and minus operators</span></span>

<span data-ttu-id="d1cd3-130">L'operatore `+` unario restituisce il valore del proprio operando.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-130">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="d1cd3-131">L'operatore `-` unario calcola la negazione numerica del proprio operando.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-131">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](snippets/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="d1cd3-132">Il tipo [ULONG](../builtin-types/integral-numeric-types.md) non supporta l'operatore unario `-` .</span><span class="sxs-lookup"><span data-stu-id="d1cd3-132">The [ulong](../builtin-types/integral-numeric-types.md) type doesn't support the unary `-` operator.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="d1cd3-133">Operatore di moltiplicazione \*</span><span class="sxs-lookup"><span data-stu-id="d1cd3-133">Multiplication operator \*</span></span>

<span data-ttu-id="d1cd3-134">L'operatore di moltiplicazione `*` calcola il prodotto degli operandi:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-134">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](snippets/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="d1cd3-135">L'operatore `*` unario è l'[operatore di riferimento indiretto a puntatore](pointer-related-operators.md#pointer-indirection-operator-).</span><span class="sxs-lookup"><span data-stu-id="d1cd3-135">The unary `*` operator is the [pointer indirection operator](pointer-related-operators.md#pointer-indirection-operator-).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="d1cd3-136">Operatore di divisione /</span><span class="sxs-lookup"><span data-stu-id="d1cd3-136">Division operator /</span></span>

<span data-ttu-id="d1cd3-137">L'operatore di divisione `/` divide l'operando di sinistra per l'operando di destra.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-137">The division operator `/` divides its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="d1cd3-138">Divisione di interi</span><span class="sxs-lookup"><span data-stu-id="d1cd3-138">Integer division</span></span>

<span data-ttu-id="d1cd3-139">Per gli operandi di tipo Integer, il risultato dell'operatore `/` è di tipo Integer ed è uguale al quoziente dei due operandi arrotondato allo zero:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-139">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](snippets/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="d1cd3-140">Per ottenere il quoziente dei due operandi come numero a virgola mobile, usare il tipo `float`, `double`,o `decimal`:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-140">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](snippets/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="d1cd3-141">Divisione a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="d1cd3-141">Floating-point division</span></span>

<span data-ttu-id="d1cd3-142">Per i tipi `float`, `double` e `decimal`, il risultato dell'operatore `/` è il quoziente dei due operandi:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-142">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](snippets/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="d1cd3-143">Se uno degli operandi è `decimal`, un altro operando non può essere né `float` né `double`, perché né `float` né `double` è convertibile implicitamente in `decimal`.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-143">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="d1cd3-144">È necessario convertire esplicitamente l'operando `float` o `double` nel tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-144">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="d1cd3-145">Per ulteriori informazioni sulle conversioni tra tipi numerici, vedere [conversioni numeriche predefinite](../builtin-types/numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="d1cd3-145">For more information about conversions between numeric types, see [Built-in numeric conversions](../builtin-types/numeric-conversions.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="d1cd3-146">Operatore di resto %</span><span class="sxs-lookup"><span data-stu-id="d1cd3-146">Remainder operator %</span></span>

<span data-ttu-id="d1cd3-147">L'operatore di resto `%` calcola il resto dopo aver diviso l'operando di sinistra per l'operando di destra.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-147">The remainder operator `%` computes the remainder after dividing its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="d1cd3-148">Resto intero</span><span class="sxs-lookup"><span data-stu-id="d1cd3-148">Integer remainder</span></span>

<span data-ttu-id="d1cd3-149">Per gli operandi di tipi interi, il risultato di `a % b` è il valore prodotto da `a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-149">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="d1cd3-150">Il segno del resto diverso da zero è uguale a quello dell'operando di sinistra, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-150">The sign of the non-zero remainder is the same as that of the left-hand operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](snippets/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="d1cd3-151">Usare il metodo <xref:System.Math.DivRem%2A?displayProperty=nameWithType> per calcolare sia la divisione di numeri interi, sia i risultati del resto.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-151">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="d1cd3-152">Resto a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="d1cd3-152">Floating-point remainder</span></span>

<span data-ttu-id="d1cd3-153">Per gli operandi `float` e `double`, il risultato di `x % y` per `x` e `y` finiti è il valore `z` tale che</span><span class="sxs-lookup"><span data-stu-id="d1cd3-153">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="d1cd3-154">Il segno di `z`, se diverso da zero, è uguale a quello di `x`.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-154">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="d1cd3-155">Il valore assoluto di `z` è il valore prodotto da `|x| - n * |y|` in cui `n` è l'intero più grande possibile, che è minore o uguale a `|x| / |y|` e `|x|` e `|y|` sono i valori assoluti di `x` e `y`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-155">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="d1cd3-156">Questo metodo di calcolo del resto è analogo a quello usato per gli operandi Integer, ma diverso dalla specifica IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-156">This method of computing the remainder is analogous to that used for integer operands, but different from the IEEE 754 specification.</span></span> <span data-ttu-id="d1cd3-157">Se è necessaria l'operazione di resto conforme alla specifica IEEE 754, usare il <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-157">If you need the remainder operation that complies with the IEEE 754 specification, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="d1cd3-158">Per informazioni sul comportamento dell'operatore `%` in caso di operandi non finiti, vedere la sezione [Operatore di resto](~/_csharplang/spec/expressions.md#remainder-operator) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d1cd3-158">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="d1cd3-159">Per gli operandi `decimal`, l'operatore di resto `%` equivale all'[operatore di resto](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) di tipo <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-159">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="d1cd3-160">L'esempio seguente illustra il comportamento dell'operatore di resto con operandi a virgola mobile:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-160">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](snippets/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="d1cd3-161">Operatore di addizione +</span><span class="sxs-lookup"><span data-stu-id="d1cd3-161">Addition operator +</span></span>

<span data-ttu-id="d1cd3-162">L'operatore di addizione `+` calcola la somma degli operandi:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-162">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](snippets/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="d1cd3-163">È anche possibile usare l' `+` operatore per la concatenazione di stringhe e la combinazione di delegati.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-163">You can also use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="d1cd3-164">Per ulteriori informazioni, vedere l'articolo [ `+` `+=` operatori e](addition-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="d1cd3-164">For more information, see the [`+` and `+=` operators](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="d1cd3-165">Operatore di sottrazione -</span><span class="sxs-lookup"><span data-stu-id="d1cd3-165">Subtraction operator -</span></span>

<span data-ttu-id="d1cd3-166">L'operatore di sottrazione `-` sottrae l'operando di destra dall'operando di sinistra:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-166">The subtraction operator `-` subtracts its right-hand operand from its left-hand operand:</span></span>

[!code-csharp-interactive[subtraction operator](snippets/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="d1cd3-167">È anche possibile usare l' `-` operatore per la rimozione dei delegati.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-167">You can also use the `-` operator for delegate removal.</span></span> <span data-ttu-id="d1cd3-168">Per ulteriori informazioni, vedere l'articolo [ `-` `-=` operatori e](subtraction-operator.md) .</span><span class="sxs-lookup"><span data-stu-id="d1cd3-168">For more information, see the [`-` and `-=` operators](subtraction-operator.md) article.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="d1cd3-169">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="d1cd3-169">Compound assignment</span></span>

<span data-ttu-id="d1cd3-170">Per un operatore binario `op`, un'espressione di assegnazione composta in formato</span><span class="sxs-lookup"><span data-stu-id="d1cd3-170">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="d1cd3-171">equivale a</span><span class="sxs-lookup"><span data-stu-id="d1cd3-171">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="d1cd3-172">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-172">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="d1cd3-173">L'esempio seguente illustra l'uso dell'assegnazione composta con gli operatori aritmetici:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-173">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](snippets/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="d1cd3-174">A causa delle [promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions) il risultato dell'operazione `op` potrebbe non essere convertibile in modo implicito nel tipo `T` di `x`.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-174">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="d1cd3-175">In questo caso, se `op` è un operatore già definito e il risultato dell'operazione è convertibile in modo esplicito nel tipo `T` di `x`, un'espressione di assegnazione composta nel formato `x op= y` equivale a `x = (T)(x op y)`, con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-175">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="d1cd3-176">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-176">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](snippets/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

<span data-ttu-id="d1cd3-177">È anche possibile usare `+=` gli `-=` operatori e per sottoscrivere e annullare la sottoscrizione di un [evento](../keywords/event.md), rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-177">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from an [event](../keywords/event.md), respectively.</span></span> <span data-ttu-id="d1cd3-178">Per ulteriori informazioni, vedere [come sottoscrivere e annullare la sottoscrizione di eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="d1cd3-178">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="d1cd3-179">Precedenza e associatività degli operatori</span><span class="sxs-lookup"><span data-stu-id="d1cd3-179">Operator precedence and associativity</span></span>

<span data-ttu-id="d1cd3-180">Nell'elenco seguente gli operatori aritmetici sono ordinati dalla precedenza più elevata a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-180">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="d1cd3-181">Operatori di incremento `x++` e decremento `x--` in forma suffissa</span><span class="sxs-lookup"><span data-stu-id="d1cd3-181">Postfix increment `x++` and decrement `x--` operators</span></span>
- <span data-ttu-id="d1cd3-182">Operatori di incremento `++x` e decremento `--x` e unari `+` e `-`</span><span class="sxs-lookup"><span data-stu-id="d1cd3-182">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators</span></span>
- <span data-ttu-id="d1cd3-183">Operatori moltiplicativi `*`, `/` e `%`</span><span class="sxs-lookup"><span data-stu-id="d1cd3-183">Multiplicative `*`, `/`, and `%` operators</span></span>
- <span data-ttu-id="d1cd3-184">Operatori di addizione `+` e `-`</span><span class="sxs-lookup"><span data-stu-id="d1cd3-184">Additive `+` and `-` operators</span></span>

<span data-ttu-id="d1cd3-185">Gli operatori aritmetici binari prevedono l'associazione all'operando sinistro.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-185">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="d1cd3-186">Ciò significa che gli operatori con lo stesso livello di precedenza vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-186">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="d1cd3-187">Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza e dall'associatività degli operatori.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-187">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](snippets/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="d1cd3-188">Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere la sezione [precedenza](index.md#operator-precedence) degli operatori dell'articolo [operatori c#](index.md) .</span><span class="sxs-lookup"><span data-stu-id="d1cd3-188">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="d1cd3-189">Overflow aritmetico e divisione per zero</span><span class="sxs-lookup"><span data-stu-id="d1cd3-189">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="d1cd3-190">Quando il risultato di un'operazione aritmetica non rientra nell'intervallo di valori finiti possibili del tipo numerico interessato, il comportamento di un operatore aritmetico dipende dal tipo dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-190">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="d1cd3-191">Overflow aritmetico di numeri interi</span><span class="sxs-lookup"><span data-stu-id="d1cd3-191">Integer arithmetic overflow</span></span>

<span data-ttu-id="d1cd3-192">La divisione di interi per zero genera sempre un'eccezione <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-192">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="d1cd3-193">In caso di overflow aritmetico di interi, un contesto di verifica overflow, che può essere [verificato o non verificato](../keywords/checked-and-unchecked.md), controlla il comportamento risultante:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-193">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="d1cd3-194">In un contesto verificato, se l'overflow si verifica in un'espressione costante, verrà restituito un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-194">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="d1cd3-195">Quando invece l'operazione avviene in fase di esecuzione, viene generata una <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-195">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="d1cd3-196">In un contesto non verificato, il risultato viene troncato tramite la rimozione dei bit più significativi che non rientrano nel tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-196">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="d1cd3-197">Oltre alle istruzioni [checked e unchecked](../keywords/checked-and-unchecked.md), è possibile usare gli operatori `checked` e `unchecked` per controllare il contesto di verifica overflow in cui viene valutata un'espressione:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-197">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](snippets/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="d1cd3-198">Per impostazione predefinita, le operazioni aritmetiche vengono eseguite in un contesto *non verificato*.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-198">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="d1cd3-199">Overflow aritmetico di numeri a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="d1cd3-199">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="d1cd3-200">Le operazioni aritmetiche con i tipi `float` e `double` non generano mai un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-200">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="d1cd3-201">Il risultato delle operazioni aritmetiche con questi tipi può essere uno dei valori speciali che rappresentano un numero infinito e non un numero:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-201">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](snippets/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="d1cd3-202">Per gli operandi di tipo `decimal`, l'overflow aritmetico genera sempre una <xref:System.OverflowException> e la divisione per zero genera sempre una <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-202">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="d1cd3-203">Errori di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="d1cd3-203">Round-off errors</span></span>

<span data-ttu-id="d1cd3-204">A causa delle limitazioni generali della rappresentazione a virgola mobile dei numeri reali e dell'aritmetica a virgola mobile, è possibile che si verifichino errori di arrotondamento nei calcoli con tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-204">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="d1cd3-205">Ossia, il risultato prodotto di un'espressione può essere diverso dal risultato matematico previsto.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-205">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="d1cd3-206">L'esempio seguente illustra molti di questi casi:</span><span class="sxs-lookup"><span data-stu-id="d1cd3-206">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](snippets/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="d1cd3-207">Per ulteriori informazioni, vedere la sezione osservazioni nelle pagine di riferimento [System. Double](/dotnet/api/system.double#remarks), [System. Single](/dotnet/api/system.single#remarks)o [System. Decimal](/dotnet/api/system.decimal#remarks) .</span><span class="sxs-lookup"><span data-stu-id="d1cd3-207">For more information, see remarks at the [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d1cd3-208">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="d1cd3-208">Operator overloadability</span></span>

<span data-ttu-id="d1cd3-209">Un tipo definito dall'utente può eseguire l' [Overload](operator-overloading.md) degli `++` operatori aritmetici unari (,, `--` `+` e `-` ) e binari ( `*` ,, `/` `%` , `+` e `-` ).</span><span class="sxs-lookup"><span data-stu-id="d1cd3-209">A user-defined type can [overload](operator-overloading.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="d1cd3-210">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione composta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-210">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="d1cd3-211">Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="d1cd3-211">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d1cd3-212">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d1cd3-212">C# language specification</span></span>

<span data-ttu-id="d1cd3-213">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="d1cd3-213">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="d1cd3-214">Operatori di incremento e decremento suffisso</span><span class="sxs-lookup"><span data-stu-id="d1cd3-214">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="d1cd3-215">Operatori di incremento e decremento in forma prefissa</span><span class="sxs-lookup"><span data-stu-id="d1cd3-215">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="d1cd3-216">Operatore più unario</span><span class="sxs-lookup"><span data-stu-id="d1cd3-216">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="d1cd3-217">Operatore meno unario</span><span class="sxs-lookup"><span data-stu-id="d1cd3-217">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="d1cd3-218">Operatore di moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="d1cd3-218">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="d1cd3-219">Operatore di divisione</span><span class="sxs-lookup"><span data-stu-id="d1cd3-219">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="d1cd3-220">Operatore resto</span><span class="sxs-lookup"><span data-stu-id="d1cd3-220">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="d1cd3-221">Operatore addizione</span><span class="sxs-lookup"><span data-stu-id="d1cd3-221">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="d1cd3-222">Operatore di sottrazione</span><span class="sxs-lookup"><span data-stu-id="d1cd3-222">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="d1cd3-223">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="d1cd3-223">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="d1cd3-224">Operatori Checked e Unchecked</span><span class="sxs-lookup"><span data-stu-id="d1cd3-224">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [<span data-ttu-id="d1cd3-225">Promozioni numeriche</span><span class="sxs-lookup"><span data-stu-id="d1cd3-225">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="d1cd3-226">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1cd3-226">See also</span></span>

- [<span data-ttu-id="d1cd3-227">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="d1cd3-227">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d1cd3-228">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="d1cd3-228">C# operators</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="d1cd3-229">Valori numerici in .NET</span><span class="sxs-lookup"><span data-stu-id="d1cd3-229">Numerics in .NET</span></span>](../../../standard/numerics.md)
