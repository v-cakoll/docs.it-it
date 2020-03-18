---
title: 'Procedura: gestire le eccezioni in una query PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
ms.openlocfilehash: 3645f5dc470ef53710aa7f4c78c60431fb27ecfa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123098"
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a><span data-ttu-id="c5090-102">Procedura: gestire le eccezioni in una query PLINQ</span><span class="sxs-lookup"><span data-stu-id="c5090-102">How to: Handle Exceptions in a PLINQ Query</span></span>

<span data-ttu-id="c5090-103">Il primo esempio in questo argomento mostra come gestire l'oggetto <xref:System.AggregateException?displayProperty=nameWithType>, che può essere generato da una query PLINQ in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c5090-103">The first example in this topic shows how to handle the <xref:System.AggregateException?displayProperty=nameWithType> that can be thrown from a PLINQ query when it executes.</span></span> <span data-ttu-id="c5090-104">Il secondo esempio mostra come inserire blocchi Try-Catch all'interno di delegati, il più vicino possibile al punto in cui verrà generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c5090-104">The second example shows how to put try-catch blocks within delegates, as close as possible to where the exception will be thrown.</span></span> <span data-ttu-id="c5090-105">In questo modo, è possibile intercettare le eccezioni non appena si verificano, per poter proseguire con l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="c5090-105">In this way, you can catch them as soon as they occur and possibly continue query execution.</span></span> <span data-ttu-id="c5090-106">Quando alle eccezioni è consentita la propagazione fino al thread di unione, è possibile che una query continui a elaborare alcuni elementi dopo la generazione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c5090-106">When exceptions are allowed to bubble up back to the joining thread, then it is possible that a query may continue to process some items after the exception is raised.</span></span>

<span data-ttu-id="c5090-107">In alcuni casi, quando PLINQ passa all'esecuzione sequenziale e viene generata un'eccezione, l'eccezione può essere propagata direttamente, senza eseguirne il wrapping in un oggetto <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="c5090-107">In some cases when PLINQ falls back to sequential execution, and an exception occurs, the exception may be propagated directly, and not wrapped in an <xref:System.AggregateException>.</span></span> <span data-ttu-id="c5090-108">Inoltre, gli oggetti <xref:System.Threading.ThreadAbortException> vengono sempre propagati direttamente.</span><span class="sxs-lookup"><span data-stu-id="c5090-108">Also, <xref:System.Threading.ThreadAbortException>s are always propagated directly.</span></span>

> [!NOTE]
> <span data-ttu-id="c5090-109">Quando è abilitato "Just My Code", Visual Studio si interrompe in corrispondenza della riga che genera l'eccezione e visualizza un messaggio di errore che indica che l'eccezione non è stata gestita dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="c5090-109">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="c5090-110">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="c5090-110">This error is benign.</span></span> <span data-ttu-id="c5090-111">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="c5090-111">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="c5090-112">Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.</span><span class="sxs-lookup"><span data-stu-id="c5090-112">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>
>
> <span data-ttu-id="c5090-113">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="c5090-113">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="c5090-114">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="c5090-114">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>

## <a name="example"></a><span data-ttu-id="c5090-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5090-115">Example</span></span>

<span data-ttu-id="c5090-116">Questo esempio mostra come inserire blocchi Try-Catch intorno al codice che esegue la query per recuperare qualsiasi eccezione <xref:System.AggregateException?displayProperty=nameWithType> generata.</span><span class="sxs-lookup"><span data-stu-id="c5090-116">This example shows how to put the try-catch blocks around the code that executes the query to catch any <xref:System.AggregateException?displayProperty=nameWithType>s that are thrown.</span></span>

[!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
[!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]

<span data-ttu-id="c5090-117">In questo esempio la query non può continuare dopo la generazione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c5090-117">In this example, the query cannot continue after the exception is thrown.</span></span> <span data-ttu-id="c5090-118">Nel momento in cui il codice dell'applicazione intercetta l'eccezione, PLINQ ha già arrestato la query in tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="c5090-118">By the time your application code catches the exception, PLINQ has already stopped the query on all threads.</span></span>

## <a name="example"></a><span data-ttu-id="c5090-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5090-119">Example</span></span>

<span data-ttu-id="c5090-120">L'esempio seguente mostra come inserire un blocco Try-Catch in un delegato per permettere di intercettare un'eccezione e proseguire con l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="c5090-120">The following example shows how to put a try-catch block in a delegate to make it possible to catch an exception and continue with the query execution.</span></span>

[!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
[!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]

## <a name="compiling-the-code"></a><span data-ttu-id="c5090-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c5090-121">Compiling the Code</span></span>

- <span data-ttu-id="c5090-122">Per compilare ed eseguire questi esempi, copiarli nel progetto PLINQ Data Sample e chiamare il metodo da Main.</span><span class="sxs-lookup"><span data-stu-id="c5090-122">To compile and run these examples, copy them into the PLINQ Data Sample example and call the method from Main.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="c5090-123">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c5090-123">Robust Programming</span></span>

<span data-ttu-id="c5090-124">Non intercettare un'eccezione se non si è in grado di gestirla, in modo da non danneggiare lo stato del programma.</span><span class="sxs-lookup"><span data-stu-id="c5090-124">Do not catch an exception unless you know how to handle it so that you do not corrupt the state of your program.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5090-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5090-125">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="c5090-126">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="c5090-126">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
