---
title: Operatore <<= - Riferimenti per C#
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: d2105fbee4ddfe1b2cb3325d82b0f2f8c5559297
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219451"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6377f-102">Operatore \<\<= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6377f-102">\<\<= operator (C# Reference)</span></span>

<span data-ttu-id="6377f-103">Operatore di assegnazione di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="6377f-103">The left-shift assignment operator.</span></span>

<span data-ttu-id="6377f-104">Un'espressione che usa l'operatore `<<=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="6377f-104">An expression using the `<<=` operator, such as</span></span>

```csharp
x <<= y
```

<span data-ttu-id="6377f-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="6377f-105">is equivalent to</span></span>

```csharp
x = x << y
```

<span data-ttu-id="6377f-106">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="6377f-106">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="6377f-107">L'[operatore `<<`](left-shift-operator.md) scorre verso sinistra il primo operando del numero di bit specificato dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="6377f-107">The [`<<` operator](left-shift-operator.md) shifts its first operand left by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="6377f-108">Nell'esempio seguente viene illustrato l'uso dell'operatore `<<=`:</span><span class="sxs-lookup"><span data-stu-id="6377f-108">The following example demonstrates the usage of the `<<=` operator:</span></span>

[!code-csharp-interactive[left shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftAssignment)]

## <a name="operator-overloadability"></a><span data-ttu-id="6377f-109">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="6377f-109">Operator overloadability</span></span>

<span data-ttu-id="6377f-110">Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore `<<`](left-shift-operator.md), viene eseguito l'overload in modo implicito dell'operatore di assegnazione di scorrimento a sinistra `<<=`.</span><span class="sxs-lookup"><span data-stu-id="6377f-110">If a user-defined type [overloads](../keywords/operator.md) the [`<<` operator](left-shift-operator.md), the left-shift assignment operator `<<=` is implicitly overloaded.</span></span> <span data-ttu-id="6377f-111">Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di scorrimento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="6377f-111">A user-defined type cannot explicitly overload the left-shift assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6377f-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6377f-112">C# language specification</span></span>

<span data-ttu-id="6377f-113">Per altre informazioni, vedere la sezione [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="6377f-113">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6377f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6377f-114">See also</span></span>

- [<span data-ttu-id="6377f-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="6377f-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6377f-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6377f-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6377f-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="6377f-117">C# Operators</span></span>](index.md)
