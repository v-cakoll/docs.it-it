---
title: Operatore != - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: 939b5664dba4345e62a43fb2f8d4d5379659d6aa
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610177"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="699c8-102">Operatore != (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="699c8-102">!= Operator (C# Reference)</span></span>

<span data-ttu-id="699c8-103">L'operatore di disuguaglianza `!=` restituisce `true` se gli operandi sono diversi, `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="699c8-103">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="699c8-104">Per gli operandi dei [tipi predefiniti](../keywords/built-in-types-table.md), l'espressione `x != y` produce lo stesso risultato dell'espressione `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="699c8-104">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="699c8-105">Per altre informazioni, vedere l'articolo [Operatore ==](equality-comparison-operator.md).</span><span class="sxs-lookup"><span data-stu-id="699c8-105">For more information, see the [== Operator](equality-comparison-operator.md) article.</span></span>

<span data-ttu-id="699c8-106">Nell'esempio seguente viene illustrato l'uso dell'operatore `!=`:</span><span class="sxs-lookup"><span data-stu-id="699c8-106">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="699c8-107">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="699c8-107">Operator overloadability</span></span>

<span data-ttu-id="699c8-108">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `!=`.</span><span class="sxs-lookup"><span data-stu-id="699c8-108">User-defined types can [overload](../keywords/operator.md) the `!=` operator.</span></span> <span data-ttu-id="699c8-109">Se un tipo esegue l'overload dell'operatore di disuguaglianza `!=`, deve anche eseguire l'overload dell'[operatore di uguaglianza](equality-comparison-operator.md) `==`.</span><span class="sxs-lookup"><span data-stu-id="699c8-109">If a type overloads the inequality operator `!=`, it must also overload the [equality operator](equality-comparison-operator.md) `==`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="699c8-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="699c8-110">C# language specification</span></span>

<span data-ttu-id="699c8-111">Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="699c8-111">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="699c8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="699c8-112">See also</span></span>

- [<span data-ttu-id="699c8-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="699c8-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="699c8-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="699c8-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="699c8-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="699c8-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="699c8-116">Confronti di uguaglianza</span><span class="sxs-lookup"><span data-stu-id="699c8-116">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
