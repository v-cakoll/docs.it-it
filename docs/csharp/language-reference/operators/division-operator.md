---
title: Operatore / - Riferimenti per C#
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 45bcd64b60e7d13f389064faefeda815ea1f32c9
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286533"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="64297-102">Operatore / (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="64297-102">/ Operator (C# Reference)</span></span>

<span data-ttu-id="64297-103">L'operatore di divisione `/` divide il primo operando per il secondo operando.</span><span class="sxs-lookup"><span data-stu-id="64297-103">The division operator `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="64297-104">Tutti i tipi numerici supportano l'operatore di divisione.</span><span class="sxs-lookup"><span data-stu-id="64297-104">All numeric types support the division operator.</span></span>

## <a name="integer-division"></a><span data-ttu-id="64297-105">Divisione di interi</span><span class="sxs-lookup"><span data-stu-id="64297-105">Integer division</span></span>

<span data-ttu-id="64297-106">Per gli operandi di tipo Integer, il risultato dell'operatore `/` è di tipo Integer ed è uguale al quoziente dei due operandi arrotondato allo zero:</span><span class="sxs-lookup"><span data-stu-id="64297-106">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#Integer)]

<span data-ttu-id="64297-107">Per ottenere il quoziente dei due operandi come numero a virgola mobile, usare il tipo `float`, `double`,o `decimal`:</span><span class="sxs-lookup"><span data-stu-id="64297-107">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#IntegerAsFloatingPoint)]

## <a name="floating-point-division"></a><span data-ttu-id="64297-108">Divisione a virgola mobile</span><span class="sxs-lookup"><span data-stu-id="64297-108">Floating-point division</span></span>

<span data-ttu-id="64297-109">Per i tipi `float`, `double` e `decimal`, il risultato dell'operatore `/` è il quoziente dei due operandi:</span><span class="sxs-lookup"><span data-stu-id="64297-109">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#FloatingPoint)]

<span data-ttu-id="64297-110">Se uno degli operandi è `decimal`, un altro operando non può essere né `float` né `double`, perché né `float` né `double` è convertibile implicitamente in `decimal`.</span><span class="sxs-lookup"><span data-stu-id="64297-110">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="64297-111">È necessario convertire esplicitamente l'operando `float` o `double` nel tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="64297-111">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="64297-112">Per altre informazioni sulle conversioni implicite tra tipi numerici, vedere [Tabella delle conversioni numeriche implicite](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="64297-112">For more information about implicit conversions between numeric types, see [Implicit numeric conversions table](../keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="64297-113">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="64297-113">Operator overloadability</span></span>

<span data-ttu-id="64297-114">I tipi definiti dall'utente possono eseguire l'[overload](../keywords/operator.md) dell'operatore `/`.</span><span class="sxs-lookup"><span data-stu-id="64297-114">User-defined types can [overload](../keywords/operator.md) the `/` operator.</span></span> <span data-ttu-id="64297-115">Quando viene eseguito l'overload dell'operatore `/`, viene eseguito in modo implicito anche l'overload dell'[operatore di assegnazione di divisione](division-assignment-operator.md) `/=`.</span><span class="sxs-lookup"><span data-stu-id="64297-115">When the `/` operator is overloaded, the [division assignment operator](division-assignment-operator.md) `/=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="64297-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="64297-116">C# language specification</span></span>

<span data-ttu-id="64297-117">Per altre informazioni, vedere la sezione [Operatore di divisione](~/_csharplang/spec/expressions.md#division-operator) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="64297-117">For more information, see the [Division operator](~/_csharplang/spec/expressions.md#division-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="64297-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64297-118">See also</span></span>

- [<span data-ttu-id="64297-119">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="64297-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="64297-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="64297-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="64297-121">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="64297-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="64297-122">Operatore %</span><span class="sxs-lookup"><span data-stu-id="64297-122">% Operator</span></span>](remainder-operator.md)
