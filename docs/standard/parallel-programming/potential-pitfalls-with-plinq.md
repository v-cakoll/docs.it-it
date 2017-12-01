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
# <a name="potential-pitfalls-with-plinq"></a>Problemi potenziali dell'utilizzo di PLINQ
In molti casi, PLINQ può fornire miglioramenti significativi delle prestazioni su sequenziale query LINQ to Objects. Tuttavia, le operazioni di parallelizzazione l'esecuzione della query introducono complessità che può causare problemi che in codice sequenziale, non sono comuni o non vengono rilevati affatto. In questo argomento sono elencati alcuni suggerimenti da tenere presenti quando si scrivono query PLINQ.  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a>Non presupporre che l'approccio in parallelo sia sempre più veloce  
 In alcuni casi la parallelizzazione interrompe una query PLINQ eseguita più lentamente rispetto alla query LINQ to Objects equivalente. La regola generale di base è che le query con alcuni elementi di origine e i delegati dell'utente veloci sono molto improbabile che un aumento di velocità. Tuttavia, poiché molti fattori influiscono sulle prestazioni, è consigliabile misurare i risultati effettivi prima di decidere se utilizzare PLINQ. Per altre informazioni, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="avoid-writing-to-shared-memory-locations"></a>Evitare di scrivere in percorsi di memoria condivisi  
 Nel codice sequenziale spesso si eseguono operazioni di lettura e scrittura su variabili o campi di classe statici. Tuttavia, ogni volta che più thread eseguono un accesso simultaneo a queste variabili, è molto probabile che si verifichino race condition. Anche se è possibile sincronizzare l'accesso alla variabile mediante l'utilizzo di blocchi, il costo di questa sincronizzazione può influire negativamente sulle prestazioni. È pertanto consigliabile evitare, o almeno limitare, accedere allo stato condiviso in una query PLINQ quanto possibile.  
  
## <a name="avoid-over-parallelization"></a>Evitare parallelizzazioni eccessive  
 Tramite il `AsParallel` operatore costo dei costi generali di partizionamento della raccolta di origine e di sincronizzazione dei thread di lavoro. I vantaggi della parallelizzazione vengono limitati ulteriormente dal numero di processori nel computer. Non si ottiene alcun aumento di velocità eseguendo più thread con vincoli di calcolo in un unico processore. Pertanto, è necessario fare attenzione a non parallelizzazione eccessiva delle query.  
  
 Lo scenario più comune in cui parallelizzazioni possono verificarsi è query annidate, come illustrato nel seguente frammento.  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 In questo caso, è consigliabile parallelizzare solo l'origine dati esterna (customers), a meno che non si applicano a uno o più delle condizioni seguenti:  
  
-   L'origine dati interna (cust. Ordini) è noto a essere molto lunghi.  
  
-   Si eseguono calcoli dispendiosi in ogni ordine. L'operazione mostrata nell'esempio non è dispendiosa.  
  
