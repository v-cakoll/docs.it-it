---
title: Operatore += - Riferimenti per C#
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: 5d48f2fe53a9bb6f781f8d35f1e0983bcaa30f88
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240931"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5abd0-102">Operatore += (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5abd0-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="5abd0-103">Operatore di assegnazione di addizione.</span><span class="sxs-lookup"><span data-stu-id="5abd0-103">The addition assignment operator.</span></span>

<span data-ttu-id="5abd0-104">Un'espressione che usa l'operatore `+=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="5abd0-104">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="5abd0-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="5abd0-105">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="5abd0-106">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="5abd0-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="5abd0-107">Per i tipi numerici, l'[operatore addizione](addition-operator.md) `+` calcola la somma dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="5abd0-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="5abd0-108">Quando uno o entrambi gli operandi sono di tipo [stringa](../keywords/string.md), concatena le rappresentazioni di stringa dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="5abd0-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="5abd0-109">Per i tipi delegati, l'operatore `+` restituisce una nuova istanza di delegato che è una combinazione dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="5abd0-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="5abd0-110">È anche possibile usare l'operatore `+=` per specificare un metodo del gestore eventi quando si sottoscrive un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="5abd0-110">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="5abd0-111">Per altre informazioni, vedere [Procedura: Eseguire e annullare la sottoscrizione a eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="5abd0-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="5abd0-112">Nell'esempio seguente viene illustrato l'uso dell'operatore `+=`:</span><span class="sxs-lookup"><span data-stu-id="5abd0-112">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="5abd0-113">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="5abd0-113">Operator overloadability</span></span>

<span data-ttu-id="5abd0-114">Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore addizione](addition-operator.md) `+`, viene eseguito l'overload in modo implicito dell'operatore di assegnazione di addizione `+=`.</span><span class="sxs-lookup"><span data-stu-id="5abd0-114">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span> <span data-ttu-id="5abd0-115">Un tipo definito dall'utente non può eseguire l'overload in modo esplicito dell'operatore di assegnazione di addizione.</span><span class="sxs-lookup"><span data-stu-id="5abd0-115">A user-defined type cannot explicitly overload the addition assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5abd0-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="5abd0-116">C# language specification</span></span>

<span data-ttu-id="5abd0-117">Per altre informazioni, vedere le sezioni [Assegnazione composta](~/_csharplang/spec/expressions.md#compound-assignment) e [Assegnazione di eventi](~/_csharplang/spec/expressions.md#event-assignment) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="5abd0-117">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) and [Event assignment](~/_csharplang/spec/expressions.md#event-assignment) sections of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5abd0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5abd0-118">See also</span></span>

- [<span data-ttu-id="5abd0-119">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5abd0-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5abd0-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5abd0-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5abd0-121">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="5abd0-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="5abd0-122">Eventi</span><span class="sxs-lookup"><span data-stu-id="5abd0-122">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="5abd0-123">Delegati</span><span class="sxs-lookup"><span data-stu-id="5abd0-123">Delegates</span></span>](../../programming-guide/delegates/index.md)
