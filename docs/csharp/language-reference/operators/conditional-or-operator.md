---
title: Operatore || (Riferimenti per C#)
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: a391078372e4ec0a3882bed4515733adedffb547
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "42925540"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a33f0-102">Operatore || (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a33f0-102">|| Operator (C# Reference)</span></span>

<span data-ttu-id="a33f0-103">L'operatore OR logico condizionale `||`, chiamato anche operatore OR logico di "corto circuito", calcola l'OR logico dei relativi operandi [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="a33f0-103">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="a33f0-104">Il risultato di `x || y` è `true` se `x` o `y` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="a33f0-104">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="a33f0-105">In caso contrario, il risultato è `false`.</span><span class="sxs-lookup"><span data-stu-id="a33f0-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="a33f0-106">Se il primo operando restituisce `true`, il secondo operando non viene valutato e il risultato dell'operazione è `true`.</span><span class="sxs-lookup"><span data-stu-id="a33f0-106">If the first operand evaluates to `true`, the second operand is not evaluated and the result of operation is `true`.</span></span> <span data-ttu-id="a33f0-107">L'esempio seguente illustra questo comportamento:</span><span class="sxs-lookup"><span data-stu-id="a33f0-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

<span data-ttu-id="a33f0-108">L'[operatore OR logico](or-operator.md) `|` calcola anche l'OR logico dei relativi operandi `bool`, ma valuta sempre entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="a33f0-108">The [logical OR operator](or-operator.md) `|` also computes the logical OR of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a33f0-109">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="a33f0-109">Operator overloadability</span></span>

<span data-ttu-id="a33f0-110">Un tipo definito dall'utente non può eseguire l'overload dell'operatore OR logico condizionale.</span><span class="sxs-lookup"><span data-stu-id="a33f0-110">A user-defined type cannot overload the conditional logical OR operator.</span></span> <span data-ttu-id="a33f0-111">Tuttavia, se un tipo definito dall'utente esegue l'overload degli operatori [OR logico](or-operator.md), [true](../keywords/true-operator.md) e [false](../keywords/false-operator.md) in un determinato modo, l'operazione `||` può essere valutata per gli operandi di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="a33f0-111">However, if a user-defined type overloads the [logical OR](or-operator.md), [true](../keywords/true-operator.md), and [false](../keywords/false-operator.md) operators in a certain way, the `||` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="a33f0-112">Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a33f0-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a33f0-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a33f0-113">C# language specification</span></span>

<span data-ttu-id="a33f0-114">Per altre informazioni, vedere la sezione [Operatori logici condizionali definiti dall'utente](~/_csharplang/spec/expressions.md#conditional-logical-operators) di [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a33f0-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a33f0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a33f0-115">See also</span></span>

- [<span data-ttu-id="a33f0-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a33f0-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a33f0-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a33f0-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a33f0-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a33f0-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="a33f0-119">Operatore &&</span><span class="sxs-lookup"><span data-stu-id="a33f0-119">&& operator</span></span>](conditional-and-operator.md)
- [<span data-ttu-id="a33f0-120">Operatore !</span><span class="sxs-lookup"><span data-stu-id="a33f0-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="a33f0-121">Operatore |</span><span class="sxs-lookup"><span data-stu-id="a33f0-121">| operator</span></span>](or-operator.md)
