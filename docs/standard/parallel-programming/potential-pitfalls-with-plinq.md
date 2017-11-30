---
title: Problemi potenziali dell'utilizzo di PLINQ
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
helpviewer_keywords: PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7c971d2c039e6441669108e966eba472819fde5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="potential-pitfalls-with-plinq"></a><span data-ttu-id="1dfd2-102">Problemi potenziali dell'utilizzo di PLINQ</span><span class="sxs-lookup"><span data-stu-id="1dfd2-102">Potential Pitfalls with PLINQ</span></span>
<span data-ttu-id="1dfd2-103">In molti casi, PLINQ può fornire miglioramenti significativi delle prestazioni su sequenziale query LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-103">In many cases, PLINQ can provide significant performance improvements over sequential LINQ to Objects queries.</span></span> <span data-ttu-id="1dfd2-104">Tuttavia, le operazioni di parallelizzazione l'esecuzione della query introducono complessità che può causare problemi che in codice sequenziale, non sono comuni o non vengono rilevati affatto.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-104">However, the work of parallelizing the query execution introduces complexity that can lead to problems that, in sequential code, are not as common or are not encountered at all.</span></span> <span data-ttu-id="1dfd2-105">In questo argomento sono elencati alcuni suggerimenti da tenere presenti quando si scrivono query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-105">This topic lists some practices to avoid when you write PLINQ queries.</span></span>  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a><span data-ttu-id="1dfd2-106">Non presupporre che l'approccio in parallelo sia sempre più veloce</span><span class="sxs-lookup"><span data-stu-id="1dfd2-106">Do Not Assume That Parallel Is Always Faster</span></span>  
 <span data-ttu-id="1dfd2-107">In alcuni casi la parallelizzazione interrompe una query PLINQ eseguita più lentamente rispetto alla query LINQ to Objects equivalente.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-107">Parallelization sometimes causes a PLINQ query to run slower than its LINQ to Objects equivalent.</span></span> <span data-ttu-id="1dfd2-108">La regola generale di base è che le query con alcuni elementi di origine e i delegati dell'utente veloci sono molto improbabile che un aumento di velocità.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-108">The basic rule of thumb is that queries that have few source elements and fast user delegates are unlikely to speedup much.</span></span> <span data-ttu-id="1dfd2-109">Tuttavia, poiché molti fattori influiscono sulle prestazioni, è consigliabile misurare i risultati effettivi prima di decidere se utilizzare PLINQ.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-109">However, because many factors are involved in performance, we recommend that you measure actual results before you decide whether to use PLINQ.</span></span> <span data-ttu-id="1dfd2-110">Per altre informazioni, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="1dfd2-110">For more information, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="avoid-writing-to-shared-memory-locations"></a><span data-ttu-id="1dfd2-111">Evitare di scrivere in percorsi di memoria condivisi</span><span class="sxs-lookup"><span data-stu-id="1dfd2-111">Avoid Writing to Shared Memory Locations</span></span>  
 <span data-ttu-id="1dfd2-112">Nel codice sequenziale spesso si eseguono operazioni di lettura e scrittura su variabili o campi di classe statici.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-112">In sequential code, it is not uncommon to read from or write to static variables or class fields.</span></span> <span data-ttu-id="1dfd2-113">Tuttavia, ogni volta che più thread eseguono un accesso simultaneo a queste variabili, è molto probabile che si verifichino race condition.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-113">However, whenever multiple threads are accessing such variables concurrently, there is a big potential for race conditions.</span></span> <span data-ttu-id="1dfd2-114">Anche se è possibile sincronizzare l'accesso alla variabile mediante l'utilizzo di blocchi, il costo di questa sincronizzazione può influire negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-114">Even though you can use locks to synchronize access to the variable, the cost of synchronization can hurt performance.</span></span> <span data-ttu-id="1dfd2-115">È pertanto consigliabile evitare, o almeno limitare, accedere allo stato condiviso in una query PLINQ quanto possibile.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-115">Therefore, we recommend that you avoid, or at least limit, access to shared state in a PLINQ query as much as possible.</span></span>  
  
