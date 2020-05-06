---
title: Operatori logici booleani - Riferimenti per C#
description: Informazioni sugli operatori C# che eseguono operazioni logiche di negazione, congiunzione (AND) e disgiunzione inclusiva ed esclusiva (OR) con operandi booleani.
ms.date: 09/27/2019
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: 5f85b88236c2e643f97453c64173a3f4f7159a35
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795001"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="8325f-103">Operatori logici booleani (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8325f-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="8325f-104">Gli operatori seguenti eseguono operazioni logiche con operandi [bool](../builtin-types/bool.md) :</span><span class="sxs-lookup"><span data-stu-id="8325f-104">The following operators perform logical operations with [bool](../builtin-types/bool.md) operands:</span></span>

- <span data-ttu-id="8325f-105">Operatore unario [ `!` (negazione logica)](#logical-negation-operator-) .</span><span class="sxs-lookup"><span data-stu-id="8325f-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="8325f-106">Operatori di tipo binario [ `&` (and logico)](#logical-and-operator-), [ `|` (OR logico)](#logical-or-operator-)e [ `^` (OR esclusivo logico)](#logical-exclusive-or-operator-) .</span><span class="sxs-lookup"><span data-stu-id="8325f-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="8325f-107">Questi operatori valutano sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="8325f-108">Operatori binari [ `&&` (and logico condizionale)](#conditional-logical-and-operator-) e [ `||` (OR logico condizionale)](#conditional-logical-or-operator-) .</span><span class="sxs-lookup"><span data-stu-id="8325f-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="8325f-109">Questi operatori valutano l'operando di destra solo se è necessario.</span><span class="sxs-lookup"><span data-stu-id="8325f-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="8325f-110">Per gli operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md), gli `&`operatori `|`, e `^` eseguono operazioni logiche bit per bit.</span><span class="sxs-lookup"><span data-stu-id="8325f-110">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="8325f-111">Per altre informazioni, vedere [Operatori di scorrimento e bit per bit](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="8325f-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="8325f-112">Operatore di negazione logica !</span><span class="sxs-lookup"><span data-stu-id="8325f-112">Logical negation operator !</span></span>

<span data-ttu-id="8325f-113">L'operatore di `!` prefisso unario calcola la negazione logica del relativo operando.</span><span class="sxs-lookup"><span data-stu-id="8325f-113">The unary prefix `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="8325f-114">Vale a dire, produce `true` se l'operando restituisce `false` e `false` se l'operando restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="8325f-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](snippets/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="8325f-115">A partire da C# 8,0, l'operatore `!` unario di suffisso è l' [operatore che perdona i valori null](null-forgiving.md).</span><span class="sxs-lookup"><span data-stu-id="8325f-115">Beginning with C# 8.0, the unary postfix `!` operator is the [null-forgiving operator](null-forgiving.md).</span></span>

## <a name="logical-and-operator-amp"></a><a name="logical-and-operator-"></a><span data-ttu-id="8325f-116">Operatore AND logico&amp;</span><span class="sxs-lookup"><span data-stu-id="8325f-116">Logical AND operator &amp;</span></span>

<span data-ttu-id="8325f-117">L'operatore `&` calcola l'AND logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-117">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="8325f-118">Il risultato di `x & y` è `true` se `x` e `y` restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="8325f-118">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="8325f-119">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="8325f-119">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="8325f-120">L' `&` operatore valuta entrambi gli operandi anche se l'operando sinistro restituisce, in `false`modo che il risultato dell'operazione sia `false` indipendentemente dal valore dell'operando destro.</span><span class="sxs-lookup"><span data-stu-id="8325f-120">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the operation result is `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="8325f-121">Nell'esempio seguente l'operando di destra dell'operatore `&` è una chiamata a un metodo, che viene eseguita indipendentemente dal valore dell'operando di sinistra:</span><span class="sxs-lookup"><span data-stu-id="8325f-121">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](snippets/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="8325f-122">L'[operatore AND condizionale logico](#conditional-logical-and-operator-) `&&` calcola anche l'AND logico dei relativi operandi, ma non valuta l'operando di destra se l'operando di sinistra restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="8325f-122">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="8325f-123">Per gli operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md), l' `&` operatore calcola l' [and logico bit per bit](bitwise-and-shift-operators.md#logical-and-operator-) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-123">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="8325f-124">L'operatore unario `&` è l'[operatore address-of](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="8325f-124">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="8325f-125">Operatore OR esclusivo logico: ^</span><span class="sxs-lookup"><span data-stu-id="8325f-125">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="8325f-126">L'operatore `^` calcola l'OR esclusivo logico, noto anche come XOR logico, dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-126">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="8325f-127">Il risultato di `x ^ y` è `true` se `x` restituisce `true` e `y` restituisce `false` oppure `x` restituisce `false` e `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="8325f-127">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="8325f-128">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="8325f-128">Otherwise, the result is `false`.</span></span> <span data-ttu-id="8325f-129">Vale a dire, per gli operandi `bool`, l'operatore `^` calcola lo stesso risultato dell'[operatore di disuguaglianza](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="8325f-129">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](snippets/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="8325f-130">Per gli operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md), l' `^` operatore calcola l' [OR esclusivo logico bit per bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-130">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="8325f-131">Operatore OR logico |</span><span class="sxs-lookup"><span data-stu-id="8325f-131">Logical OR operator |</span></span>

<span data-ttu-id="8325f-132">L'operatore `|` calcola l'OR logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-132">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="8325f-133">Il risultato di `x | y` è `true` se `x` o `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="8325f-133">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="8325f-134">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="8325f-134">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="8325f-135">L' `|` operatore valuta entrambi gli operandi anche se l'operando sinistro restituisce, in `true`modo che il risultato dell'operazione sia `true` indipendentemente dal valore dell'operando destro.</span><span class="sxs-lookup"><span data-stu-id="8325f-135">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the operation result is `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="8325f-136">Nell'esempio seguente l'operando di destra dell'operatore `|` è una chiamata a un metodo, che viene eseguita indipendentemente dal valore dell'operando di sinistra:</span><span class="sxs-lookup"><span data-stu-id="8325f-136">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](snippets/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="8325f-137">L'[operatore OR condizionale logico](#conditional-logical-or-operator-) `||` calcola anche l'OR logico dei relativi operandi, ma non valuta l'operando di destra se l'operando di sinistra restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="8325f-137">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="8325f-138">Per gli operandi dei [tipi numerici integrali](../builtin-types/integral-numeric-types.md), l' `|` operatore calcola l' [OR logico bit per bit](bitwise-and-shift-operators.md#logical-or-operator-) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-138">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><a name="conditional-logical-and-operator-"></a><span data-ttu-id="8325f-139">Operatore logico AND condizionale&amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="8325f-139">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="8325f-140">L'operatore AND condizionale logico `&&`, chiamato anche operatore AND logico di "corto circuito", calcola l'AND logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-140">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="8325f-141">Il risultato di `x && y` è `true` se `x` e `y` restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="8325f-141">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="8325f-142">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="8325f-142">Otherwise, the result is `false`.</span></span> <span data-ttu-id="8325f-143">Se `x` è `false`, `y` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="8325f-143">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="8325f-144">Nell'esempio seguente l'operando di destra dell'operatore `&&` è una chiamata a un metodo, che non viene eseguita se l'operando di sinistra restituisce `false`:</span><span class="sxs-lookup"><span data-stu-id="8325f-144">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](snippets/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="8325f-145">`&` L' [operatore logico and](#logical-and-operator-) calcola anche l'and logico degli operandi, ma valuta sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-145">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="8325f-146">Operatore OR condizionale logico ||</span><span class="sxs-lookup"><span data-stu-id="8325f-146">Conditional logical OR operator ||</span></span>

<span data-ttu-id="8325f-147">L'operatore OR condizionale logico `||`, chiamato anche operatore OR logico di "corto circuito", calcola l'OR logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-147">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="8325f-148">Il risultato di `x || y` è `true` se `x` o `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="8325f-148">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="8325f-149">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="8325f-149">Otherwise, the result is `false`.</span></span> <span data-ttu-id="8325f-150">Se `x` è `true`, `y` non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="8325f-150">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="8325f-151">Nell'esempio seguente l'operando di destra dell'operatore `||` è una chiamata a un metodo, che non viene eseguita se l'operando di sinistra restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="8325f-151">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](snippets/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="8325f-152">L' [operatore](#logical-or-operator-) `|` OR logico calcola anche l'OR logico degli operandi, ma valuta sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-152">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="8325f-153">Operatori logici booleani nullable</span><span class="sxs-lookup"><span data-stu-id="8325f-153">Nullable Boolean logical operators</span></span>

<span data-ttu-id="8325f-154">Per `bool?` gli operandi, gli `&` operatori `|` e supportano la logica a tre valori.</span><span class="sxs-lookup"><span data-stu-id="8325f-154">For `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="8325f-155">La semantica di questi operatori è definita dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="8325f-155">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="8325f-156">x</span><span class="sxs-lookup"><span data-stu-id="8325f-156">x</span></span>|<span data-ttu-id="8325f-157">y</span><span class="sxs-lookup"><span data-stu-id="8325f-157">y</span></span>|<span data-ttu-id="8325f-158">x&y</span><span class="sxs-lookup"><span data-stu-id="8325f-158">x&y</span></span>|<span data-ttu-id="8325f-159">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="8325f-159">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="8325f-160">true</span><span class="sxs-lookup"><span data-stu-id="8325f-160">true</span></span>|<span data-ttu-id="8325f-161">true</span><span class="sxs-lookup"><span data-stu-id="8325f-161">true</span></span>|<span data-ttu-id="8325f-162">true</span><span class="sxs-lookup"><span data-stu-id="8325f-162">true</span></span>|<span data-ttu-id="8325f-163">true</span><span class="sxs-lookup"><span data-stu-id="8325f-163">true</span></span>|  
|<span data-ttu-id="8325f-164">true</span><span class="sxs-lookup"><span data-stu-id="8325f-164">true</span></span>|<span data-ttu-id="8325f-165">false</span><span class="sxs-lookup"><span data-stu-id="8325f-165">false</span></span>|<span data-ttu-id="8325f-166">false</span><span class="sxs-lookup"><span data-stu-id="8325f-166">false</span></span>|<span data-ttu-id="8325f-167">true</span><span class="sxs-lookup"><span data-stu-id="8325f-167">true</span></span>|  
|<span data-ttu-id="8325f-168">true</span><span class="sxs-lookup"><span data-stu-id="8325f-168">true</span></span>|<span data-ttu-id="8325f-169">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-169">null</span></span>|<span data-ttu-id="8325f-170">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-170">null</span></span>|<span data-ttu-id="8325f-171">true</span><span class="sxs-lookup"><span data-stu-id="8325f-171">true</span></span>|  
|<span data-ttu-id="8325f-172">false</span><span class="sxs-lookup"><span data-stu-id="8325f-172">false</span></span>|<span data-ttu-id="8325f-173">true</span><span class="sxs-lookup"><span data-stu-id="8325f-173">true</span></span>|<span data-ttu-id="8325f-174">false</span><span class="sxs-lookup"><span data-stu-id="8325f-174">false</span></span>|<span data-ttu-id="8325f-175">true</span><span class="sxs-lookup"><span data-stu-id="8325f-175">true</span></span>|  
|<span data-ttu-id="8325f-176">false</span><span class="sxs-lookup"><span data-stu-id="8325f-176">false</span></span>|<span data-ttu-id="8325f-177">false</span><span class="sxs-lookup"><span data-stu-id="8325f-177">false</span></span>|<span data-ttu-id="8325f-178">false</span><span class="sxs-lookup"><span data-stu-id="8325f-178">false</span></span>|<span data-ttu-id="8325f-179">false</span><span class="sxs-lookup"><span data-stu-id="8325f-179">false</span></span>|  
|<span data-ttu-id="8325f-180">false</span><span class="sxs-lookup"><span data-stu-id="8325f-180">false</span></span>|<span data-ttu-id="8325f-181">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-181">null</span></span>|<span data-ttu-id="8325f-182">false</span><span class="sxs-lookup"><span data-stu-id="8325f-182">false</span></span>|<span data-ttu-id="8325f-183">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-183">null</span></span>|  
|<span data-ttu-id="8325f-184">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-184">null</span></span>|<span data-ttu-id="8325f-185">true</span><span class="sxs-lookup"><span data-stu-id="8325f-185">true</span></span>|<span data-ttu-id="8325f-186">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-186">null</span></span>|<span data-ttu-id="8325f-187">true</span><span class="sxs-lookup"><span data-stu-id="8325f-187">true</span></span>|  
|<span data-ttu-id="8325f-188">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-188">null</span></span>|<span data-ttu-id="8325f-189">false</span><span class="sxs-lookup"><span data-stu-id="8325f-189">false</span></span>|<span data-ttu-id="8325f-190">false</span><span class="sxs-lookup"><span data-stu-id="8325f-190">false</span></span>|<span data-ttu-id="8325f-191">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-191">null</span></span>|  
|<span data-ttu-id="8325f-192">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-192">null</span></span>|<span data-ttu-id="8325f-193">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-193">null</span></span>|<span data-ttu-id="8325f-194">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-194">null</span></span>|<span data-ttu-id="8325f-195">Null</span><span class="sxs-lookup"><span data-stu-id="8325f-195">null</span></span>|  

<span data-ttu-id="8325f-196">Il comportamento di questi operatori è diverso dal comportamento tipico degli operatori con tipi valore nullable.</span><span class="sxs-lookup"><span data-stu-id="8325f-196">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="8325f-197">In genere un operatore definito per gli operandi di un tipo valore può essere usato anche con gli operandi del tipo valore nullable corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8325f-197">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="8325f-198">Questo operatore produce `null` se uno qualsiasi degli operandi restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="8325f-198">Such an operator produces `null` if any of its operands evaluates to `null`.</span></span> <span data-ttu-id="8325f-199">Tuttavia, gli `&` operatori `|` e possono produrre un valore diverso da `null`null anche se uno degli operandi restituisce.</span><span class="sxs-lookup"><span data-stu-id="8325f-199">However, the `&` and `|` operators can produce non-null even if one of the operands evaluates to `null`.</span></span> <span data-ttu-id="8325f-200">Per ulteriori informazioni sul comportamento dell'operatore con i tipi di valore Nullable, vedere la sezione [operatori rimossi](../builtin-types/nullable-value-types.md#lifted-operators) dell'articolo [tipi di valore Nullable](../builtin-types/nullable-value-types.md) .</span><span class="sxs-lookup"><span data-stu-id="8325f-200">For more information about the operator behavior with nullable value types, see the [Lifted operators](../builtin-types/nullable-value-types.md#lifted-operators) section of the [Nullable value types](../builtin-types/nullable-value-types.md) article.</span></span>

<span data-ttu-id="8325f-201">È anche possibile usare gli `!` operatori `^` e con `bool?` operandi, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8325f-201">You can also use the `!` and `^` operators with `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](snippets/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="8325f-202">Gli operatori `&&` logici condizionali e `||` non supportano `bool?` gli operandi.</span><span class="sxs-lookup"><span data-stu-id="8325f-202">The conditional logical operators `&&` and `||` don't support `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="8325f-203">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="8325f-203">Compound assignment</span></span>

<span data-ttu-id="8325f-204">Per un operatore binario `op`, un'espressione di assegnazione composta in formato</span><span class="sxs-lookup"><span data-stu-id="8325f-204">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="8325f-205">equivale a</span><span class="sxs-lookup"><span data-stu-id="8325f-205">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="8325f-206">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="8325f-206">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="8325f-207">Gli operatori `&`, `|` e `^` supportano l'assegnazione composta, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8325f-207">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](snippets/BooleanLogicalOperators.cs#CompoundAssignment)]

> [!NOTE]
> <span data-ttu-id="8325f-208">Gli operatori condizionali logici `&&` e `||` non supportano l'assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="8325f-208">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="8325f-209">Precedenza degli operatori</span><span class="sxs-lookup"><span data-stu-id="8325f-209">Operator precedence</span></span>

<span data-ttu-id="8325f-210">Nell'elenco seguente gli operatori logici sono ordinati dalla precedenza più elevata a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="8325f-210">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="8325f-211">Operatore di negazione logica `!`</span><span class="sxs-lookup"><span data-stu-id="8325f-211">Logical negation operator `!`</span></span>
- <span data-ttu-id="8325f-212">Operatore AND logico `&`</span><span class="sxs-lookup"><span data-stu-id="8325f-212">Logical AND operator `&`</span></span>
- <span data-ttu-id="8325f-213">Operatore OR esclusivo logico `^`</span><span class="sxs-lookup"><span data-stu-id="8325f-213">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="8325f-214">Operatore OR logico `|`</span><span class="sxs-lookup"><span data-stu-id="8325f-214">Logical OR operator `|`</span></span>
- <span data-ttu-id="8325f-215">Operatore AND condizionale logico `&&`</span><span class="sxs-lookup"><span data-stu-id="8325f-215">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="8325f-216">Operatore OR condizionale logico `||`</span><span class="sxs-lookup"><span data-stu-id="8325f-216">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="8325f-217">Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori:</span><span class="sxs-lookup"><span data-stu-id="8325f-217">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](snippets/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="8325f-218">Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere la sezione [precedenza](index.md#operator-precedence) degli operatori dell'articolo [operatori c#](index.md) .</span><span class="sxs-lookup"><span data-stu-id="8325f-218">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="8325f-219">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="8325f-219">Operator overloadability</span></span>

<span data-ttu-id="8325f-220">Un tipo definito dall'utente può [overload](operator-overloading.md) eseguire l' `!`overload `&`degli `|`operatori, `^` , e.</span><span class="sxs-lookup"><span data-stu-id="8325f-220">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="8325f-221">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione composta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8325f-221">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="8325f-222">Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="8325f-222">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="8325f-223">Un tipo definito dall'utente non può eseguire l'overload degli operatori condizionali logici `&&` e `||`.</span><span class="sxs-lookup"><span data-stu-id="8325f-223">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="8325f-224">Tuttavia, se un tipo definito dall'utente esegue l'overload degli [operatori true e false](true-false-operators.md) e dell'operatore `&` o `|` in un determinato modo, l'operazione `&&` o `||` può essere valutata per gli operandi di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="8325f-224">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="8325f-225">Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8325f-225">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8325f-226">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8325f-226">C# language specification</span></span>

<span data-ttu-id="8325f-227">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="8325f-227">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="8325f-228">Operatore di negazione logica</span><span class="sxs-lookup"><span data-stu-id="8325f-228">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="8325f-229">Operatori logici</span><span class="sxs-lookup"><span data-stu-id="8325f-229">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="8325f-230">Operatori logici condizionali</span><span class="sxs-lookup"><span data-stu-id="8325f-230">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="8325f-231">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="8325f-231">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="8325f-232">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8325f-232">See also</span></span>

- [<span data-ttu-id="8325f-233">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="8325f-233">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8325f-234">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8325f-234">C# operators</span></span>](index.md)
- [<span data-ttu-id="8325f-235">Operatori di spostamento e bit per bit</span><span class="sxs-lookup"><span data-stu-id="8325f-235">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
