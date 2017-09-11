---
title: when (Riferimenti per C#)
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 9ad2eff6eb527f00ce23f463e811aa748def62d0
ms.openlocfilehash: c391c6de51d41577d61278f43d58fade5b7c139f
ms.contentlocale: it-it
ms.lasthandoff: 08/11/2017

---
 # <a name="when-c-reference"></a><span data-ttu-id="9164a-102">when (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9164a-102">when (C# Reference)</span></span>

<span data-ttu-id="9164a-103">È possibile usare la parola chiave contestuale `when` per specificare una condizione di filtro in due contesti:</span><span class="sxs-lookup"><span data-stu-id="9164a-103">You can use the `when` contextual keyword to specify a filter condition in two contexts:</span></span>

- <span data-ttu-id="9164a-104">Nell'istruzione `catch` di un blocco [try/catch](try-catch.md) o [try/catch/finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="9164a-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="9164a-105">Nell'etichetta `case` di un'istruzione [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="9164a-105">In the `case` label of a [switch](switch.md) statement.</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="9164a-106">`when` in un'istruzione `catch`</span><span class="sxs-lookup"><span data-stu-id="9164a-106">`when` in a `catch` statement</span></span>

<span data-ttu-id="9164a-107">A partire da C# 6 `When` può essere usata in un'istruzione `catch` per specificare una condizione che deve essere vera per eseguire il gestore di una determinata eccezione.</span><span class="sxs-lookup"><span data-stu-id="9164a-107">Starting with C# 6, `When` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="9164a-108">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="9164a-108">Its syntax is:</span></span>

```csharp
catch ExceptionType [e] when (expr)
```
<span data-ttu-id="9164a-109">dove *expr* è un'espressione che dà come risultato un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="9164a-109">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="9164a-110">Se restituisce `true`, il gestore di eccezioni viene eseguito, se restituisce `false`, non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="9164a-110">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span> 

<span data-ttu-id="9164a-111">Nell'esempio seguente viene usata la parola chiave `when` per eseguire in modo condizionale i gestori per un elemento @System.Net.HttpRequestException in base al testo del messaggio dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9164a-111">The following example uses the `when` keyword to conditionally execute handlers for an @System.Net.HttpRequestException depending on the text of the exception message.</span></span>

 <span data-ttu-id="9164a-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span><span class="sxs-lookup"><span data-stu-id="9164a-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span></span>  
  
## <a name="when-in-a-switch-statement"></a><span data-ttu-id="9164a-113">`when` in un'istruzione `switch`</span><span class="sxs-lookup"><span data-stu-id="9164a-113">`when` in a `switch` statement</span></span>

<span data-ttu-id="9164a-114">A partire da 7 non è più necessario che le etichette `case` siano reciprocamente esclusive e l'ordine in cui le etichette `case` appaiono in un'istruzione `switch` può determinare quale blocco switch eseguire.</span><span class="sxs-lookup"><span data-stu-id="9164a-114">Starting with 7, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="9164a-115">La parola chiave `when` può essere usata per specificare una condizione di filtro che fa sì che l'etichetta case associata sia vera solo se è vera anche la condizione di filtro.</span><span class="sxs-lookup"><span data-stu-id="9164a-115">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="9164a-116">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="9164a-116">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```
<span data-ttu-id="9164a-117">dove *expr* è un modello costante o un modello del tipo che viene confrontato con l'espressione di corrispondenza e *when-condition* è qualsiasi espressione booleana.</span><span class="sxs-lookup"><span data-stu-id="9164a-117">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span> 

<span data-ttu-id="9164a-118">Nell'esempio seguente viene usata la parola chiave `when` per testare gli oggetti `Shape` che hanno un'area pari a zero, nonché una varietà di oggetti `Shape` che hanno un'area maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="9164a-118">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span> 

 <span data-ttu-id="9164a-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="9164a-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9164a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9164a-120">See also</span></span> 
  [<span data-ttu-id="9164a-121">Istruzione switch</span><span class="sxs-lookup"><span data-stu-id="9164a-121">switch statement</span></span>](switch.md)  
  [<span data-ttu-id="9164a-122">Istruzione try/catch</span><span class="sxs-lookup"><span data-stu-id="9164a-122">try/catch statement</span></span>](try-catch.md)  
  [<span data-ttu-id="9164a-123">Istruzione try/catch/finally</span><span class="sxs-lookup"><span data-stu-id="9164a-123">try/catch/finally statement</span></span>](try-catch-finally.md) 