## <a name="avoid-over-parallelization"></a><span data-ttu-id="1dfd2-116">Evitare parallelizzazioni eccessive</span><span class="sxs-lookup"><span data-stu-id="1dfd2-116">Avoid Over-Parallelization</span></span>  
 <span data-ttu-id="1dfd2-117">Tramite il `AsParallel` operatore costo dei costi generali di partizionamento della raccolta di origine e di sincronizzazione dei thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-117">By using the `AsParallel` operator, you incur the overhead costs of partitioning the source collection and synchronizing the worker threads.</span></span> <span data-ttu-id="1dfd2-118">I vantaggi della parallelizzazione vengono limitati ulteriormente dal numero di processori nel computer.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-118">The benefits of parallelization are further limited by the number of processors on the computer.</span></span> <span data-ttu-id="1dfd2-119">Non si ottiene alcun aumento di velocità eseguendo più thread con vincoli di calcolo in un unico processore.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-119">There is no speedup to be gained by running multiple compute-bound threads on just one processor.</span></span> <span data-ttu-id="1dfd2-120">Pertanto, è necessario fare attenzione a non parallelizzazione eccessiva delle query.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-120">Therefore, you must be careful not to over-parallelize a query.</span></span>  
  
 <span data-ttu-id="1dfd2-121">Lo scenario più comune in cui parallelizzazioni possono verificarsi è query annidate, come illustrato nel seguente frammento.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-121">The most common scenario in which over-parallelization can occur is in nested queries, as shown in the following snippet.</span></span>  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 <span data-ttu-id="1dfd2-122">In questo caso, è consigliabile parallelizzare solo l'origine dati esterna (customers), a meno che non si applicano a uno o più delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1dfd2-122">In this case, it is best to parallelize only the outer data source (customers) unless one or more of the following conditions apply:</span></span>  
  
-   <span data-ttu-id="1dfd2-123">L'origine dati interna (cust. Ordini) è noto a essere molto lunghi.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-123">The inner data source (cust.Orders) is known to be very long.</span></span>  
  
-   <span data-ttu-id="1dfd2-124">Si eseguono calcoli dispendiosi in ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-124">You are performing an expensive computation on each order.</span></span> <span data-ttu-id="1dfd2-125">L'operazione mostrata nell'esempio non è dispendiosa.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-125">(The operation shown in the example is not expensive.)</span></span>  
  
-   <span data-ttu-id="1dfd2-126">È noto che il sistema di destinazione presenta un numero di processori sufficiente per gestire il numero di thread che verranno prodotti dalla parallelizzazione della query su `cust.Orders`.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-126">The target system is known to have enough processors to handle the number of threads that will be produced by parallelizing the query on `cust.Orders`.</span></span>  
  
 <span data-ttu-id="1dfd2-127">In ogni caso, il miglior modo per determinare la forma ottimale della query è tramite lo svolgimento di test e misure.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-127">In all cases, the best way to determine the optimum query shape is to test and measure.</span></span> <span data-ttu-id="1dfd2-128">Per ulteriori informazioni, vedere [come: misura le prestazioni delle Query PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span><span class="sxs-lookup"><span data-stu-id="1dfd2-128">For more information, see [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span></span>  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a><span data-ttu-id="1dfd2-129">Evitare chiamate a metodi non thread-safe</span><span class="sxs-lookup"><span data-stu-id="1dfd2-129">Avoid Calls to Non-Thread-Safe Methods</span></span>  
 <span data-ttu-id="1dfd2-130">Scrittura di metodi di istanza non thread-safe da un PLINQ query può causare il danneggiamento dei dati che non può passare inosservato nel programma.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-130">Writing to non-thread-safe instance methods from a PLINQ query can lead to data corruption which may or may not go undetected in your program.</span></span> <span data-ttu-id="1dfd2-131">Può inoltre comportare la generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-131">It can also lead to exceptions.</span></span> <span data-ttu-id="1dfd2-132">Nell'esempio seguente, più thread tentano di chiamare il `Filestream.Write` metodo contemporaneamente, che non è supportata dalla classe.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-132">In the following example, multiple threads would be attempting to call the `Filestream.Write` method simultaneously, which is not supported by the class.</span></span>  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a><span data-ttu-id="1dfd2-133">Limitare le chiamate ai metodi thread-safe</span><span class="sxs-lookup"><span data-stu-id="1dfd2-133">Limit Calls to Thread-Safe Methods</span></span>  
 <span data-ttu-id="1dfd2-134">La maggior parte dei metodi statici in .NET Framework è thread-safe e può essere chiamata simultaneamente da più thread.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-134">Most static methods in the .NET Framework are thread-safe and can be called from multiple threads concurrently.</span></span> <span data-ttu-id="1dfd2-135">Tuttavia, anche in questi casi, la sincronizzazione da applicare può comportare un rallentamento significativo della query.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-135">However, even in these cases, the synchronization involved can lead to significant slowdown in the query.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1dfd2-136">È possibile testare per questo manualmente mediante l'inserimento di alcune chiamate a <xref:System.Console.WriteLine%2A> nelle query.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-136">You can test for this yourself by inserting some calls to <xref:System.Console.WriteLine%2A> in your queries.</span></span> <span data-ttu-id="1dfd2-137">Anche se questo metodo viene utilizzato negli esempi della documentazione a scopo dimostrativo, non utilizzarlo nelle query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-137">Although this method is used in the documentation examples for demonstration purposes, do not use it in PLINQ queries.</span></span>  
  
