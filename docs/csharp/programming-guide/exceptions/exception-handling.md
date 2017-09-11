---
title: Gestione delle eccezioni (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
caps.latest.revision: 24
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ab03e00a6b62d0c737c90fdb489be2a78f7ab6af
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="exception-handling-c-programming-guide"></a><span data-ttu-id="d5ffc-102">Gestione delle eccezioni (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d5ffc-102">Exception Handling (C# Programming Guide)</span></span>
<span data-ttu-id="d5ffc-103">I programmatori C# usano un blocco [try](../../../csharp/language-reference/keywords/try-catch.md) per creare partizioni di codice in cui potrebbe essere rilevata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-103">A [try](../../../csharp/language-reference/keywords/try-catch.md) block is used by C# programmers to partition code that might be affected by an exception.</span></span> <span data-ttu-id="d5ffc-104">I blocchi [catch](../../../csharp/language-reference/keywords/try-catch.md) associati vengono usati per gestire tutte le eccezioni risultanti.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-104">Associated [catch](../../../csharp/language-reference/keywords/try-catch.md) blocks are used to handle any resulting exceptions.</span></span> <span data-ttu-id="d5ffc-105">Un blocco [finally](../../../csharp/language-reference/keywords/try-finally.md) contiene il codice eseguito, indipendentemente dal fatto che venga generata o meno un'eccezione nel blocco `try`, ad esempio il codice relativo al rilascio delle risorse allocate nel blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-105">A [finally](../../../csharp/language-reference/keywords/try-finally.md) block contains code that is run regardless of whether or not an exception is thrown in the `try` block, such as releasing resources that are allocated in the `try` block.</span></span> <span data-ttu-id="d5ffc-106">Un blocco `try` richiede uno o più blocchi `catch` associati, un blocco `finally` o entrambi.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-106">A `try` block requires one or more associated `catch` blocks, or a `finally` block, or both.</span></span>  
  
 <span data-ttu-id="d5ffc-107">Gli esempi seguenti illustrano un'istruzione `try-catch`, un'istruzione `try-finally` e un'istruzione `try-catch-finally`.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-107">The following examples show a `try-catch` statement, a `try-finally` statement, and a `try-catch-finally` statement.</span></span>  
  
 <span data-ttu-id="d5ffc-108">[!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5ffc-108">[!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]</span></span>  
  
 <span data-ttu-id="d5ffc-109">[!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5ffc-109">[!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]</span></span>  
  
 <span data-ttu-id="d5ffc-110">[!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5ffc-110">[!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]</span></span>  
  
 <span data-ttu-id="d5ffc-111">Un blocco `try` senza un blocco `catch` o `finally` genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-111">A `try` block without a `catch` or `finally` block causes a compiler error.</span></span>  
  
## <a name="catch-blocks"></a><span data-ttu-id="d5ffc-112">Blocchi catch</span><span class="sxs-lookup"><span data-stu-id="d5ffc-112">Catch Blocks</span></span>  
 <span data-ttu-id="d5ffc-113">Un blocco `catch` consente di specificare il tipo di eccezione da intercettare.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-113">A `catch` block can specify the type of exception to catch.</span></span> <span data-ttu-id="d5ffc-114">La specifica del tipo è chiamata *filtro eccezioni*.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-114">The type specification is called an *exception filter*.</span></span> <span data-ttu-id="d5ffc-115">Il tipo di eccezione deve essere derivato da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-115">The exception type should be derived from <xref:System.Exception>.</span></span> <span data-ttu-id="d5ffc-116">In genere, specificare <xref:System.Exception> come filtro eccezioni solo se si sa come gestire tutte le eccezioni che potrebbero essere generate nel blocco `try` o se si è inclusa un'istruzione [throw](../../../csharp/language-reference/keywords/throw.md) alla fine del blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-116">In general, do not specify <xref:System.Exception> as the exception filter unless either you know how to handle all exceptions that might be thrown in the `try` block, or you have included a [throw](../../../csharp/language-reference/keywords/throw.md) statement at the end of your `catch` block.</span></span>  
  
 <span data-ttu-id="d5ffc-117">È possibile concatenare più blocchi `catch` con filtri eccezioni diversi.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-117">Multiple `catch` blocks with different exception filters can be chained together.</span></span> <span data-ttu-id="d5ffc-118">I blocchi `catch` vengono valutati dall'alto verso il basso nel codice, ma viene eseguito un solo blocco `catch` per ogni eccezione generata,</span><span class="sxs-lookup"><span data-stu-id="d5ffc-118">The `catch` blocks are evaluated from top to bottom in your code, but only one `catch` block is executed for each exception that is thrown.</span></span> <span data-ttu-id="d5ffc-119">in particolare il primo blocco `catch` che specifica il tipo esatto o una classe di base dell'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-119">The first `catch` block that specifies the exact type or a base class of the thrown exception is executed.</span></span> <span data-ttu-id="d5ffc-120">Se nessun blocco `catch` specifica un filtro eccezioni corrispondente, viene selezionato un blocco `catch` che non dispone di filtro, se presente nell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-120">If no `catch` block specifies a matching exception filter, a `catch` block that does not have a filter is selected, if one is present in the statement.</span></span> <span data-ttu-id="d5ffc-121">È importante posizionare per primi i blocchi `catch` con i tipi di eccezione più specifici (ossia i più derivati).</span><span class="sxs-lookup"><span data-stu-id="d5ffc-121">It is important to position `catch` blocks with the most specific (that is, the most derived) exception types first.</span></span>  
  
 <span data-ttu-id="d5ffc-122">È necessario intercettare le eccezioni quando le condizioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="d5ffc-122">You should catch exceptions when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="d5ffc-123">Si è compreso il motivo per cui è stata generata l'eccezione ed è possibile implementare un recupero specifico, ad esempio chiedendo all'utente di immettere un nuovo nome di file quando si intercetta un oggetto <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-123">You have a good understanding of why the exception might be thrown, and you can implement a specific recovery, such as prompting the user to enter a new file name when you catch a <xref:System.IO.FileNotFoundException> object.</span></span>  
  
-   <span data-ttu-id="d5ffc-124">È possibile creare e generare una nuova eccezione più specifica.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-124">You can create and throw a new, more specific exception.</span></span>  
  
     <span data-ttu-id="d5ffc-125">[!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5ffc-125">[!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]</span></span>  
  
-   <span data-ttu-id="d5ffc-126">Si vuole gestire parzialmente un'eccezione prima di passarla a funzioni di gestione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-126">You want to partially handle an exception before passing it on for additional handling.</span></span> <span data-ttu-id="d5ffc-127">Nell'esempio seguente un blocco `catch` viene usato per aggiungere una voce al log degli errori prima di generare di nuovo l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-127">In the following example, a `catch` block is used to add an entry to an error log before re-throwing the exception.</span></span>  
  
     <span data-ttu-id="d5ffc-128">[!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5ffc-128">[!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]</span></span>  
  
## <a name="finally-blocks"></a><span data-ttu-id="d5ffc-129">Blocchi finally</span><span class="sxs-lookup"><span data-stu-id="d5ffc-129">Finally Blocks</span></span>  
 <span data-ttu-id="d5ffc-130">Un blocco `finally` consente la pulizia delle azioni eseguite in un blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-130">A `finally` block enables you to clean up actions that are performed in a `try` block.</span></span> <span data-ttu-id="d5ffc-131">Se presente, il blocco `finally` viene eseguito per ultimo, dopo il blocco `try` e i blocchi `catch` corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-131">If present, the `finally` block executes last, after the `try` block and any matched `catch` block.</span></span> <span data-ttu-id="d5ffc-132">Un blocco `finally` viene sempre eseguito, sia che venga o meno generata un'eccezione o che venga o meno individuato un blocco `catch` corrispondente al tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-132">A `finally` block always runs, regardless of whether an exception is thrown or a `catch` block matching the exception type is found.</span></span>  
  
 <span data-ttu-id="d5ffc-133">Il blocco `finally` può essere usato per rilasciare risorse quali flussi di file, connessioni di database e handle di elementi grafici, senza attendere che il Garbage Collector del runtime finalizzi gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-133">The `finally` block can be used to release resources such as file streams, database connections, and graphics handles without waiting for the garbage collector in the runtime to finalize the objects.</span></span> <span data-ttu-id="d5ffc-134">Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d5ffc-134">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="d5ffc-135">Nell'esempio riportato di seguito viene usato il blocco `finally` per chiudere un file aperto nel blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-135">In the following example, the `finally` block is used to close a file that is opened in the `try` block.</span></span> <span data-ttu-id="d5ffc-136">Si noti che prima della chiusura viene controllato lo stato dell'handle del file.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-136">Notice that the state of the file handle is checked before the file is closed.</span></span> <span data-ttu-id="d5ffc-137">Se il blocco `try` non riesce ad aprire il file, l'handle del file ha sempre valore `null` e il blocco `finally` non tenta di chiuderlo.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-137">If the `try` block cannot open the file, the file handle still has the value `null` and the `finally` block does not try to close it.</span></span> <span data-ttu-id="d5ffc-138">In alternativa, se il file è aperto correttamente nel blocco `try`, il blocco `finally` chiude il file aperto.</span><span class="sxs-lookup"><span data-stu-id="d5ffc-138">Alternatively, if the file is opened successfully in the `try` block, the `finally` block closes the open file.</span></span>  
  
 <span data-ttu-id="d5ffc-139">[!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5ffc-139">[!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d5ffc-140">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d5ffc-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5ffc-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5ffc-141">See Also</span></span>  
 <span data-ttu-id="d5ffc-142">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5ffc-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d5ffc-143">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5ffc-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d5ffc-144">[Eccezioni e gestione delle eccezioni](../../../csharp/programming-guide/exceptions/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5ffc-144">[Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md) </span></span>  
 <span data-ttu-id="d5ffc-145">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="d5ffc-145">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="d5ffc-146">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="d5ffc-146">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 <span data-ttu-id="d5ffc-147">[try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md) </span><span class="sxs-lookup"><span data-stu-id="d5ffc-147">[try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md) </span></span>  
 [<span data-ttu-id="d5ffc-148">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="d5ffc-148">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

