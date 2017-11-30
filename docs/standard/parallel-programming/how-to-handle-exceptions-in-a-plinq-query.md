---
title: 'Procedura: gestire le eccezioni in una query PLINQ'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a><span data-ttu-id="59af3-102">Procedura: gestire le eccezioni in una query PLINQ</span><span class="sxs-lookup"><span data-stu-id="59af3-102">How to: Handle Exceptions in a PLINQ Query</span></span>
<span data-ttu-id="59af3-103">Nel primo esempio in questo argomento viene illustrato come gestire il <xref:System.AggregateException?displayProperty=nameWithType> che possono essere generate da una query PLINQ quando viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="59af3-103">The first example in this topic shows how to handle the <xref:System.AggregateException?displayProperty=nameWithType> that can be thrown from a PLINQ query when it executes.</span></span> <span data-ttu-id="59af3-104">Nel secondo esempio viene illustrato come inserire i blocchi try-catch all'interno dei delegati, più vicino possibile a cui verrà generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="59af3-104">The second example shows how to put try-catch blocks within delegates, as close as possible to where the exception will be thrown.</span></span> <span data-ttu-id="59af3-105">In questo modo, è possibile intercettarle appena che si verificano e probabilmente continuare l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="59af3-105">In this way, you can catch them as soon as they occur and possibly continue query execution.</span></span> <span data-ttu-id="59af3-106">Quando alle eccezioni è consentita la propagazione fino al thread di unione, è possibile che una query continui a elaborare alcuni elementi dopo la generazione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="59af3-106">When exceptions are allowed to bubble up back to the joining thread, then it is possible that a query may continue to process some items after the exception is raised.</span></span>  
  
 <span data-ttu-id="59af3-107">In alcuni casi quando PLINQ esegue il fallback all'esecuzione sequenziale e si verifica un'eccezione, l'eccezione può essere propagata direttamente e non il wrapping in un <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="59af3-107">In some cases when PLINQ falls back to sequential execution, and an exception occurs, the exception may be propagated directly, and not wrapped in an <xref:System.AggregateException>.</span></span> <span data-ttu-id="59af3-108">Inoltre, <xref:System.Threading.ThreadAbortException>vengono sempre propagate direttamente.</span><span class="sxs-lookup"><span data-stu-id="59af3-108">Also, <xref:System.Threading.ThreadAbortException>s are always propagated directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59af3-109">Quando "Just My Code" è abilitato, Visual interruzione sulla riga che genera l'eccezione e verrà visualizzato un messaggio di errore simile a "eccezione non gestita dal codice utente".</span><span class="sxs-lookup"><span data-stu-id="59af3-109">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="59af3-110">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="59af3-110">This error is benign.</span></span> <span data-ttu-id="59af3-111">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="59af3-111">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="59af3-112">Per impedire l'interruzione per il primo errore di Visual Studio, deselezionare semplicemente la casella di controllo "Just My Code" **strumenti, opzioni, debug, generale**.</span><span class="sxs-lookup"><span data-stu-id="59af3-112">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="59af3-113">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="59af3-113">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="59af3-114">Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="59af3-114">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59af3-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="59af3-115">Example</span></span>  
 <span data-ttu-id="59af3-116">In questo esempio viene illustrato come inserire i blocchi try-catch intorno al codice che esegue la query per rilevare qualsiasi <xref:System.AggregateException?displayProperty=nameWithType>s che vengono generate.</span><span class="sxs-lookup"><span data-stu-id="59af3-116">This example shows how to put the try-catch blocks around the code that executes the query to catch any <xref:System.AggregateException?displayProperty=nameWithType>s that are thrown.</span></span>  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 <span data-ttu-id="59af3-117">In questo esempio, la query non può continuare dopo la generazione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="59af3-117">In this example, the query cannot continue after the exception is thrown.</span></span> <span data-ttu-id="59af3-118">Una volta che il codice dell'applicazione rileva l'eccezione, PLINQ è già stato arrestato la query su tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="59af3-118">By the time your application code catches the exception, PLINQ has already stopped the query on all threads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59af3-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="59af3-119">Example</span></span>  
 <span data-ttu-id="59af3-120">Nell'esempio seguente viene illustrato come inserire un blocco try-catch a un delegato consentono di rilevare un'eccezione e continuare l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="59af3-120">The following example shows how to put a try-catch block in a delegate to make it possible to catch an exception and continue with the query execution.</span></span>  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="59af3-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="59af3-121">Compiling the Code</span></span>  
  
-   <span data-ttu-id="59af3-122">Per compilare ed eseguire questi esempi, copiarli nell'esempio di PLINQ, dati di esempio e chiamare il metodo principale.</span><span class="sxs-lookup"><span data-stu-id="59af3-122">To compile and run these examples, copy them into the PLINQ Data Sample example and call the method from Main.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="59af3-123">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="59af3-123">Robust Programming</span></span>  
 <span data-ttu-id="59af3-124">Non rilevare un'eccezione a meno che non si sa come gestire in modo tale da non danneggiare lo stato del programma.</span><span class="sxs-lookup"><span data-stu-id="59af3-124">Do not catch an exception unless you know how to handle it so that you do not corrupt the state of your program.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59af3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59af3-125">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="59af3-126">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="59af3-126">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