## <a name="avoid-unnecessary-ordering-operations"></a><span data-ttu-id="1dfd2-138">Evitare operazioni di ordinamento superflue</span><span class="sxs-lookup"><span data-stu-id="1dfd2-138">Avoid Unnecessary Ordering Operations</span></span>  
 <span data-ttu-id="1dfd2-139">Quando PLINQ esegue una query in parallelo, divide la sequenza di origine in partizioni che possono essere utilizzate contemporaneamente su più thread.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-139">When PLINQ executes a query in parallel, it divides the source sequence into partitions that can be operated on concurrently on multiple threads.</span></span> <span data-ttu-id="1dfd2-140">Per impostazione predefinita, l'ordine in cui le partizioni vengono elaborate e i risultati vengono recapitati non è stimabile (ad eccezione degli operatori, ad esempio `OrderBy`).</span><span class="sxs-lookup"><span data-stu-id="1dfd2-140">By default, the order in which the partitions are processed and the results are delivered is not predictable (except for operators such as `OrderBy`).</span></span> <span data-ttu-id="1dfd2-141">È possibile indicare a PLINQ di conservare l'ordine di qualsiasi sequenza di origine, ma si ha un impatto negativo sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-141">You can instruct PLINQ to preserve the ordering of any source sequence, but this has a negative impact on performance.</span></span> <span data-ttu-id="1dfd2-142">La procedura consigliata, se possibile, è strutturare le query in modo che non si basano sulla conservazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-142">The best practice, whenever possible, is to structure queries so that they do not rely on order preservation.</span></span> <span data-ttu-id="1dfd2-143">Per altre informazioni, vedere [Conservazione dell'ordine in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="1dfd2-143">For more information, see [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span></span>  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a><span data-ttu-id="1dfd2-144">Preferire ForAll a ForEach quando è possibile</span><span class="sxs-lookup"><span data-stu-id="1dfd2-144">Prefer ForAll to ForEach When It Is Possible</span></span>  
 <span data-ttu-id="1dfd2-145">Anche se PLINQ esegue una query su più thread, se si utilizzano i risultati in un `foreach` ciclo (`For Each` in Visual Basic), quindi i risultati della query devono essere uniti a un unico thread e accedere in modo seriale dall'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-145">Although PLINQ executes a query on multiple threads, if you consume the results in a `foreach` loop (`For Each` in Visual Basic), then the query results must be merged back into one thread and accessed serially by the enumerator.</span></span> <span data-ttu-id="1dfd2-146">In alcuni casi, questo è inevitabile. Tuttavia, se possibile, utilizzare il `ForAll` metodo per consentire a ogni thread restituire i propri risultati, ad esempio, scrivendo in una raccolta thread-safe, ad esempio <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-146">In some cases, this is unavoidable; however, whenever possible, use the `ForAll` method to enable each thread to output its own results, for example, by writing to a thread-safe collection such as <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="1dfd2-147">Lo stesso problema si verifica con <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. In altre parole, `source.AsParallel().Where().ForAll(...)` deve essere fortemente preferito a</span><span class="sxs-lookup"><span data-stu-id="1dfd2-147">The same issue applies to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> In other words, `source.AsParallel().Where().ForAll(...)` should be strongly preferred to</span></span>  
  
 <span data-ttu-id="1dfd2-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span></span>  
  
