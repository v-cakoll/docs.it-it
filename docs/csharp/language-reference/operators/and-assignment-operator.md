---
title: Operatore &amp;= (Riferimenti per C#)
ms.date: 10/29/2018
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 8ce27c999cf21a9059ba23ee3c86b8fa024c7341
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "50980609"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="e93c8-102">Operatore &amp;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e93c8-102">&amp;= Operator (C# Reference)</span></span>

<span data-ttu-id="e93c8-103">Operatore di assegnazione AND.</span><span class="sxs-lookup"><span data-stu-id="e93c8-103">The AND assignment operator.</span></span>

<span data-ttu-id="e93c8-104">Un'espressione che usa l'operatore `&=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="e93c8-104">An expression using the `&=` operator, such as</span></span>

```csharp
x &= y
```

<span data-ttu-id="e93c8-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="e93c8-105">is equivalent to</span></span>

```csharp
x = x & y
```

<span data-ttu-id="e93c8-106">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="e93c8-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="e93c8-107">Per gli operandi di numeri interi, l'[operatore `&`](and-operator.md) calcola l'AND logico bit per bit dei relativi operandi; per gli operandi [bool](../keywords/bool.md), calcola l'AND logico dei relativi operandi.</span><span class="sxs-lookup"><span data-stu-id="e93c8-107">For integer operands, the [`&` operator](and-operator.md) computes the bitwise logical AND of its operands; for [bool](../keywords/bool.md) operands, it computes the logical AND of its operands.</span></span>

<span data-ttu-id="e93c8-108">Nell'esempio seguente viene illustrato l'uso dell'operatore `&=`:</span><span class="sxs-lookup"><span data-stu-id="e93c8-108">The following example demonstrates the usage of the `&=` operator:</span></span>

[!code-csharp-interactive[AND assignment example](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#AndAssignmentExample)]

## <a name="operator-overloadability"></a><span data-ttu-id="e93c8-109">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="e93c8-109">Operator overloadability</span></span>

<span data-ttu-id="e93c8-110">Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore `&`](and-operator.md), viene eseguito l'overload in modo implicito dell'operatore di assegnazione `&=`.</span><span class="sxs-lookup"><span data-stu-id="e93c8-110">If a user-defined type [overloads](../keywords/operator.md) the [`&` operator](and-operator.md), the AND assignment operator `&=` is implicitly overloaded.</span></span> <span data-ttu-id="e93c8-111">Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione AND.</span><span class="sxs-lookup"><span data-stu-id="e93c8-111">A user-defined type cannot explicitly overload the AND assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e93c8-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e93c8-112">C# language specification</span></span>

<span data-ttu-id="e93c8-113">Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="e93c8-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e93c8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e93c8-114">See also</span></span>

- [<span data-ttu-id="e93c8-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e93c8-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e93c8-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e93c8-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e93c8-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="e93c8-117">C# Operators</span></span>](index.md)