-   È noto che il sistema di destinazione presenta un numero di processori sufficiente per gestire il numero di thread che verranno prodotti dalla parallelizzazione della query su `cust.Orders`.  
  
 In ogni caso, il miglior modo per determinare la forma ottimale della query è tramite lo svolgimento di test e misure. Per ulteriori informazioni, vedere [come: misura le prestazioni delle Query PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a>Evitare chiamate a metodi non thread-safe  
 Scrittura di metodi di istanza non thread-safe da un PLINQ query può causare il danneggiamento dei dati che non può passare inosservato nel programma. Può inoltre comportare la generazione di eccezioni. Nell'esempio seguente, più thread tentano di chiamare il `Filestream.Write` metodo contemporaneamente, che non è supportata dalla classe.  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a>Limitare le chiamate ai metodi thread-safe  
 La maggior parte dei metodi statici in .NET Framework è thread-safe e può essere chiamata simultaneamente da più thread. Tuttavia, anche in questi casi, la sincronizzazione da applicare può comportare un rallentamento significativo della query.  
  
> [!NOTE]
>  È possibile testare per questo manualmente mediante l'inserimento di alcune chiamate a <xref:System.Console.WriteLine%2A> nelle query. Anche se questo metodo viene utilizzato negli esempi della documentazione a scopo dimostrativo, non utilizzarlo nelle query PLINQ.  
  
## <a name="avoid-unnecessary-ordering-operations"></a>Evitare operazioni di ordinamento superflue  
 Quando PLINQ esegue una query in parallelo, divide la sequenza di origine in partizioni che possono essere utilizzate contemporaneamente su più thread. Per impostazione predefinita, l'ordine in cui le partizioni vengono elaborate e i risultati vengono recapitati non è stimabile (ad eccezione degli operatori, ad esempio `OrderBy`). È possibile indicare a PLINQ di conservare l'ordine di qualsiasi sequenza di origine, ma si ha un impatto negativo sulle prestazioni. La procedura consigliata, se possibile, è strutturare le query in modo che non si basano sulla conservazione dell'ordine. Per altre informazioni, vedere [Conservazione dell'ordine in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a>Preferire ForAll a ForEach quando è possibile  
 Anche se PLINQ esegue una query su più thread, se si utilizzano i risultati in un `foreach` ciclo (`For Each` in Visual Basic), quindi i risultati della query devono essere uniti a un unico thread e accedere in modo seriale dall'enumeratore. In alcuni casi, questo è inevitabile. Tuttavia, se possibile, utilizzare il `ForAll` metodo per consentire a ogni thread restituire i propri risultati, ad esempio, scrivendo in una raccolta thread-safe, ad esempio <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.  
  
 Lo stesso problema si verifica con <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. In altre parole, `source.AsParallel().Where().ForAll(...)` deve essere fortemente preferito a  
  
 `Parallel.ForEach(source.AsParallel().Where(), ...)`.  
  
## <a name="be-aware-of-thread-affinity-issues"></a>Tenere presente i problemi di affinità di thread  
 Alcune tecnologie, ad esempio l'interoperabilità COM per i componenti apartment a thread singolo (STA, Single-Threaded Apartment), Windows Form e Windows Presentation Foundation (WPF), impongono restrizioni di affinità di thread che richiedono l'esecuzione del codice in un thread specifico. Ad esempio, sia in Windows Form sia in WPF, l'accesso a un controllo può essere eseguito solo nel thread in cui è stato creato. Se si tenta di accedere allo stato condiviso di un controllo Windows Form in una query PLINQ, viene generata un'eccezione se si esegue il debugger. (Questa impostazione può essere disattivata.) Tuttavia, se la query viene utilizzata nel thread dell'interfaccia utente, è possibile accedere al controllo dal `foreach` ciclo che enumera la query si verifica perché tale codice viene eseguito in un solo thread.  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a>Non presupporre che le iterazioni di Foreach, For e ForAll vengano eseguite sempre in parallelo  
 È importante tenere presente che le iterazioni singole in una <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> o <xref:System.Linq.ParallelEnumerable.ForAll%2A> ciclo maggio ma non è necessario eseguire in parallelo. È pertanto necessario evitare di scrivere codice la cui correttezza dipenda dall'esecuzione parallela delle iterazioni o dall'esecuzione delle iterazioni in un particolare ordine.  
  
 Il codice seguente, ad esempio, è molto probabile che conduca a un deadlock:  
  
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
  
 In questo esempio, un'unica iterazione imposta un evento e tutte le altre iterazioni attendono l'evento. Nessuna delle iterazioni in attesa può essere completata fino a quando non viene completata l'iterazione di impostazione dell'evento. È tuttavia possibile che le iterazioni in attesa blocchino tutti i thread utilizzati per eseguire il ciclo parallelo, prima che l'iterazione di impostazione dell'evento abbia avuto la possibilità di essere eseguita. Ciò comporta un deadlock. L'iterazione di impostazione dell'evento non verrà mai eseguita e le iterazioni in attesa non verranno mai riattivate.  
  
 In particolare, l'avanzamento di un'iterazione di un ciclo parallelo non deve dipendere da un'altra iterazione del ciclo. Se il ciclo parallelo decide di pianificare le iterazioni in sequenza ma nell'ordine opposto, si verificherà un deadlock.  
  
## <a name="see-also"></a>Vedere anche  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
