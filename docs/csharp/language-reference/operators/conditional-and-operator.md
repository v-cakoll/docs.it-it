---
title: Operatore &amp;&amp; - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 82442f50275f21e0a0748951dc50628a8d7e11bb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243588"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="55ab4-102">&amp;&amp; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="55ab4-102">&amp;&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="55ab4-103">L'operatore AND logico condizionale `&&`, chiamato anche operatore AND logico di "corto circuito", calcola l'AND logico dei relativi operandi [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="55ab4-103">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="55ab4-104">Il risultato di `x && y` è `true` se `x` e `y` restituiscono `true`.</span><span class="sxs-lookup"><span data-stu-id="55ab4-104">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="55ab4-105">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="55ab4-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="55ab4-106">Se il primo operando restituisce `false`, il secondo operando non viene valutato e il risultato dell'operazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="55ab4-106">If the first operand evaluates to `false`, the second operand is not evaluated and the result of operation is `false`.</span></span> <span data-ttu-id="55ab4-107">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="55ab4-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

<span data-ttu-id="55ab4-108">L'[operatore AND logico](and-operator.md) `&` calcola anche l'AND logico dei relativi operandi `bool`, ma valuta sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="55ab4-108">The [logical AND operator](and-operator.md) `&` also computes the logical AND of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="55ab4-109">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="55ab4-109">Operator overloadability</span></span>

<span data-ttu-id="55ab4-110">Un tipo definito dall'utente non può eseguire l'overload dell'operatore AND logico condizionale.</span><span class="sxs-lookup"><span data-stu-id="55ab4-110">A user-defined type cannot overload the conditional logical AND operator.</span></span> <span data-ttu-id="55ab4-111">Tuttavia, se un tipo definito dall'utente esegue l'overload degli operatori [AND logico](and-operator.md), [true e false](../keywords/true-false-operators.md) in un determinato modo, l'operazione `&&` può essere valutata per gli operandi di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="55ab4-111">However, if a user-defined type overloads the [logical AND](and-operator.md) and [true and false operators](../keywords/true-false-operators.md) in a certain way, the `&&` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="55ab4-112">Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="55ab4-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="55ab4-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="55ab4-113">C# language specification</span></span>

<span data-ttu-id="55ab4-114">Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="55ab4-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="55ab4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55ab4-115">See also</span></span>

- [<span data-ttu-id="55ab4-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="55ab4-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="55ab4-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="55ab4-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="55ab4-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="55ab4-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="55ab4-119">Operatore ||</span><span class="sxs-lookup"><span data-stu-id="55ab4-119">|| operator</span></span>](conditional-or-operator.md)
- [<span data-ttu-id="55ab4-120">Operatore \!</span><span class="sxs-lookup"><span data-stu-id="55ab4-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="55ab4-121">Operatore &</span><span class="sxs-lookup"><span data-stu-id="55ab4-121">& operator</span></span>](and-operator.md)
