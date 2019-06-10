---
title: Operatori di scorrimento e bit per bit - Riferimento C#
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
ms.openlocfilehash: bf42a53a89676f457d3d2df8d193a83299c3e4cc
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758366"
---
# <a name="bitwise-and-shift-operators-c-reference"></a><span data-ttu-id="0b8d1-103">Operatori di scorrimento e bit per bit (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="0b8d1-103">Bitwise and shift operators (C# Reference)</span></span>

<span data-ttu-id="0b8d1-104">Gli operatori seguenti eseguono operazioni di scorrimento o bit per bit con operandi di [tipi integrali](../keywords/integral-types-table.md):</span><span class="sxs-lookup"><span data-stu-id="0b8d1-104">The following operators perform bitwise or shift operations with operands of the [integral types](../keywords/integral-types-table.md):</span></span>

- <span data-ttu-id="0b8d1-105">Operatore unario [`~` (complemento bit per bit)](#bitwise-complement-operator-)</span><span class="sxs-lookup"><span data-stu-id="0b8d1-105">Unary [`~` (bitwise complement)](#bitwise-complement-operator-) operator</span></span>
- <span data-ttu-id="0b8d1-106">Operatori di scorrimento binari [`<<` (scorrimento a sinistra)](#left-shift-operator-) e [`>>` (scorrimento a destra)](#right-shift-operator-)</span><span class="sxs-lookup"><span data-stu-id="0b8d1-106">Binary [`<<` (left shift)](#left-shift-operator-) and [`>>` (right shift)](#right-shift-operator-) shift operators</span></span>
- <span data-ttu-id="0b8d1-107">Operatori binari [`&` (AND logico)](#logical-and-operator-), [`|` (OR logico)](#logical-or-operator-) e [`^` (OR esclusivo logico)](#logical-exclusive-or-operator-)</span><span class="sxs-lookup"><span data-stu-id="0b8d1-107">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators</span></span>

<span data-ttu-id="0b8d1-108">Questi operatori sono definiti per i tipi `int`, `uint`, `long` e `ulong`.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-108">Those operators are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="0b8d1-109">Quando entrambi gli operandi sono di altri tipi integrali (`sbyte`, `byte`, `short`, `ushort` o `char`), i relativi valori vengono convertiti nel tipo `int`, che è anche il tipo di risultato di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-109">When both operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="0b8d1-110">Quando gli operandi sono di tipi integrali diversi, i relativi valori vengono convertiti nel tipo integrale più vicino.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-110">When operands are of different integral types, their values are converted to the closest containing integral type.</span></span> <span data-ttu-id="0b8d1-111">Per altre informazioni, vedere la sezione [Promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="0b8d1-112">Gli operatori `&`, `|` e `^` sono definiti anche per gli operandi di tipo `bool`.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-112">The `&`, `|`, and `^` operators are also defined for the operands of the `bool` type.</span></span> <span data-ttu-id="0b8d1-113">Per altre informazioni, vedere [Operatori logici booleani](boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-113">For more information, see [Boolean logical operators](boolean-logical-operators.md).</span></span>

<span data-ttu-id="0b8d1-114">Le operazioni di scorrimento non causano mai overflow e producono gli stessi risultati nei contesti [Checked e Unchecked](../keywords/checked-and-unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-114">Bitwise and shift operations never cause overflow and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="bitwise-complement-operator-"></a><span data-ttu-id="0b8d1-115">Operatore di complemento bit per bit ~</span><span class="sxs-lookup"><span data-stu-id="0b8d1-115">Bitwise complement operator ~</span></span>

<span data-ttu-id="0b8d1-116">L'operatore `~` produce un complemento bit per bit del relativo operando invertendo ogni bit:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-116">The `~` operator produces a bitwise complement of its operand by reversing each bit:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

<span data-ttu-id="0b8d1-117">È anche possibile usare il simbolo `~` per dichiarare i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-117">You can also use the `~` symbol to declare finalizers.</span></span> <span data-ttu-id="0b8d1-118">Per altre informazioni, vedere [Finalizzatori](../../programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-118">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

## <a name="left-shift-operator-"></a><span data-ttu-id="0b8d1-119">Operatore di scorrimento a sinistra \<\<</span><span class="sxs-lookup"><span data-stu-id="0b8d1-119">Left-shift operator \<\<</span></span>

<span data-ttu-id="0b8d1-120">L'operatore `<<` scorre verso sinistra il primo operando del numero di bit specificato dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-120">The `<<` operator shifts its first operand left by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="0b8d1-121">L'operazione di scorrimento a sinistra rimuove i bit più significativi che non rientrano nell'intervallo del tipo di risultato e imposta le posizioni dei bit vuoti meno significativi su zero, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-121">The left-shift operation discards the high-order bits that are outside the range of the result type and sets the low-order empty bit positions to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

<span data-ttu-id="0b8d1-122">Poiché gli operatori di scorrimento sono definiti solo per i tipi `int`, `uint`, `long` e `ulong`, il risultato di un'operazione contiene almeno 32 bit.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-122">Because the shift operators are defined only for the `int`, `uint`, `long`, and `ulong` types, the result of an operation always contains at least 32 bits.</span></span> <span data-ttu-id="0b8d1-123">Se il primo operando e di un tipo integrale diverso (`sbyte`, `byte`, `short`, `ushort` o `char`), il relativo valore viene convertito nel tipo `int`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-123">If the first operand is of another integral type (`sbyte`, `byte`, `short`, `ushort`, or `char`), its value is converted to the `int` type, as the following example shows:</span></span>

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

<span data-ttu-id="0b8d1-124">Per informazioni su come il secondo operando dell'operatore `<<` definisce il conteggio degli scorrimenti, vedere la sezione [Conteggio degli scorrimenti degli operatori di scorrimento](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-124">For information about how the second operand of the `<<` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="right-shift-operator-"></a><span data-ttu-id="0b8d1-125">Operatore di scorrimento a destra >></span><span class="sxs-lookup"><span data-stu-id="0b8d1-125">Right-shift operator >></span></span>

<span data-ttu-id="0b8d1-126">L'operatore `>>` scorre il primo operando verso destra del numero di bit definito dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-126">The `>>` operator shifts its first operand right by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="0b8d1-127">L'operazione di scorrimento a destra rimuove i bit meno significativi, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-127">The right-shift operation discards the low-order bits, as the following example shows:</span></span>

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

<span data-ttu-id="0b8d1-128">Le posizioni dei bit vuoti più significativi vengono impostate in base al tipo del primo operando come segue:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-128">The high-order empty bit positions are set based on the type of the first operand as follows:</span></span>

- <span data-ttu-id="0b8d1-129">Se il primo operando è di tipo [int](../keywords/int.md) oppure [long](../keywords/long.md), l'operatore di scorrimento a destra esegue uno scorrimento *aritmetico*: il valore del bit più significativo (il bit di segno) del primo operando viene propagato alle posizioni dei bit vuoti più significativi.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-129">If the first operand is of type [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift operator performs an *arithmetic* shift: the value of the most significant bit (the sign bit) of the first operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="0b8d1-130">Vale a dire, le posizioni dei bit vuoti più significativi vengono impostate su zero se il primo operando è un valore non negativo e impostate su uno se è negativo.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-130">That is, the high-order empty bit positions are set to zero if the first operand is non-negative and set to one if it's negative.</span></span>

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- <span data-ttu-id="0b8d1-131">Se il primo operando è di tipo [uint](../keywords/uint.md) oppure [ulong](../keywords/ulong.md), l'operatore di scorrimento a destra esegue uno scorrimento *logico*: le posizioni dei bit vuoti più significativi vengono sempre impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-131">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift operator performs a *logical* shift: the high-order empty bit positions are always set to zero.</span></span>

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

<span data-ttu-id="0b8d1-132">Per informazioni su come il secondo operando dell'operatore `>>` definisce il conteggio degli scorrimenti, vedere la sezione [Conteggio degli scorrimenti degli operatori di scorrimento](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-132">For information about how the second operand of the `>>` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="logical-and-operator-amp"></a><span data-ttu-id="0b8d1-133">Operatore AND logico &amp;</span><span class="sxs-lookup"><span data-stu-id="0b8d1-133">Logical AND operator &amp;</span></span>

<span data-ttu-id="0b8d1-134">L'operatore `&` calcola l'AND logico bit per bit dei relativi operandi:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-134">The `&` operator computes the bitwise logical AND of its operands:</span></span>

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

<span data-ttu-id="0b8d1-135">Per gli operandi di tipo `bool`, l'operatore `&` calcola l'[AND logico](boolean-logical-operators.md#logical-and-operator-) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-135">For the operands of the `bool` type, the `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="0b8d1-136">L'operatore unario `&` è l'[operatore address-of](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-136">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="0b8d1-137">Operatore OR esclusivo logico: ^</span><span class="sxs-lookup"><span data-stu-id="0b8d1-137">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="0b8d1-138">L'operatore `^` calcola l'OR esclusivo logico bit per bit, chiamato anche XOR logico bit per bit, dei relativi operandi:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-138">The `^` operator computes the bitwise logical exclusive OR, also known as the bitwise logical XOR, of its operands:</span></span>

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

<span data-ttu-id="0b8d1-139">Per gli operandi di tipo `bool`, l'operatore `^` calcola l'[OR esclusivo logico](boolean-logical-operators.md#logical-exclusive-or-operator-) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-139">For the operands of the `bool` type, the `^` operator computes the [logical exclusive OR](boolean-logical-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="0b8d1-140">Operatore OR logico |</span><span class="sxs-lookup"><span data-stu-id="0b8d1-140">Logical OR operator |</span></span>

<span data-ttu-id="0b8d1-141">L'operatore `|` calcola l'OR logico bit per bit dei relativi operandi:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-141">The `|` operator computes the bitwise logical OR of its operands:</span></span>

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

<span data-ttu-id="0b8d1-142">Per gli operandi di tipo `bool`, l'operatore `|` calcola l'[OR logico](boolean-logical-operators.md#logical-or-operator-) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-142">For the operands of the `bool` type, the `|` operator computes the [logical OR](boolean-logical-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="0b8d1-143">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="0b8d1-143">Compound assignment</span></span>

<span data-ttu-id="0b8d1-144">Per un operatore binario `op`, un'espressione di assegnazione composta in formato</span><span class="sxs-lookup"><span data-stu-id="0b8d1-144">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="0b8d1-145">equivale a</span><span class="sxs-lookup"><span data-stu-id="0b8d1-145">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="0b8d1-146">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-146">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="0b8d1-147">L'esempio seguente illustra l'uso dell'assegnazione composta con gli operatori di scorrimento e bit per bit:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-147">The following example demonstrates the usage of compound assignment with bitwise and shift operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

<span data-ttu-id="0b8d1-148">A causa delle [promozioni numeriche](~/_csharplang/spec/expressions.md#numeric-promotions) il risultato dell'operazione `op` potrebbe non essere convertibile in modo implicito nel tipo `T` di `x`.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-148">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="0b8d1-149">In questo caso, se `op` è un operatore già definito e il risultato dell'operazione è convertibile in modo esplicito nel tipo `T` di `x`, un'espressione di assegnazione composta nel formato `x op= y` equivale a `x = (T)(x op y)`, con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-149">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="0b8d1-150">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-150">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a><span data-ttu-id="0b8d1-151">Precedenza tra gli operatori</span><span class="sxs-lookup"><span data-stu-id="0b8d1-151">Operator precedence</span></span>

<span data-ttu-id="0b8d1-152">Nell'elenco seguente gli operatori di scorrimento e bit per bit sono ordinati dalla precedenza più elevata a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-152">The following list orders bitwise and shift operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="0b8d1-153">Operatore di complemento bit per bit `~`</span><span class="sxs-lookup"><span data-stu-id="0b8d1-153">Bitwise complement operator `~`</span></span>
- <span data-ttu-id="0b8d1-154">Operatori di scorrimento `<<` e `>>`</span><span class="sxs-lookup"><span data-stu-id="0b8d1-154">Shift operators `<<` and `>>`</span></span>
- <span data-ttu-id="0b8d1-155">Operatore AND logico `&`</span><span class="sxs-lookup"><span data-stu-id="0b8d1-155">Logical AND operator `&`</span></span>
- <span data-ttu-id="0b8d1-156">Operatore OR esclusivo logico `^`</span><span class="sxs-lookup"><span data-stu-id="0b8d1-156">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="0b8d1-157">Operatore OR logico `|`</span><span class="sxs-lookup"><span data-stu-id="0b8d1-157">Logical OR operator `|`</span></span>

<span data-ttu-id="0b8d1-158">Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-158">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

<span data-ttu-id="0b8d1-159">Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere [Operatori C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-159">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="shift-count-of-the-shift-operators"></a><span data-ttu-id="0b8d1-160">Conteggio degli scorrimenti degli operatori di scorrimento</span><span class="sxs-lookup"><span data-stu-id="0b8d1-160">Shift count of the shift operators</span></span>

<span data-ttu-id="0b8d1-161">Per gli operatori di scorrimento `<<` e `>>`, il tipo del secondo operando deve essere [int](../keywords/int.md) o un tipo con una [conversione numerica implicita predefinita](../keywords/implicit-numeric-conversions-table.md) in `int`.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-161">For the shift operators `<<` and `>>`, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="0b8d1-162">Per le espressioni `x << count` e `x >> count`, il conteggio effettivo degli scorrimenti varia a seconda del tipo di `x` come segue:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-162">For the `x << count` and `x >> count` expressions, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="0b8d1-163">Se il tipo di `x` è [int](../keywords/int.md) o [uint](../keywords/uint.md), il conteggio degli scorrimenti è definito dai *cinque* bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-163">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is defined by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="0b8d1-164">Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x1F` (o `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-164">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="0b8d1-165">Se il tipo di `x` è [long](../keywords/long.md) o [ulong](../keywords/ulong.md), il conteggio degli scorrimenti è definito dai *sei* bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-165">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is defined by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="0b8d1-166">Vale a dire, il conteggio degli scorrimenti viene calcolato da `count & 0x3F` (o `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-166">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="0b8d1-167">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="0b8d1-167">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

## <a name="enumeration-logical-operators"></a><span data-ttu-id="0b8d1-168">Operatori logici di enumerazione</span><span class="sxs-lookup"><span data-stu-id="0b8d1-168">Enumeration logical operators</span></span>

<span data-ttu-id="0b8d1-169">Gli operatori `~`, `&`, `|` e `^` sono definiti anche per qualsiasi tipo di [enumerazione](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-169">The `~`, `&`, `|`, and `^` operators are also defined for any [enumeration](../keywords/enum.md) type.</span></span> <span data-ttu-id="0b8d1-170">Per gli operandi dello stesso tipo di enumerazione, viene eseguita un'operazione logica sui valori corrispondenti del tipo integrale sottostante.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-170">For the operands of the same enumeration type, a logical operation is performed on the corresponding values of the underlying integral type.</span></span> <span data-ttu-id="0b8d1-171">Ad esempio, per qualsiasi `x` e `y` di un tipo di enumerazione `T` con un tipo sottostante `U`, l'espressione `x & y` produce lo stesso risultato dell'espressione `(T)((U)x & (U)y)`.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-171">For example, for any `x` and `y` of an enumeration type `T` with an underlying type `U`, the `x & y` expression produces the same result as the `(T)((U)x & (U)y)` expression.</span></span>

<span data-ttu-id="0b8d1-172">Gli operatori logici bit per bit vengono in genere usati con un tipo di enumerazione definito con l'attributo [Flags](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-172">You typically use bitwise logical operators with an enumeration type which is defined with the [Flags](xref:System.FlagsAttribute) attribute.</span></span> <span data-ttu-id="0b8d1-173">Per altre informazioni, vedere la sezione [Tipi di enumerazione come flag di bit](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags) dell'articolo [Tipi di enumerazione](../../programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="0b8d1-173">For more information, see the [Enumeration types as bit flags](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags) section of the [Enumeration types](../../programming-guide/enumeration-types.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0b8d1-174">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="0b8d1-174">Operator overloadability</span></span>

<span data-ttu-id="0b8d1-175">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) degli operatori `~`, `<<`, `>>`, `&`, `|` e `^`.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-175">A user-defined type can [overload](../keywords/operator.md) the `~`, `<<`, `>>`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="0b8d1-176">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione composta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-176">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="0b8d1-177">Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-177">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="0b8d1-178">Se un tipo definito dall'utente `T` esegue l'overload dell'operatore `<<` o `>>`, il tipo del primo operando deve essere `T` e il tipo del secondo operando deve essere `int`.</span><span class="sxs-lookup"><span data-stu-id="0b8d1-178">If a user-defined type `T` overloads the `<<` or `>>` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b8d1-179">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0b8d1-179">C# language specification</span></span>

<span data-ttu-id="0b8d1-180">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="0b8d1-180">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="0b8d1-181">Operatore di complemento bit per bit</span><span class="sxs-lookup"><span data-stu-id="0b8d1-181">Bitwise complement operator</span></span>](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [<span data-ttu-id="0b8d1-182">Operatori shift</span><span class="sxs-lookup"><span data-stu-id="0b8d1-182">Shift operators</span></span>](~/_csharplang/spec/expressions.md#shift-operators)
- [<span data-ttu-id="0b8d1-183">Operatori logici</span><span class="sxs-lookup"><span data-stu-id="0b8d1-183">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="0b8d1-184">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="0b8d1-184">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="0b8d1-185">Promozioni numeriche</span><span class="sxs-lookup"><span data-stu-id="0b8d1-185">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="0b8d1-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b8d1-186">See also</span></span>

- [<span data-ttu-id="0b8d1-187">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0b8d1-187">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0b8d1-188">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0b8d1-188">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0b8d1-189">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="0b8d1-189">C# Operators</span></span>](index.md)
- [<span data-ttu-id="0b8d1-190">Operatori logici booleani</span><span class="sxs-lookup"><span data-stu-id="0b8d1-190">Boolean logical operators</span></span>](boolean-logical-operators.md)