## <a name="be-aware-of-thread-affinity-issues"></a><span data-ttu-id="1dfd2-149">Tenere presente i problemi di affinità di thread</span><span class="sxs-lookup"><span data-stu-id="1dfd2-149">Be Aware of Thread Affinity Issues</span></span>  
 <span data-ttu-id="1dfd2-150">Alcune tecnologie, ad esempio l'interoperabilità COM per i componenti apartment a thread singolo (STA, Single-Threaded Apartment), Windows Form e Windows Presentation Foundation (WPF), impongono restrizioni di affinità di thread che richiedono l'esecuzione del codice in un thread specifico.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-150">Some technologies, for example, COM interoperability for Single-Threaded Apartment (STA) components, Windows Forms, and Windows Presentation Foundation (WPF), impose thread affinity restrictions that require code to run on a specific thread.</span></span> <span data-ttu-id="1dfd2-151">Ad esempio, sia in Windows Form sia in WPF, l'accesso a un controllo può essere eseguito solo nel thread in cui è stato creato.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-151">For example, in both Windows Forms and WPF, a control can only be accessed on the thread on which it was created.</span></span> <span data-ttu-id="1dfd2-152">Se si tenta di accedere allo stato condiviso di un controllo Windows Form in una query PLINQ, viene generata un'eccezione se si esegue il debugger.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-152">If you try to access the shared state of a Windows Forms control in a PLINQ query, an exception is raised if you are running in the debugger.</span></span> <span data-ttu-id="1dfd2-153">(Questa impostazione può essere disattivata.) Tuttavia, se la query viene utilizzata nel thread dell'interfaccia utente, è possibile accedere al controllo dal `foreach` ciclo che enumera la query si verifica perché tale codice viene eseguito in un solo thread.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-153">(This setting can be turned off.) However, if your query is consumed on the UI thread, then you can access the control from the `foreach` loop that enumerates the query results because that code executes on just one thread.</span></span>  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a><span data-ttu-id="1dfd2-154">Non presupporre che le iterazioni di Foreach, For e ForAll vengano eseguite sempre in parallelo</span><span class="sxs-lookup"><span data-stu-id="1dfd2-154">Do Not Assume that Iterations of ForEach, For and ForAll Always Execute in Parallel</span></span>  
 <span data-ttu-id="1dfd2-155">È importante tenere presente che le iterazioni singole in una <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> o <xref:System.Linq.ParallelEnumerable.ForAll%2A> ciclo maggio ma non è necessario eseguire in parallelo.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-155">It is important to keep in mind that individual iterations in a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> or <xref:System.Linq.ParallelEnumerable.ForAll%2A> loop may but do not have to execute in parallel.</span></span> <span data-ttu-id="1dfd2-156">È pertanto necessario evitare di scrivere codice la cui correttezza dipenda dall'esecuzione parallela delle iterazioni o dall'esecuzione delle iterazioni in un particolare ordine.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-156">Therefore, you should avoid writing any code that depends for correctness on parallel execution of iterations or on the execution of iterations in any particular order.</span></span>  
  
 <span data-ttu-id="1dfd2-157">Il codice seguente, ad esempio, è molto probabile che conduca a un deadlock:</span><span class="sxs-lookup"><span data-stu-id="1dfd2-157">For example, this code is likely to deadlock:</span></span>  
  
```vb  
Dim mre = New ManualResetEventSlim()  
    Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll(Sub(j)   
  
                                                     If j = Environment.ProcessorCount Then  
  
                                                         Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Set()  
  
                                                     Else  
  
                                                         Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Wait()  
                                                     End If  
    End Sub) ' deadlocks  
```  
  
```csharp  
ManualResetEventSlim mre = new ManualResetEventSlim();  
            Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll((j) =>  
            {  
                if (j == Environment.ProcessorCount)  
                {  
                    Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Set();  
                }  
                else  
                {  
                    Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Wait();  
                }  
            }); //deadlocks  
```  
  
 <span data-ttu-id="1dfd2-158">In questo esempio, un'unica iterazione imposta un evento e tutte le altre iterazioni attendono l'evento.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-158">In this example, one iteration sets an event, and all other iterations wait on the event.</span></span> <span data-ttu-id="1dfd2-159">Nessuna delle iterazioni in attesa può essere completata fino a quando non viene completata l'iterazione di impostazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-159">None of the waiting iterations can complete until the event-setting iteration has completed.</span></span> <span data-ttu-id="1dfd2-160">È tuttavia possibile che le iterazioni in attesa blocchino tutti i thread utilizzati per eseguire il ciclo parallelo, prima che l'iterazione di impostazione dell'evento abbia avuto la possibilità di essere eseguita.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-160">However, it is possible that the waiting iterations block all threads that are used to execute the parallel loop, before the event-setting iteration has had a chance to execute.</span></span> <span data-ttu-id="1dfd2-161">Ciò comporta un deadlock. L'iterazione di impostazione dell'evento non verrà mai eseguita e le iterazioni in attesa non verranno mai riattivate.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-161">This results in a deadlock – the event-setting iteration will never execute, and the waiting iterations will never wake up.</span></span>  
  
 <span data-ttu-id="1dfd2-162">In particolare, l'avanzamento di un'iterazione di un ciclo parallelo non deve dipendere da un'altra iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-162">In particular, one iteration of a parallel loop should never wait on another iteration of the loop to make progress.</span></span> <span data-ttu-id="1dfd2-163">Se il ciclo parallelo decide di pianificare le iterazioni in sequenza ma nell'ordine opposto, si verificherà un deadlock.</span><span class="sxs-lookup"><span data-stu-id="1dfd2-163">If the parallel loop decides to schedule the iterations sequentially but in the opposite order, a deadlock will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dfd2-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dfd2-164">See Also</span></span>  
 [<span data-ttu-id="1dfd2-165">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="1dfd2-165">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
