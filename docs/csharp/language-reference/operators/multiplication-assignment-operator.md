---
title: Operatore *= - Riferimenti per C#
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 70461f79e714e44354fe4137e5360769fa048d3e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967386"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a07dc-102">Operatore \*= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a07dc-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="a07dc-103">Operatore di assegnazione di moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="a07dc-103">The multiplication assignment operator.</span></span>

<span data-ttu-id="a07dc-104">Un'espressione che usa l'operatore `*=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="a07dc-104">An expression using the `*=` operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="a07dc-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="a07dc-105">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="a07dc-106">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a07dc-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="a07dc-107">Per i tipi numerici, l'[operatore \*](multiplication-operator.md) calcola il prodotto dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="a07dc-107">For numeric types, the [\* operator](multiplication-operator.md) computes the product of its operands.</span></span>

<span data-ttu-id="a07dc-108">Nell'esempio seguente viene illustrato l'uso dell'operatore `*=`:</span><span class="sxs-lookup"><span data-stu-id="a07dc-108">The following example demonstrates the usage of the `*=` operator:</span></span>

[!code-csharp-interactive[multiply and assign](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#MultiplyAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="a07dc-109">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="a07dc-109">Operator overloadability</span></span>

<span data-ttu-id="a07dc-110">Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore di moltiplicazione](multiplication-operator.md) `*`, viene eseguito l'overload in modo implicito dell'operatore di assegnazione di moltiplicazione `*=`.</span><span class="sxs-lookup"><span data-stu-id="a07dc-110">If a user-defined type [overloads](../keywords/operator.md) the [multiplication operator](multiplication-operator.md) `*`, the multiplication assignment operator `*=` is implicitly overloaded.</span></span> <span data-ttu-id="a07dc-111">Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="a07dc-111">A user-defined type cannot explicitly overload the multiplication assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a07dc-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a07dc-112">C# language specification</span></span>

<span data-ttu-id="a07dc-113">Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a07dc-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a07dc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a07dc-114">See also</span></span>

- [<span data-ttu-id="a07dc-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a07dc-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a07dc-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a07dc-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a07dc-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a07dc-117">C# Operators</span></span>](index.md)
