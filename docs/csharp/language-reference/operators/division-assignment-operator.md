---
title: Operatore /= - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: ed4dd6c0c944b77543aae4de8d51534b4df4f4ef
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286520"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b7200-102">Operatore /= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b7200-102">/= Operator (C# Reference)</span></span>

<span data-ttu-id="b7200-103">Operatore di assegnazione di divisione.</span><span class="sxs-lookup"><span data-stu-id="b7200-103">The division assignment operator.</span></span>

<span data-ttu-id="b7200-104">Un'espressione che usa l'operatore `/=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="b7200-104">An expression using the `/=` operator, such as</span></span>

```csharp
x /= y
```

<span data-ttu-id="b7200-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="b7200-105">is equivalent to</span></span>

```csharp
x = x / y
```

<span data-ttu-id="b7200-106">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="b7200-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="b7200-107">L'[operatore di divisione](division-operator.md) `/` divide il primo operando per il secondo operando.</span><span class="sxs-lookup"><span data-stu-id="b7200-107">The [division operator](division-operator.md) `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="b7200-108">È supportato da tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="b7200-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="b7200-109">Nell'esempio seguente viene illustrato l'uso dell'operatore `/=`:</span><span class="sxs-lookup"><span data-stu-id="b7200-109">The following example demonstrates the usage of the `/=` operator:</span></span>

[!code-csharp-interactive[divide and assign](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#DivisionAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="b7200-110">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="b7200-110">Operator overloadability</span></span>

<span data-ttu-id="b7200-111">Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore di divisione](division-operator.md) `/`, viene eseguito l'overload in modo implicito dell'operatore di assegnazione di divisione `/=`.</span><span class="sxs-lookup"><span data-stu-id="b7200-111">If a user-defined type [overloads](../keywords/operator.md) the [division operator](division-operator.md) `/`, the division assignment operator `/=` is implicitly overloaded.</span></span> <span data-ttu-id="b7200-112">Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di divisione.</span><span class="sxs-lookup"><span data-stu-id="b7200-112">A user-defined type cannot explicitly overload the division assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b7200-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b7200-113">C# language specification</span></span>

<span data-ttu-id="b7200-114">Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="b7200-114">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b7200-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7200-115">See also</span></span>

- [<span data-ttu-id="b7200-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b7200-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b7200-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b7200-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b7200-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b7200-118">C# Operators</span></span>](index.md)
