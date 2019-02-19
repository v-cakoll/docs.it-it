---
title: '>>Operatore = - Riferimenti per C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 51914bb5e9ebffd5d868528b5a8d3072a956cea6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220913"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="99158-102">Operatore >>= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="99158-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="99158-103">Operatore di assegnazione di spostamento a destra.</span><span class="sxs-lookup"><span data-stu-id="99158-103">The right-shift assignment operator.</span></span>

<span data-ttu-id="99158-104">Un'espressione che usa l'operatore `>>=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="99158-104">An expression using the `>>=` operator, such as</span></span>

```csharp
x >>= y
```

<span data-ttu-id="99158-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="99158-105">is equivalent to</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="99158-106">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="99158-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="99158-107">L'[operatore `>>`](right-shift-operator.md) scorre verso destra il primo operando del numero di bit definito dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="99158-107">The [`>>` operator](right-shift-operator.md) shifts its first operand right by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="99158-108">Nell'esempio seguente viene illustrato l'uso dell'operatore `>>=`:</span><span class="sxs-lookup"><span data-stu-id="99158-108">The following example demonstrates the usage of the `>>=` operator:</span></span>

[!code-csharp-interactive[right shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="99158-109">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="99158-109">Operator overloadability</span></span>

<span data-ttu-id="99158-110">Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore `>>`](right-shift-operator.md), viene eseguito l'overload in modo implicito dell'operatore di assegnazione di scorrimento a destra `>>=`.</span><span class="sxs-lookup"><span data-stu-id="99158-110">If a user-defined type [overloads](../keywords/operator.md) the [`>>` operator](right-shift-operator.md), the right-shift assignment operator `>>=` is implicitly overloaded.</span></span> <span data-ttu-id="99158-111">Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di scorrimento a destra.</span><span class="sxs-lookup"><span data-stu-id="99158-111">A user-defined type cannot explicitly overload the right-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="99158-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="99158-112">C# language specification</span></span>

<span data-ttu-id="99158-113">Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="99158-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="99158-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99158-114">See also</span></span>

- [<span data-ttu-id="99158-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="99158-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="99158-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="99158-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="99158-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="99158-117">C# operators</span></span>](index.md)