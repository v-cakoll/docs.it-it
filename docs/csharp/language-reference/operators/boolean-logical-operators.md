---
title: Operatori logici booleani - Riferimenti per C#
description: Informazioni sugli operatori C# che eseguono operazioni logiche di negazione, congiunzione (AND) e disgiunzione inclusiva ed esclusiva (OR) con operandi booleani.
ms.date: 04/08/2019
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
ms.openlocfilehash: b666c915506872930b16c1c5890de24e9cbe4f7a
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880573"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="60dcb-103">Operatori logici booleani (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="60dcb-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="60dcb-104">Gli operatori seguenti eseguono operazioni logiche con gli operandi [bool](../keywords/bool.md):</span><span class="sxs-lookup"><span data-stu-id="60dcb-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="60dcb-105">Operatore unario [`!` (negazione logica)](#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="60dcb-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="60dcb-106">Operatori binari [`&` (AND logico)](#logical-and-operator-), [`|` (OR logico)](#logical-or-operator-) e [`^` (OR esclusivo logico)](#logical-exclusive-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="60dcb-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="60dcb-107">Questi operatori valutano sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="60dcb-108">Operatori binari [`&&` (AND condizionale logico)](#conditional-logical-and-operator-) e [`||` (OR condizionale logico)](#conditional-logical-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="60dcb-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="60dcb-109">Questi operatori valutano il secondo operando solo se è necessario.</span><span class="sxs-lookup"><span data-stu-id="60dcb-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="60dcb-110">Per gli operandi dei tipi [integrali](../keywords/integral-types-table.md), gli operatori `&`, `|` e `^` eseguono operazioni logiche bit per bit.</span><span class="sxs-lookup"><span data-stu-id="60dcb-110">For the operands of the [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="60dcb-111">Per altre informazioni, vedere [Operatori di scorrimento e bit per bit](bitwise-and-shift-operators.md).</span><span class="sxs-lookup"><span data-stu-id="60dcb-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="60dcb-112">Operatore di negazione logica !</span><span class="sxs-lookup"><span data-stu-id="60dcb-112">Logical negation operator !</span></span>

<span data-ttu-id="60dcb-113">L'operatore `!` calcola la negazione logica del suo operando.</span><span class="sxs-lookup"><span data-stu-id="60dcb-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="60dcb-114">Vale a dire, produce `true` se l'operando restituisce `false` e `false` se l'operando restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="60dcb-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="60dcb-115">Operatore AND logico &amp;</span><span class="sxs-lookup"><span data-stu-id="60dcb-115">Logical AND operator &amp;</span></span>

<span data-ttu-id="60dcb-116">L'operatore `&` calcola l'AND logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-116">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="60dcb-117">Il risultato di `x & y` è `true` se `x` e `y` restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-117">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="60dcb-118">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-118">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="60dcb-119">L'operatore `&` valuta entrambi gli operandi anche se il primo operando restituisce `false`, in modo che il risultato sia `false` indipendentemente dal valore del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="60dcb-119">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="60dcb-120">Nell'esempio seguente il secondo operando dell'operatore `&` è una chiamata a un metodo, che viene eseguita indipendentemente dal valore del primo operando:</span><span class="sxs-lookup"><span data-stu-id="60dcb-120">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

<span data-ttu-id="60dcb-121">L'[operatore AND condizionale logico](#conditional-logical-and-operator-) `&&` calcola anche l'AND logico dei relativi operandi, ma non valuta il secondo operando se il primo operando restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-121">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="60dcb-122">Per gli operandi dei tipi integrali, l'operatore `&` calcola l'[AND logico bit per bit](bitwise-and-shift-operators.md#logical-and-operator-) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-122">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="60dcb-123">L'operatore unario `&` è l'[operatore address-of](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="60dcb-123">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="60dcb-124">Operatore OR esclusivo logico: ^</span><span class="sxs-lookup"><span data-stu-id="60dcb-124">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="60dcb-125">L'operatore `^` calcola l'OR esclusivo logico, noto anche come XOR logico, dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-125">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="60dcb-126">Il risultato di `x ^ y` è `true` se `x` restituisce `true` e `y` restituisce `false` oppure `x` restituisce `false` e `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-126">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="60dcb-127">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-127">Otherwise, the result is `false`.</span></span> <span data-ttu-id="60dcb-128">Vale a dire, per gli operandi `bool`, l'operatore `^` calcola lo stesso risultato dell'[operatore di disuguaglianza](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-128">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

<span data-ttu-id="60dcb-129">Per gli operandi dei tipi integrali, l'operatore `^` calcola l'[OR esclusivo logico bit per bit](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-129">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="60dcb-130">Operatore OR logico |</span><span class="sxs-lookup"><span data-stu-id="60dcb-130">Logical OR operator |</span></span>

<span data-ttu-id="60dcb-131">L'operatore `|` calcola l'OR logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-131">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="60dcb-132">Il risultato di `x | y` è `true` se `x` o `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-132">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="60dcb-133">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-133">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="60dcb-134">L'operatore `|` valuta entrambi gli operandi anche se il primo operando restituisce `true`, in modo che il risultato sia `true` indipendentemente dal valore del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="60dcb-134">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="60dcb-135">Nell'esempio seguente il secondo operando dell'operatore `|` è una chiamata a un metodo, che viene eseguita indipendentemente dal valore del primo operando:</span><span class="sxs-lookup"><span data-stu-id="60dcb-135">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

<span data-ttu-id="60dcb-136">L'[operatore OR condizionale logico](#conditional-logical-or-operator-) `||` calcola anche l'OR logico dei relativi operandi, ma non valuta il secondo operando se il primo operando restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-136">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="60dcb-137">Per gli operandi dei tipi integrali, l'operatore `|` calcola l'[OR logico bit per bit](bitwise-and-shift-operators.md#logical-or-operator-) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-137">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="60dcb-138">Operatore AND condizionale logico&amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="60dcb-138">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="60dcb-139">L'operatore AND condizionale logico `&&`, chiamato anche operatore AND logico di "corto circuito", calcola l'AND logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-139">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="60dcb-140">Il risultato di `x && y` è `true` se `x` e `y` restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-140">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="60dcb-141">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-141">Otherwise, the result is `false`.</span></span> <span data-ttu-id="60dcb-142">Se il primo operando restituisce `false`, il secondo operando non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="60dcb-142">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="60dcb-143">Nell'esempio seguente il secondo operando dell'operatore `&&` è una chiamata a un metodo, che non viene eseguita se il primo operando restituisce `false`:</span><span class="sxs-lookup"><span data-stu-id="60dcb-143">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="60dcb-144">L'[operatore AND logico](#logical-and-operator-) `&` calcola anche l'AND logico dei relativi operandi, ma valuta sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-144">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="60dcb-145">Operatore OR condizionale logico ||</span><span class="sxs-lookup"><span data-stu-id="60dcb-145">Conditional logical OR operator ||</span></span>

<span data-ttu-id="60dcb-146">L'operatore OR condizionale logico `||`, chiamato anche operatore OR logico di "corto circuito", calcola l'OR logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-146">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="60dcb-147">Il risultato di `x || y` è `true` se `x` o `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-147">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="60dcb-148">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-148">Otherwise, the result is `false`.</span></span> <span data-ttu-id="60dcb-149">Se il primo operando restituisce `true`, il secondo operando non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="60dcb-149">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="60dcb-150">Nell'esempio seguente il secondo operando dell'operatore `||` è una chiamata a un metodo, che non viene eseguita se il primo operando restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="60dcb-150">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="60dcb-151">L'[operatore OR logico](#logical-or-operator-) `|` calcola anche l'OR logico dei relativi operandi, ma valuta sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="60dcb-151">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="60dcb-152">Operatori logici booleani nullable</span><span class="sxs-lookup"><span data-stu-id="60dcb-152">Nullable Boolean logical operators</span></span>

<span data-ttu-id="60dcb-153">Per gli operandi `bool?`, gli operatori `&` e `|` supportano la logica a tre valori.</span><span class="sxs-lookup"><span data-stu-id="60dcb-153">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="60dcb-154">La semantica di questi operatori è definita dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="60dcb-154">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="60dcb-155">x</span><span class="sxs-lookup"><span data-stu-id="60dcb-155">x</span></span>|<span data-ttu-id="60dcb-156">y</span><span class="sxs-lookup"><span data-stu-id="60dcb-156">y</span></span>|<span data-ttu-id="60dcb-157">x&y</span><span class="sxs-lookup"><span data-stu-id="60dcb-157">x&y</span></span>|<span data-ttu-id="60dcb-158">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="60dcb-158">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="60dcb-159">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-159">true</span></span>|<span data-ttu-id="60dcb-160">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-160">true</span></span>|<span data-ttu-id="60dcb-161">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-161">true</span></span>|<span data-ttu-id="60dcb-162">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-162">true</span></span>|  
|<span data-ttu-id="60dcb-163">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-163">true</span></span>|<span data-ttu-id="60dcb-164">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-164">false</span></span>|<span data-ttu-id="60dcb-165">false</span><span class="sxs-lookup"><span data-stu-id="60dcb-165">false</span></span>|<span data-ttu-id="60dcb-166">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-166">true</span></span>|  
|<span data-ttu-id="60dcb-167">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-167">true</span></span>|<span data-ttu-id="60dcb-168">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-168">null</span></span>|<span data-ttu-id="60dcb-169">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-169">null</span></span>|<span data-ttu-id="60dcb-170">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-170">true</span></span>|  
|<span data-ttu-id="60dcb-171">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-171">false</span></span>|<span data-ttu-id="60dcb-172">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-172">true</span></span>|<span data-ttu-id="60dcb-173">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-173">false</span></span>|<span data-ttu-id="60dcb-174">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-174">true</span></span>|  
|<span data-ttu-id="60dcb-175">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-175">false</span></span>|<span data-ttu-id="60dcb-176">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-176">false</span></span>|<span data-ttu-id="60dcb-177">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-177">false</span></span>|<span data-ttu-id="60dcb-178">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-178">false</span></span>|  
|<span data-ttu-id="60dcb-179">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-179">false</span></span>|<span data-ttu-id="60dcb-180">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-180">null</span></span>|<span data-ttu-id="60dcb-181">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-181">false</span></span>|<span data-ttu-id="60dcb-182">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-182">null</span></span>|  
|<span data-ttu-id="60dcb-183">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-183">null</span></span>|<span data-ttu-id="60dcb-184">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-184">true</span></span>|<span data-ttu-id="60dcb-185">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-185">null</span></span>|<span data-ttu-id="60dcb-186">true</span><span class="sxs-lookup"><span data-stu-id="60dcb-186">true</span></span>|  
|<span data-ttu-id="60dcb-187">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-187">null</span></span>|<span data-ttu-id="60dcb-188">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-188">false</span></span>|<span data-ttu-id="60dcb-189">False</span><span class="sxs-lookup"><span data-stu-id="60dcb-189">false</span></span>|<span data-ttu-id="60dcb-190">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-190">null</span></span>|  
|<span data-ttu-id="60dcb-191">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-191">null</span></span>|<span data-ttu-id="60dcb-192">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-192">null</span></span>|<span data-ttu-id="60dcb-193">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-193">null</span></span>|<span data-ttu-id="60dcb-194">Null</span><span class="sxs-lookup"><span data-stu-id="60dcb-194">null</span></span>|  

<span data-ttu-id="60dcb-195">Il comportamento di questi operatori è diverso dal comportamento tipico degli operatori con tipi valore nullable.</span><span class="sxs-lookup"><span data-stu-id="60dcb-195">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="60dcb-196">In genere un operatore definito per gli operandi di un tipo valore può essere usato anche con gli operandi del tipo valore nullable corrispondente.</span><span class="sxs-lookup"><span data-stu-id="60dcb-196">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="60dcb-197">Un operatore di questo tipo produce `null` se uno qualsiasi dei suoi operandi è `null`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-197">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="60dcb-198">Tuttavia gli operatori `&` e `|` possono produrre valori non Null anche se uno degli operandi è `null`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-198">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="60dcb-199">Per altre informazioni sul comportamento degli operatori con i tipi valore nullable, vedere la sezione [Operatori](../../programming-guide/nullable-types/using-nullable-types.md#operators) dell'articolo [Uso dei tipi nullable](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="60dcb-199">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="60dcb-200">È anche possibile usare gli operatori `!` e `^` con gli operandi `bool?`, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="60dcb-200">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="60dcb-201">Gli operatori condizionali logici `&&` e `||` non supportano gli operandi `bool?`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-201">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="60dcb-202">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="60dcb-202">Compound assignment</span></span>

<span data-ttu-id="60dcb-203">Per un operatore binario `op`, un'espressione di assegnazione composta in formato</span><span class="sxs-lookup"><span data-stu-id="60dcb-203">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="60dcb-204">equivale a</span><span class="sxs-lookup"><span data-stu-id="60dcb-204">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="60dcb-205">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="60dcb-205">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="60dcb-206">Gli operatori `&`, `|` e `^` supportano l'assegnazione composta, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="60dcb-206">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="60dcb-207">Gli operatori condizionali logici `&&` e `||` non supportano l'assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="60dcb-207">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="60dcb-208">Precedenza tra gli operatori</span><span class="sxs-lookup"><span data-stu-id="60dcb-208">Operator precedence</span></span>

<span data-ttu-id="60dcb-209">Nell'elenco seguente gli operatori logici sono ordinati dalla precedenza più elevata a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="60dcb-209">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="60dcb-210">Operatore di negazione logica `!`</span><span class="sxs-lookup"><span data-stu-id="60dcb-210">Logical negation operator `!`</span></span>
- <span data-ttu-id="60dcb-211">Operatore AND logico `&`</span><span class="sxs-lookup"><span data-stu-id="60dcb-211">Logical AND operator `&`</span></span>
- <span data-ttu-id="60dcb-212">Operatore OR esclusivo logico `^`</span><span class="sxs-lookup"><span data-stu-id="60dcb-212">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="60dcb-213">Operatore OR logico `|`</span><span class="sxs-lookup"><span data-stu-id="60dcb-213">Logical OR operator `|`</span></span>
- <span data-ttu-id="60dcb-214">Operatore AND condizionale logico `&&`</span><span class="sxs-lookup"><span data-stu-id="60dcb-214">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="60dcb-215">Operatore OR condizionale logico `||`</span><span class="sxs-lookup"><span data-stu-id="60dcb-215">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="60dcb-216">Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori:</span><span class="sxs-lookup"><span data-stu-id="60dcb-216">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

<span data-ttu-id="60dcb-217">Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere [Operatori C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="60dcb-217">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="60dcb-218">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="60dcb-218">Operator overloadability</span></span>

<span data-ttu-id="60dcb-219">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) degli operatori `!`, `&`, `|` e `^`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-219">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="60dcb-220">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione composta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="60dcb-220">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="60dcb-221">Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="60dcb-221">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="60dcb-222">Un tipo definito dall'utente non può eseguire l'overload degli operatori condizionali logici `&&` e `||`.</span><span class="sxs-lookup"><span data-stu-id="60dcb-222">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="60dcb-223">Tuttavia, se un tipo definito dall'utente esegue l'overload degli [operatori true e false](../keywords/true-false-operators.md) e dell'operatore `&` o `|` in un determinato modo, l'operazione `&&` o `||` può essere valutata per gli operandi di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="60dcb-223">However, if a user-defined type overloads the [true and false operators](../keywords/true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="60dcb-224">Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="60dcb-224">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="60dcb-225">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="60dcb-225">C# language specification</span></span>

<span data-ttu-id="60dcb-226">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="60dcb-226">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="60dcb-227">Operatore di negazione logica</span><span class="sxs-lookup"><span data-stu-id="60dcb-227">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="60dcb-228">Operatori logici</span><span class="sxs-lookup"><span data-stu-id="60dcb-228">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="60dcb-229">Operatori logici condizionali</span><span class="sxs-lookup"><span data-stu-id="60dcb-229">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="60dcb-230">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="60dcb-230">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="60dcb-231">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60dcb-231">See also</span></span>

- [<span data-ttu-id="60dcb-232">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="60dcb-232">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="60dcb-233">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="60dcb-233">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="60dcb-234">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="60dcb-234">C# Operators</span></span>](index.md)
- [<span data-ttu-id="60dcb-235">Operatori di scorrimento e bit per bit</span><span class="sxs-lookup"><span data-stu-id="60dcb-235">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
