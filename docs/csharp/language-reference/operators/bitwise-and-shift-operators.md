---
title: Operatori di scorrimento e bit per bit - Riferimenti per C#
description: Di seguito sono descritti gli operatori C# che eseguono operazioni di scorrimento o logiche bit per bit con operandi di tipi integrali.
ms.date: 04/18/2019
author: pkulikov
f1_keywords:
- ~_CSharpKeyword
- <<_CSharpKeyword
- '>>_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise logical operators [C#]
- shift operators [C#]
- tilde operator [C#]
- one's complement operator [C#]
- bitwise complement operator [C#]
- ~ operator [C#]
- left shift operator [C#]
- << operator [C#]
- right shift operator [C#]
- '>> operator [C#]'
- bitwise logical AND operator [C#]
- ampersand operator [C#]
- '& operator [C#]'
- bitwise logical exclusive OR operator [C#]
- bitwise logical XOR operator [C#]
- ^ operator [C#]
- bitwise logical OR operator [C#]
- '| operator [C#]'
ms.openlocfilehash: f14b92aba270eab845ca50e5407da3502b5c4087
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345336"
---
# <a name="bitwise-and-shift-operators-c-reference"></a><span data-ttu-id="8ffcc-103">Operatori di scorrimento e bit per bit (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8ffcc-103">Bitwise and shift operators (C# reference)</span></span>

<span data-ttu-id="8ffcc-104">Gli operatori seguenti eseguono operazioni di spostamento or bit per bit con operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md) o del tipo [char](../builtin-types/char.md) :</span><span class="sxs-lookup"><span data-stu-id="8ffcc-104">The following operators perform bitwise or shift operations with operands of the [integral numeric types](../builtin-types/integral-numeric-types.md) or the [char](../builtin-types/char.md) type:</span></span>

- <span data-ttu-id="8ffcc-105">Operatore unario [`~` (complemento bit per bit)](#bitwise-complement-operator-)</span><span class="sxs-lookup"><span data-stu-id="8ffcc-105">Unary [`~` (bitwise complement)](#bitwise-complement-operator-) operator</span></span>
- <span data-ttu-id="8ffcc-106">Operatori di scorrimento binari [`<<` (scorrimento a sinistra)](#left-shift-operator-) e [`>>` (scorrimento a destra)](#right-shift-operator-)</span><span class="sxs-lookup"><span data-stu-id="8ffcc-106">Binary [`<<` (left shift)](#left-shift-operator-) and [`>>` (right shift)](#right-shift-operator-) shift operators</span></span>
- <span data-ttu-id="8ffcc-107">Operatori binari [`&` (AND logico)](#logical-and-operator-), [`|` (OR logico)](#logical-or-operator-) e [`^` (OR esclusivo logico)](#logical-exclusive-or-operator-)</span><span class="sxs-lookup"><span data-stu-id="8ffcc-107">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators</span></span>

<span data-ttu-id="8ffcc-108">Questi operatori sono definiti per i tipi `int`, `uint`, `long` e `ulong`.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-108">Those operators are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="8ffcc-109">Quando entrambi gli operandi sono di altri tipi integrali (`sbyte`, `byte`, `short`, `ushort` o `char`), i relativi valori vengono convertiti nel tipo `int`, che è anche il tipo di risultato di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-109">When both operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="8ffcc-110">Quando gli operandi sono di tipi integrali diversi, i relativi valori vengono convertiti nel tipo integrale più vicino.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-110">When operands are of different integral types, their values are converted to the closest containing integral type.</span></span> <span data-ttu-id="8ffcc-111">Per altre informazioni, vedere la sezione [Promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="8ffcc-112">Gli operatori `&`, `|`e `^` sono definiti anche per gli operandi del tipo di `bool`.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-112">The `&`, `|`, and `^` operators are also defined for operands of the `bool` type.</span></span> <span data-ttu-id="8ffcc-113">Per altre informazioni, vedere [Operatori logici booleani](boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-113">For more information, see [Boolean logical operators](boolean-logical-operators.md).</span></span>

<span data-ttu-id="8ffcc-114">Le operazioni di scorrimento non causano mai overflow e producono gli stessi risultati nei contesti [Checked e Unchecked](../keywords/checked-and-unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-114">Bitwise and shift operations never cause overflow and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="bitwise-complement-operator-"></a><span data-ttu-id="8ffcc-115">Operatore di complemento bit per bit ~</span><span class="sxs-lookup"><span data-stu-id="8ffcc-115">Bitwise complement operator ~</span></span>

<span data-ttu-id="8ffcc-116">L'operatore `~` produce un complemento bit per bit del relativo operando invertendo ogni bit:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-116">The `~` operator produces a bitwise complement of its operand by reversing each bit:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

<span data-ttu-id="8ffcc-117">È anche possibile usare il simbolo `~` per dichiarare i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-117">You can also use the `~` symbol to declare finalizers.</span></span> <span data-ttu-id="8ffcc-118">Per altre informazioni, vedere [Finalizzatori](../../programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-118">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

## <a name="left-shift-operator-"></a><span data-ttu-id="8ffcc-119">Operatore di scorrimento a sinistra \<\<</span><span class="sxs-lookup"><span data-stu-id="8ffcc-119">Left-shift operator \<\<</span></span>

<span data-ttu-id="8ffcc-120">L'operatore `<<` scorre verso sinistra l'operando di sinistra del numero di bit specificato dall'operando di destra.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-120">The `<<` operator shifts its left-hand operand left by the number of bits defined by its right-hand operand.</span></span>

<span data-ttu-id="8ffcc-121">L'operazione di scorrimento a sinistra rimuove i bit più significativi che non rientrano nell'intervallo del tipo di risultato e imposta le posizioni dei bit vuoti meno significativi su zero, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-121">The left-shift operation discards the high-order bits that are outside the range of the result type and sets the low-order empty bit positions to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

<span data-ttu-id="8ffcc-122">Poiché gli operatori di scorrimento sono definiti solo per i tipi `int`, `uint`, `long` e `ulong`, il risultato di un'operazione contiene almeno 32 bit.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-122">Because the shift operators are defined only for the `int`, `uint`, `long`, and `ulong` types, the result of an operation always contains at least 32 bits.</span></span> <span data-ttu-id="8ffcc-123">Se l'operando di sinistra e di un tipo integrale diverso (`sbyte`, `byte`, `short`, `ushort` o `char`), il relativo valore viene convertito nel tipo `int`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-123">If the left-hand operand is of another integral type (`sbyte`, `byte`, `short`, `ushort`, or `char`), its value is converted to the `int` type, as the following example shows:</span></span>

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

<span data-ttu-id="8ffcc-124">Per informazioni su come l'operando di destra dell'operatore `<<` definisce il conteggio degli scorrimenti, vedere la sezione [Conteggio degli scorrimenti degli operatori di scorrimento](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-124">For information about how the right-hand operand of the `<<` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="right-shift-operator-"></a><span data-ttu-id="8ffcc-125">Operatore di scorrimento a destra >></span><span class="sxs-lookup"><span data-stu-id="8ffcc-125">Right-shift operator >></span></span>

<span data-ttu-id="8ffcc-126">L'operatore `>>` scorre l'operando di sinistra verso destra del numero di bit definito dall'operando di destra.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-126">The `>>` operator shifts its left-hand operand right by the number of bits defined by its right-hand operand.</span></span>

<span data-ttu-id="8ffcc-127">L'operazione di scorrimento a destra rimuove i bit meno significativi, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-127">The right-shift operation discards the low-order bits, as the following example shows:</span></span>

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

<span data-ttu-id="8ffcc-128">Le posizioni dei bit vuoti più significativi vengono impostate in base al tipo dell'operando di sinistra come segue:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-128">The high-order empty bit positions are set based on the type of the left-hand operand as follows:</span></span>

- <span data-ttu-id="8ffcc-129">Se l'operando sinistro è di tipo `int` o `long`, l'operatore di spostamento a destra esegue un turno *aritmetico* : il valore del bit più significativo (il bit di segno) dell'operando di sinistra viene propagato nelle posizioni di bit vuote di ordine superiore.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-129">If the left-hand operand is of type `int` or `long`, the right-shift operator performs an *arithmetic* shift: the value of the most significant bit (the sign bit) of the left-hand operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="8ffcc-130">Vale a dire, le posizioni dei bit vuoti più significativi vengono impostate su zero se l'operando di sinistra è un valore non negativo e impostate su uno se è negativo.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-130">That is, the high-order empty bit positions are set to zero if the left-hand operand is non-negative and set to one if it's negative.</span></span>

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- <span data-ttu-id="8ffcc-131">Se l'operando sinistro è di tipo `uint` o `ulong`, l'operatore di spostamento a destra esegue un spostamento *logico* : le posizioni dei bit vuote di ordine superiore sono sempre impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-131">If the left-hand operand is of type `uint` or `ulong`, the right-shift operator performs a *logical* shift: the high-order empty bit positions are always set to zero.</span></span>

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

<span data-ttu-id="8ffcc-132">Per informazioni su come l'operando di destra dell'operatore `>>` definisce il conteggio degli scorrimenti, vedere la sezione [Conteggio degli scorrimenti degli operatori di scorrimento](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-132">For information about how the right-hand operand of the `>>` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="8ffcc-133">Operatore AND logico &amp;</span><span class="sxs-lookup"><span data-stu-id="8ffcc-133">Logical AND operator &amp;</span></span>

<span data-ttu-id="8ffcc-134">L'operatore `&` calcola l'AND logico bit per bit dei relativi operandi:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-134">The `&` operator computes the bitwise logical AND of its operands:</span></span>

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

<span data-ttu-id="8ffcc-135">Per `bool` operandi, l'operatore di `&` calcola l'operatore [and logico](boolean-logical-operators.md#logical-and-operator-) degli operandi.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-135">For `bool` operands, the `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="8ffcc-136">L'operatore unario `&` è l'[operatore address-of](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-136">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="8ffcc-137">Operatore OR esclusivo logico: ^</span><span class="sxs-lookup"><span data-stu-id="8ffcc-137">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="8ffcc-138">L'operatore `^` calcola l'OR esclusivo logico bit per bit, chiamato anche XOR logico bit per bit, dei relativi operandi:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-138">The `^` operator computes the bitwise logical exclusive OR, also known as the bitwise logical XOR, of its operands:</span></span>

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

<span data-ttu-id="8ffcc-139">Per `bool` operandi, l'operatore di `^` calcola l' [OR esclusivo logico](boolean-logical-operators.md#logical-exclusive-or-operator-) degli operandi.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-139">For `bool` operands, the `^` operator computes the [logical exclusive OR](boolean-logical-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="8ffcc-140">Operatore OR logico |</span><span class="sxs-lookup"><span data-stu-id="8ffcc-140">Logical OR operator |</span></span>

<span data-ttu-id="8ffcc-141">L'operatore `|` calcola l'OR logico bit per bit dei relativi operandi:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-141">The `|` operator computes the bitwise logical OR of its operands:</span></span>

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

<span data-ttu-id="8ffcc-142">Per `bool` operandi, l'operatore `|` calcola l' [OR logico](boolean-logical-operators.md#logical-or-operator-) degli operandi.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-142">For `bool` operands, the `|` operator computes the [logical OR](boolean-logical-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="8ffcc-143">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="8ffcc-143">Compound assignment</span></span>

<span data-ttu-id="8ffcc-144">Per un operatore binario `op`, un'espressione di assegnazione composta in formato</span><span class="sxs-lookup"><span data-stu-id="8ffcc-144">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="8ffcc-145">equivale a</span><span class="sxs-lookup"><span data-stu-id="8ffcc-145">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="8ffcc-146">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-146">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="8ffcc-147">L'esempio seguente illustra l'uso dell'assegnazione composta con gli operatori di scorrimento e bit per bit:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-147">The following example demonstrates the usage of compound assignment with bitwise and shift operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

<span data-ttu-id="8ffcc-148">A causa delle [promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions) il risultato dell'operazione `op` potrebbe non essere convertibile in modo implicito nel tipo `T` di `x`.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-148">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="8ffcc-149">In questo caso, se `op` è un operatore già definito e il risultato dell'operazione è convertibile in modo esplicito nel tipo `T` di `x`, un'espressione di assegnazione composta nel formato `x op= y` equivale a `x = (T)(x op y)`, con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-149">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="8ffcc-150">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-150">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a><span data-ttu-id="8ffcc-151">Precedenza tra gli operatori</span><span class="sxs-lookup"><span data-stu-id="8ffcc-151">Operator precedence</span></span>

<span data-ttu-id="8ffcc-152">Nell'elenco seguente gli operatori di scorrimento e bit per bit sono ordinati dalla precedenza più elevata a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-152">The following list orders bitwise and shift operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="8ffcc-153">Operatore di complemento bit per bit `~`</span><span class="sxs-lookup"><span data-stu-id="8ffcc-153">Bitwise complement operator `~`</span></span>
- <span data-ttu-id="8ffcc-154">Operatori di scorrimento `<<` e `>>`</span><span class="sxs-lookup"><span data-stu-id="8ffcc-154">Shift operators `<<` and `>>`</span></span>
- <span data-ttu-id="8ffcc-155">Operatore AND logico `&`</span><span class="sxs-lookup"><span data-stu-id="8ffcc-155">Logical AND operator `&`</span></span>
- <span data-ttu-id="8ffcc-156">Operatore OR esclusivo logico `^`</span><span class="sxs-lookup"><span data-stu-id="8ffcc-156">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="8ffcc-157">Operatore OR logico `|`</span><span class="sxs-lookup"><span data-stu-id="8ffcc-157">Logical OR operator `|`</span></span>

<span data-ttu-id="8ffcc-158">Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-158">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

<span data-ttu-id="8ffcc-159">Per l'elenco completo degli C# operatori ordinati in base al livello di precedenza, vedere la sezione [precedenza](index.md#operator-precedence) degli [ C# operatori](index.md) dell'articolo operatori.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-159">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="shift-count-of-the-shift-operators"></a><span data-ttu-id="8ffcc-160">Conteggio degli scorrimenti degli operatori di scorrimento</span><span class="sxs-lookup"><span data-stu-id="8ffcc-160">Shift count of the shift operators</span></span>

<span data-ttu-id="8ffcc-161">Per gli operatori shift `<<` e `>>`, il tipo dell'operando destro deve essere `int` o un tipo con una [conversione numerica implicita predefinita](../builtin-types/numeric-conversions.md#implicit-numeric-conversions) in `int`.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-161">For the shift operators `<<` and `>>`, the type of the right-hand operand must be `int` or a type that has a [predefined implicit numeric conversion](../builtin-types/numeric-conversions.md#implicit-numeric-conversions) to `int`.</span></span>

<span data-ttu-id="8ffcc-162">Per le espressioni `x << count` e `x >> count`, il conteggio effettivo degli scorrimenti varia a seconda del tipo di `x` come segue:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-162">For the `x << count` and `x >> count` expressions, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="8ffcc-163">Se il tipo di `x` è `int` o `uint`, il conteggio dello spostamento viene definito dai *cinque* bit di ordine inferiore dell'operando destro.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-163">If the type of `x` is `int` or `uint`, the shift count is defined by the low-order *five* bits of the right-hand operand.</span></span> <span data-ttu-id="8ffcc-164">Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x1F` (o `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-164">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="8ffcc-165">Se il tipo di `x` è `long` o `ulong`, il conteggio dello spostamento viene definito dai *sei* bit di ordine inferiore dell'operando destro.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-165">If the type of `x` is `long` or `ulong`, the shift count is defined by the low-order *six* bits of the right-hand operand.</span></span> <span data-ttu-id="8ffcc-166">Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x3F` (o `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-166">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="8ffcc-167">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="8ffcc-167">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

## <a name="enumeration-logical-operators"></a><span data-ttu-id="8ffcc-168">Operatori logici di enumerazione</span><span class="sxs-lookup"><span data-stu-id="8ffcc-168">Enumeration logical operators</span></span>

<span data-ttu-id="8ffcc-169">Gli operatori `~`, `&`, `|`e `^` sono supportati anche da qualsiasi tipo di [enumerazione](../builtin-types/enum.md) .</span><span class="sxs-lookup"><span data-stu-id="8ffcc-169">The `~`, `&`, `|`, and `^` operators are also supported by any [enumeration](../builtin-types/enum.md) type.</span></span> <span data-ttu-id="8ffcc-170">Per gli operandi dello stesso tipo di enumerazione, viene eseguita un'operazione logica sui valori corrispondenti del tipo integrale sottostante.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-170">For operands of the same enumeration type, a logical operation is performed on the corresponding values of the underlying integral type.</span></span> <span data-ttu-id="8ffcc-171">Ad esempio, per qualsiasi `x` e `y` di un tipo di enumerazione `T` con un tipo sottostante `U`, l'espressione `x & y` produce lo stesso risultato dell'espressione `(T)((U)x & (U)y)`.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-171">For example, for any `x` and `y` of an enumeration type `T` with an underlying type `U`, the `x & y` expression produces the same result as the `(T)((U)x & (U)y)` expression.</span></span>

<span data-ttu-id="8ffcc-172">Gli operatori logici bit per bit vengono in genere usati con un tipo di enumerazione definito con l'attributo [Flags](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-172">You typically use bitwise logical operators with an enumeration type which is defined with the [Flags](xref:System.FlagsAttribute) attribute.</span></span> <span data-ttu-id="8ffcc-173">Per altre informazioni, vedere la sezione [Tipi di enumerazione come flag di bit](../builtin-types/enum.md#enumeration-types-as-bit-flags) dell'articolo [Tipi di enumerazione](../builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="8ffcc-173">For more information, see the [Enumeration types as bit flags](../builtin-types/enum.md#enumeration-types-as-bit-flags) section of the [Enumeration types](../builtin-types/enum.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="8ffcc-174">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="8ffcc-174">Operator overloadability</span></span>

<span data-ttu-id="8ffcc-175">Un tipo definito dall'utente può eseguire l'[overload](operator-overloading.md) degli operatori `~`, `<<`, `>>`, `&`, `|` e `^`.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-175">A user-defined type can [overload](operator-overloading.md) the `~`, `<<`, `>>`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="8ffcc-176">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione composta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-176">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="8ffcc-177">Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-177">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="8ffcc-178">Se un tipo definito dall'utente `T` esegue l'overload dell'operatore `<<` o `>>`, il tipo dell'operando di sinistra deve essere `T` e il tipo dell'operando di destra deve essere `int`.</span><span class="sxs-lookup"><span data-stu-id="8ffcc-178">If a user-defined type `T` overloads the `<<` or `>>` operator, the type of the left-hand operand must be `T` and the type of the right-hand operand must be `int`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8ffcc-179">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8ffcc-179">C# language specification</span></span>

<span data-ttu-id="8ffcc-180">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="8ffcc-180">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="8ffcc-181">Operatore di complemento bit per bit</span><span class="sxs-lookup"><span data-stu-id="8ffcc-181">Bitwise complement operator</span></span>](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [<span data-ttu-id="8ffcc-182">Operatori shift</span><span class="sxs-lookup"><span data-stu-id="8ffcc-182">Shift operators</span></span>](~/_csharplang/spec/expressions.md#shift-operators)
- [<span data-ttu-id="8ffcc-183">Operatori logici</span><span class="sxs-lookup"><span data-stu-id="8ffcc-183">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="8ffcc-184">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="8ffcc-184">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="8ffcc-185">Promozioni numeriche</span><span class="sxs-lookup"><span data-stu-id="8ffcc-185">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="8ffcc-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ffcc-186">See also</span></span>

- [<span data-ttu-id="8ffcc-187">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8ffcc-187">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8ffcc-188">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8ffcc-188">C# operators</span></span>](index.md)
- [<span data-ttu-id="8ffcc-189">Operatori logici booleani</span><span class="sxs-lookup"><span data-stu-id="8ffcc-189">Boolean logical operators</span></span>](boolean-logical-operators.md)
