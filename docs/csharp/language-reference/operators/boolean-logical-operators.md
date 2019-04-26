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
ms.openlocfilehash: de621b26334bbc9679ba7e48a9d5a0cbaec67eab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427318"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="71153-103">Operatori logici booleani (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="71153-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="71153-104">Gli operatori seguenti eseguono operazioni logiche con gli operandi [bool](../keywords/bool.md):</span><span class="sxs-lookup"><span data-stu-id="71153-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="71153-105">Operatore unario [`!` (negazione logica)](#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="71153-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="71153-106">Operatori binari [`&` (AND logico)](#logical-and-operator-), [`|` (OR logico)](#logical-or-operator-) e [`^` (OR esclusivo logico)](#logical-exclusive-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="71153-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="71153-107">Questi operatori valutano sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="71153-108">Operatori binari [`&&` (AND condizionale logico)](#conditional-logical-and-operator-) e [`||` (OR condizionale logico)](#conditional-logical-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="71153-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="71153-109">Questi operatori valutano il secondo operando solo se è necessario.</span><span class="sxs-lookup"><span data-stu-id="71153-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="71153-110">Per gli operandi dei tipi [integrali](../keywords/integral-types-table.md), gli operatori `&`, `|` e `^` eseguono operazioni logiche bit per bit.</span><span class="sxs-lookup"><span data-stu-id="71153-110">For the operands of [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="71153-111">Operatore di negazione logica !</span><span class="sxs-lookup"><span data-stu-id="71153-111">Logical negation operator !</span></span>

<span data-ttu-id="71153-112">L'operatore `!` calcola la negazione logica del suo operando.</span><span class="sxs-lookup"><span data-stu-id="71153-112">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="71153-113">Vale a dire, produce `true` se l'operando restituisce `false` e `false` se l'operando restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="71153-113">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="71153-114">Operatore AND logico &amp;</span><span class="sxs-lookup"><span data-stu-id="71153-114">Logical AND operator &amp;</span></span>

<span data-ttu-id="71153-115">L'operatore `&` calcola l'AND logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-115">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="71153-116">Il risultato di `x & y` è `true` se `x` e `y` restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="71153-116">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="71153-117">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="71153-117">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="71153-118">L'operatore `&` valuta entrambi gli operandi anche se il primo operando restituisce `false`, in modo che il risultato sia `false` indipendentemente dal valore del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="71153-118">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="71153-119">Nell'esempio seguente il secondo operando dell'operatore `&` è una chiamata a un metodo, che viene eseguita indipendentemente dal valore del primo operando:</span><span class="sxs-lookup"><span data-stu-id="71153-119">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

<span data-ttu-id="71153-120">L'[operatore AND condizionale logico](#conditional-logical-and-operator-) `&&` calcola anche l'AND logico dei relativi operandi, ma non valuta il secondo operando se il primo operando restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="71153-120">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="71153-121">Per gli operandi dei tipi integrali, l'operatore `&` calcola l'[AND logico bit per bit](and-operator.md#integer-logical-bitwise-and-operator) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-121">For the operands of integral types, the `&` operator computes [bitwise logical AND](and-operator.md#integer-logical-bitwise-and-operator) of its operands.</span></span> <span data-ttu-id="71153-122">L'operatore unario `&` è l'[operatore address-of](and-operator.md#unary-address-of-operator).</span><span class="sxs-lookup"><span data-stu-id="71153-122">The unary `&` operator is the [address-of operator](and-operator.md#unary-address-of-operator).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="71153-123">Operatore OR esclusivo logico: ^</span><span class="sxs-lookup"><span data-stu-id="71153-123">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="71153-124">L'operatore `^` calcola l'OR esclusivo logico, noto anche come XOR logico, dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-124">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="71153-125">Il risultato di `x ^ y` è `true` se `x` restituisce `true` e `y` restituisce `false` oppure `x` restituisce `false` e `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="71153-125">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="71153-126">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="71153-126">Otherwise, the result is `false`.</span></span> <span data-ttu-id="71153-127">Vale a dire, per gli operandi `bool`, l'operatore `^` calcola lo stesso risultato dell'[operatore di disuguaglianza](equality-operators.md#inequality-operator-) `!=`.</span><span class="sxs-lookup"><span data-stu-id="71153-127">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

<span data-ttu-id="71153-128">Per gli operandi dei tipi integrali, l'operatore `^` calcola l'[OR esclusivo logico bit per bit](xor-operator.md) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-128">For the operands of integral types, the `^` operator computes [bitwise logical exclusive OR](xor-operator.md) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="71153-129">Operatore OR logico |</span><span class="sxs-lookup"><span data-stu-id="71153-129">Logical OR operator |</span></span>

<span data-ttu-id="71153-130">L'operatore `|` calcola l'OR logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-130">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="71153-131">Il risultato di `x | y` è `true` se `x` o `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="71153-131">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="71153-132">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="71153-132">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="71153-133">L'operatore `|` valuta entrambi gli operandi anche se il primo operando restituisce `true`, in modo che il risultato sia `true` indipendentemente dal valore del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="71153-133">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="71153-134">Nell'esempio seguente il secondo operando dell'operatore `|` è una chiamata a un metodo, che viene eseguita indipendentemente dal valore del primo operando:</span><span class="sxs-lookup"><span data-stu-id="71153-134">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

<span data-ttu-id="71153-135">L'[operatore OR condizionale logico](#conditional-logical-or-operator-) `||` calcola anche l'OR logico dei relativi operandi, ma non valuta il secondo operando se il primo operando restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="71153-135">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="71153-136">Per gli operandi dei tipi integrali, l'operatore `|` calcola l'[OR logico bit per bit](or-operator.md) dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-136">For the operands of integral types, the `|` operator computes [bitwise logical OR](or-operator.md) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="71153-137">Operatore AND condizionale logico&amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="71153-137">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="71153-138">L'operatore AND condizionale logico `&&`, chiamato anche operatore AND logico di "corto circuito", calcola l'AND logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-138">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="71153-139">Il risultato di `x && y` è `true` se `x` e `y` restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="71153-139">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="71153-140">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="71153-140">Otherwise, the result is `false`.</span></span> <span data-ttu-id="71153-141">Se il primo operando restituisce `false`, il secondo operando non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="71153-141">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="71153-142">Nell'esempio seguente il secondo operando dell'operatore `&&` è una chiamata a un metodo, che non viene eseguita se il primo operando restituisce `false`:</span><span class="sxs-lookup"><span data-stu-id="71153-142">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="71153-143">L'[operatore AND logico](#logical-and-operator-) `&` calcola anche l'AND logico dei relativi operandi, ma valuta sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-143">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="71153-144">Operatore OR condizionale logico ||</span><span class="sxs-lookup"><span data-stu-id="71153-144">Conditional logical OR operator ||</span></span>

<span data-ttu-id="71153-145">L'operatore OR condizionale logico `||`, chiamato anche operatore OR logico di "corto circuito", calcola l'OR logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-145">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="71153-146">Il risultato di `x || y` è `true` se `x` o `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="71153-146">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="71153-147">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="71153-147">Otherwise, the result is `false`.</span></span> <span data-ttu-id="71153-148">Se il primo operando restituisce `true`, il secondo operando non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="71153-148">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="71153-149">Nell'esempio seguente il secondo operando dell'operatore `||` è una chiamata a un metodo, che non viene eseguita se il primo operando restituisce `true`:</span><span class="sxs-lookup"><span data-stu-id="71153-149">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="71153-150">L'[operatore OR logico](#logical-or-operator-) `|` calcola anche l'OR logico dei relativi operandi, ma valuta sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="71153-150">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="71153-151">Operatori logici booleani nullable</span><span class="sxs-lookup"><span data-stu-id="71153-151">Nullable Boolean logical operators</span></span>

<span data-ttu-id="71153-152">Per gli operandi `bool?`, gli operatori `&` e `|` supportano la logica a tre valori.</span><span class="sxs-lookup"><span data-stu-id="71153-152">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="71153-153">La semantica di questi operatori è definita dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="71153-153">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="71153-154">x</span><span class="sxs-lookup"><span data-stu-id="71153-154">x</span></span>|<span data-ttu-id="71153-155">y</span><span class="sxs-lookup"><span data-stu-id="71153-155">y</span></span>|<span data-ttu-id="71153-156">x&y</span><span class="sxs-lookup"><span data-stu-id="71153-156">x&y</span></span>|<span data-ttu-id="71153-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="71153-157">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="71153-158">true</span><span class="sxs-lookup"><span data-stu-id="71153-158">true</span></span>|<span data-ttu-id="71153-159">true</span><span class="sxs-lookup"><span data-stu-id="71153-159">true</span></span>|<span data-ttu-id="71153-160">true</span><span class="sxs-lookup"><span data-stu-id="71153-160">true</span></span>|<span data-ttu-id="71153-161">true</span><span class="sxs-lookup"><span data-stu-id="71153-161">true</span></span>|  
|<span data-ttu-id="71153-162">true</span><span class="sxs-lookup"><span data-stu-id="71153-162">true</span></span>|<span data-ttu-id="71153-163">False</span><span class="sxs-lookup"><span data-stu-id="71153-163">false</span></span>|<span data-ttu-id="71153-164">false</span><span class="sxs-lookup"><span data-stu-id="71153-164">false</span></span>|<span data-ttu-id="71153-165">true</span><span class="sxs-lookup"><span data-stu-id="71153-165">true</span></span>|  
|<span data-ttu-id="71153-166">true</span><span class="sxs-lookup"><span data-stu-id="71153-166">true</span></span>|<span data-ttu-id="71153-167">Null</span><span class="sxs-lookup"><span data-stu-id="71153-167">null</span></span>|<span data-ttu-id="71153-168">Null</span><span class="sxs-lookup"><span data-stu-id="71153-168">null</span></span>|<span data-ttu-id="71153-169">true</span><span class="sxs-lookup"><span data-stu-id="71153-169">true</span></span>|  
|<span data-ttu-id="71153-170">False</span><span class="sxs-lookup"><span data-stu-id="71153-170">false</span></span>|<span data-ttu-id="71153-171">true</span><span class="sxs-lookup"><span data-stu-id="71153-171">true</span></span>|<span data-ttu-id="71153-172">False</span><span class="sxs-lookup"><span data-stu-id="71153-172">false</span></span>|<span data-ttu-id="71153-173">true</span><span class="sxs-lookup"><span data-stu-id="71153-173">true</span></span>|  
|<span data-ttu-id="71153-174">False</span><span class="sxs-lookup"><span data-stu-id="71153-174">false</span></span>|<span data-ttu-id="71153-175">False</span><span class="sxs-lookup"><span data-stu-id="71153-175">false</span></span>|<span data-ttu-id="71153-176">False</span><span class="sxs-lookup"><span data-stu-id="71153-176">false</span></span>|<span data-ttu-id="71153-177">False</span><span class="sxs-lookup"><span data-stu-id="71153-177">false</span></span>|  
|<span data-ttu-id="71153-178">False</span><span class="sxs-lookup"><span data-stu-id="71153-178">false</span></span>|<span data-ttu-id="71153-179">Null</span><span class="sxs-lookup"><span data-stu-id="71153-179">null</span></span>|<span data-ttu-id="71153-180">False</span><span class="sxs-lookup"><span data-stu-id="71153-180">false</span></span>|<span data-ttu-id="71153-181">Null</span><span class="sxs-lookup"><span data-stu-id="71153-181">null</span></span>|  
|<span data-ttu-id="71153-182">Null</span><span class="sxs-lookup"><span data-stu-id="71153-182">null</span></span>|<span data-ttu-id="71153-183">true</span><span class="sxs-lookup"><span data-stu-id="71153-183">true</span></span>|<span data-ttu-id="71153-184">Null</span><span class="sxs-lookup"><span data-stu-id="71153-184">null</span></span>|<span data-ttu-id="71153-185">true</span><span class="sxs-lookup"><span data-stu-id="71153-185">true</span></span>|  
|<span data-ttu-id="71153-186">Null</span><span class="sxs-lookup"><span data-stu-id="71153-186">null</span></span>|<span data-ttu-id="71153-187">False</span><span class="sxs-lookup"><span data-stu-id="71153-187">false</span></span>|<span data-ttu-id="71153-188">False</span><span class="sxs-lookup"><span data-stu-id="71153-188">false</span></span>|<span data-ttu-id="71153-189">Null</span><span class="sxs-lookup"><span data-stu-id="71153-189">null</span></span>|  
|<span data-ttu-id="71153-190">Null</span><span class="sxs-lookup"><span data-stu-id="71153-190">null</span></span>|<span data-ttu-id="71153-191">Null</span><span class="sxs-lookup"><span data-stu-id="71153-191">null</span></span>|<span data-ttu-id="71153-192">Null</span><span class="sxs-lookup"><span data-stu-id="71153-192">null</span></span>|<span data-ttu-id="71153-193">Null</span><span class="sxs-lookup"><span data-stu-id="71153-193">null</span></span>|  

<span data-ttu-id="71153-194">Il comportamento di questi operatori è diverso dal comportamento tipico degli operatori con tipi valore nullable.</span><span class="sxs-lookup"><span data-stu-id="71153-194">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="71153-195">In genere un operatore definito per gli operandi di un tipo valore può essere usato anche con gli operandi del tipo valore nullable corrispondente.</span><span class="sxs-lookup"><span data-stu-id="71153-195">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="71153-196">Un operatore di questo tipo produce `null` se uno qualsiasi dei suoi operandi è `null`.</span><span class="sxs-lookup"><span data-stu-id="71153-196">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="71153-197">Tuttavia gli operatori `&` e `|` possono produrre valori non Null anche se uno degli operandi è `null`.</span><span class="sxs-lookup"><span data-stu-id="71153-197">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="71153-198">Per altre informazioni sul comportamento degli operatori con i tipi valore nullable, vedere la sezione [Operatori](../../programming-guide/nullable-types/using-nullable-types.md#operators) dell'articolo [Uso dei tipi nullable](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="71153-198">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="71153-199">È anche possibile usare gli operatori `!` e `^` con gli operandi `bool?`, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="71153-199">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="71153-200">Gli operatori condizionali logici `&&` e `||` non supportano gli operandi `bool?`.</span><span class="sxs-lookup"><span data-stu-id="71153-200">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="71153-201">Assegnazione composta</span><span class="sxs-lookup"><span data-stu-id="71153-201">Compound assignment</span></span>

<span data-ttu-id="71153-202">Per un operatore binario `op`, un'espressione di assegnazione composta in formato</span><span class="sxs-lookup"><span data-stu-id="71153-202">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="71153-203">equivale a</span><span class="sxs-lookup"><span data-stu-id="71153-203">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="71153-204">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="71153-204">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="71153-205">Gli operatori `&`, `|` e `^` supportano l'assegnazione composta, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="71153-205">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="71153-206">Gli operatori condizionali logici `&&` e `||` non supportano l'assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="71153-206">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="71153-207">Precedenza tra gli operatori</span><span class="sxs-lookup"><span data-stu-id="71153-207">Operator precedence</span></span>

<span data-ttu-id="71153-208">Nell'elenco seguente gli operatori logici sono ordinati dalla precedenza più elevata a quella più bassa:</span><span class="sxs-lookup"><span data-stu-id="71153-208">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="71153-209">Operatore di negazione logica `!`</span><span class="sxs-lookup"><span data-stu-id="71153-209">Logical negation operator `!`</span></span>
- <span data-ttu-id="71153-210">Operatore AND logico `&`</span><span class="sxs-lookup"><span data-stu-id="71153-210">Logical AND operator `&`</span></span>
- <span data-ttu-id="71153-211">Operatore OR esclusivo logico `^`</span><span class="sxs-lookup"><span data-stu-id="71153-211">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="71153-212">Operatore OR logico `|`</span><span class="sxs-lookup"><span data-stu-id="71153-212">Logical OR operator `|`</span></span>
- <span data-ttu-id="71153-213">Operatore AND condizionale logico `&&`</span><span class="sxs-lookup"><span data-stu-id="71153-213">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="71153-214">Operatore OR condizionale logico `||`</span><span class="sxs-lookup"><span data-stu-id="71153-214">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="71153-215">Usare le parentesi, `()`, per cambiare l'ordine di valutazione imposto dalla precedenza tra gli operatori:</span><span class="sxs-lookup"><span data-stu-id="71153-215">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

<span data-ttu-id="71153-216">Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere [Operatori C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="71153-216">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="71153-217">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="71153-217">Operator overloadability</span></span>

<span data-ttu-id="71153-218">Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) degli operatori `!`, `&`, `|` e `^`.</span><span class="sxs-lookup"><span data-stu-id="71153-218">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="71153-219">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione composta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="71153-219">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="71153-220">Un tipo definito dall'utente non può eseguire in modo esplicito l'overload di un operatore di assegnazione composta.</span><span class="sxs-lookup"><span data-stu-id="71153-220">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="71153-221">Un tipo definito dall'utente non può eseguire l'overload degli operatori condizionali logici `&&` e `||`.</span><span class="sxs-lookup"><span data-stu-id="71153-221">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="71153-222">Tuttavia, se un tipo definito dall'utente esegue l'overload degli [operatori true e false](../keywords/true-false-operators.md) e dell'operatore `&` o `|` in un determinato modo, l'operazione `&&` o `||` può essere valutata per gli operandi di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="71153-222">However, if a user-defined type overloads the [true and false operators](../keywords/true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="71153-223">Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="71153-223">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="71153-224">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="71153-224">C# language specification</span></span>

<span data-ttu-id="71153-225">Per altre informazioni, vedere le sezioni seguenti delle [specifiche del linguaggio C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="71153-225">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="71153-226">Operatore di negazione logica</span><span class="sxs-lookup"><span data-stu-id="71153-226">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="71153-227">Operatori logici</span><span class="sxs-lookup"><span data-stu-id="71153-227">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="71153-228">Operatori logici condizionali</span><span class="sxs-lookup"><span data-stu-id="71153-228">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)

## <a name="see-also"></a><span data-ttu-id="71153-229">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71153-229">See also</span></span>

- [<span data-ttu-id="71153-230">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="71153-230">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="71153-231">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="71153-231">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="71153-232">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="71153-232">C# Operators</span></span>](index.md)
