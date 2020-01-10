---
title: Parola chiave contestuale when - Riferimenti per C#
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: 6a61c42ba2d01e84ffae376bf95c99877437be85
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712832"
---
# <a name="when-c-reference"></a><span data-ttu-id="4429f-102">when (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4429f-102">when (C# Reference)</span></span>

<span data-ttu-id="4429f-103">È possibile usare la parola chiave contestuale `when` per specificare una condizione di filtro in due contesti:</span><span class="sxs-lookup"><span data-stu-id="4429f-103">You can use the `when` contextual keyword to specify a filter condition in two contexts:</span></span>

- <span data-ttu-id="4429f-104">Nell'istruzione `catch` di un blocco [try/catch](try-catch.md) o [try/catch/finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="4429f-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="4429f-105">Nell'etichetta `case` di un'istruzione [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="4429f-105">In the `case` label of a [switch](switch.md) statement.</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="4429f-106">`when` in un'istruzione `catch`</span><span class="sxs-lookup"><span data-stu-id="4429f-106">`when` in a `catch` statement</span></span>

<span data-ttu-id="4429f-107">A partire da C# 6 `when` può essere usata in un'istruzione `catch` per specificare una condizione che deve essere vera per eseguire il gestore di una determinata eccezione.</span><span class="sxs-lookup"><span data-stu-id="4429f-107">Starting with C# 6, `when` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="4429f-108">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="4429f-108">Its syntax is:</span></span>

```csharp
catch (ExceptionType [e]) when (expr)
```

<span data-ttu-id="4429f-109">dove *expr* è un'espressione che dà come risultato un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="4429f-109">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="4429f-110">Se restituisce `true`, il gestore di eccezioni viene eseguito, se restituisce `false`, non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="4429f-110">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span>

<span data-ttu-id="4429f-111">Nell'esempio seguente viene usata la parola chiave `when` per eseguire in modo condizionale i gestori per un elemento <xref:System.Net.Http.HttpRequestException> in base al testo del messaggio dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4429f-111">The following example uses the `when` keyword to conditionally execute handlers for an <xref:System.Net.Http.HttpRequestException> depending on the text of the exception message.</span></span>

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a><span data-ttu-id="4429f-112">`when` in un'istruzione `switch`</span><span class="sxs-lookup"><span data-stu-id="4429f-112">`when` in a `switch` statement</span></span>

<span data-ttu-id="4429f-113">A partire da C# 7.0 non è più necessario che le etichette `case` siano reciprocamente esclusive e l'ordine in cui le etichette `case` appaiono in un'istruzione `switch` può determinare quale blocco switch eseguire.</span><span class="sxs-lookup"><span data-stu-id="4429f-113">Starting with C# 7.0, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="4429f-114">La parola chiave `when` può essere usata per specificare una condizione di filtro che fa sì che l'etichetta case associata sia vera solo se è vera anche la condizione di filtro.</span><span class="sxs-lookup"><span data-stu-id="4429f-114">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="4429f-115">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="4429f-115">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```

<span data-ttu-id="4429f-116">dove *expr* è un modello costante o un modello del tipo che viene confrontato con l'espressione di corrispondenza e *when-condition* è qualsiasi espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="4429f-116">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span>

<span data-ttu-id="4429f-117">Nell'esempio seguente viene usata la parola chiave `when` per testare gli oggetti `Shape` che hanno un'area pari a zero, nonché una varietà di oggetti `Shape` che hanno un'area maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="4429f-117">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span>

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a><span data-ttu-id="4429f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4429f-118">See also</span></span>

- [<span data-ttu-id="4429f-119">Istruzione switch</span><span class="sxs-lookup"><span data-stu-id="4429f-119">switch statement</span></span>](switch.md)
- [<span data-ttu-id="4429f-120">Istruzione try/catch</span><span class="sxs-lookup"><span data-stu-id="4429f-120">try/catch statement</span></span>](try-catch.md)
- [<span data-ttu-id="4429f-121">Istruzione try/catch/finally</span><span class="sxs-lookup"><span data-stu-id="4429f-121">try/catch/finally statement</span></span>](try-catch-finally.md)
