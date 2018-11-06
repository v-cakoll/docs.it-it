---
title: Operatore += (Riferimenti per C#)
ms.date: 10/22/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ee335e3e2e7d352d4e26b802bad2b08a05c666ab
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192031"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="11a80-102">Operatore += (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="11a80-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="11a80-103">Operatore di assegnazione di addizione.</span><span class="sxs-lookup"><span data-stu-id="11a80-103">The addition assignment operator.</span></span>

<span data-ttu-id="11a80-104">Un'espressione che usa l'operatore `+=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="11a80-104">An expression using the `+=` operator, such as</span></span>  

```csharp
x += y
```  

<span data-ttu-id="11a80-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="11a80-105">is equivalent to</span></span>  

```csharp
x = x + y
```  

<span data-ttu-id="11a80-106">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="11a80-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="11a80-107">Per i tipi numerici, l'[operatore addizione](addition-operator.md) `+` calcola la somma dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="11a80-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="11a80-108">Quando uno o entrambi gli operandi sono di tipo [stringa](../keywords/string.md), concatena le rappresentazioni di stringa dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="11a80-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="11a80-109">Per i tipi delegati, l'operatore `+` restituisce una nuova istanza di delegato che è una combinazione dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="11a80-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="11a80-110">Se un tipo definito dall'utente esegue l'[overload](../keywords/operator.md) dell'[operatore addizione](addition-operator.md) `+`, viene eseguito l'overload in modo implicito dell'operatore di assegnazione di addizione `+=`.</span><span class="sxs-lookup"><span data-stu-id="11a80-110">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span>

<span data-ttu-id="11a80-111">È anche possibile usare l'operatore `+=` per specificare un metodo del gestore eventi quando si sottoscrive un [evento](../keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="11a80-111">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="11a80-112">Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="11a80-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="11a80-113">Nell'esempio seguente viene illustrato l'uso dell'operatore `+=`:</span><span class="sxs-lookup"><span data-stu-id="11a80-113">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]
  
## <a name="see-also"></a><span data-ttu-id="11a80-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11a80-114">See also</span></span>

- [<span data-ttu-id="11a80-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="11a80-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="11a80-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="11a80-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="11a80-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="11a80-117">C# Operators</span></span>](index.md)
- [<span data-ttu-id="11a80-118">Eventi</span><span class="sxs-lookup"><span data-stu-id="11a80-118">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="11a80-119">Delegati</span><span class="sxs-lookup"><span data-stu-id="11a80-119">Delegates</span></span>](../../programming-guide/delegates/index.md)
