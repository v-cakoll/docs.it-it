---
title: '! - operatore - Riferimenti per C#'
ms.custom: seodec18
ms.date: 02/14/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 464bd658c9bf430191d84d3d5ad8d57173ab87c5
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303712"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="603af-103">!</span><span class="sxs-lookup"><span data-stu-id="603af-103">!</span></span> <span data-ttu-id="603af-104">operator (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="603af-104">operator (C# Reference)</span></span>

<span data-ttu-id="603af-105">L'operatore di negazione logico `!` è un operatore unario che calcola la negazione logica del relativo operando [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="603af-105">The logical negation operator `!` is a unary operator that computes logical negation of its [bool](../keywords/bool.md) operand.</span></span> <span data-ttu-id="603af-106">Vale a dire, produce `true`, se l'operando è `false` e `false` se l'operando è `true`:</span><span class="sxs-lookup"><span data-stu-id="603af-106">That is, it produces `true`, if the operand is `false`, and `false`, if the operand is `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalNegationExamples.cs#Example)]

## <a name="operator-overloadability"></a><span data-ttu-id="603af-107">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="603af-107">Operator overloadability</span></span>

<span data-ttu-id="603af-108">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `!`.</span><span class="sxs-lookup"><span data-stu-id="603af-108">User-defined types can [overload](../keywords/operator.md) the `!` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="603af-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="603af-109">C# language specification</span></span>

<span data-ttu-id="603af-110">Per altre informazioni, vedere la sezione [Operatore di negazione logico](~/_csharplang/spec/expressions.md#logical-negation-operator) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="603af-110">For more information, see the [Logical negation operator](~/_csharplang/spec/expressions.md#logical-negation-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="603af-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="603af-111">See also</span></span>

- [<span data-ttu-id="603af-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="603af-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="603af-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="603af-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="603af-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="603af-114">C# Operators</span></span>](index.md)