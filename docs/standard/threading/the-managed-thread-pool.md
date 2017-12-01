---
title: Pool di thread gestiti
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
- cpp
helpviewer_keywords:
- thread pooling [.NET Framework]
- thread pools [.NET Framework]
- threading [.NET Framework], thread pool
- threading [.NET Framework], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38032fccce1a8f6f7cbcb3bbd3d3f9d008a74141
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="the-managed-thread-pool"></a>Pool di thread gestiti
La classe <xref:System.Threading.ThreadPool> fornisce all'applicazione un pool di thread di lavoro gestiti dal sistema, per consentire di concentrarsi sulle attività dell'applicazione anziché sulla gestione dei thread. Se si dispone di attività brevi che richiedono l'elaborazione in background, il pool di thread gestiti consente di sfruttare in modo semplice i vantaggi di più thread. A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è ad esempio possibile creare oggetti <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> che eseguono attività asincrone nei thread del pool.  
  
> [!NOTE]
>  A partire da [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)], la velocità effettiva del pool di thread è migliorata notevolmente nelle tre aree principali identificate come colli di bottiglia nelle versioni precedenti di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: accodamento delle attività, invio di thread del pool e invio di thread di completamento di I/O. Per usare questa funzionalità, l'applicazione deve essere destinata a [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] o versione successiva.  
  
 Per le attività in background che interagiscono con l'interfaccia utente, .NET Framework versione 2.0 fornisce anche la classe <xref:System.ComponentModel.BackgroundWorker>, che comunica tramite gli eventi generati nel thread di interfaccia utente.  
  
 .NET Framework usa i thread del pool per numerosi scopi, tra cui completamento I/O asincrono, callback dei timer, operazioni di attesa registrate, chiamate asincrone di metodi tramite delegati e connessioni socket <xref:System.Net>.  
  
## <a name="when-not-to-use-thread-pool-threads"></a>Quando non usare thread del pool  
 Vi sono diversi scenari in cui è appropriato creare e gestire i propri thread anziché usare i thread del pool, come i casi seguenti:  
  
-   È necessario un thread in primo piano.  
  
-   È necessario che un thread abbia una priorità specifica.  
  
-   Sono presenti attività che causano il blocco del thread per lunghi periodi di tempo. Il pool di thread prevede un numero massimo di thread, pertanto un numero elevato di thread del pool bloccati potrebbe impedire l'avvio delle attività.  
  
-   È necessario inserire thread di un apartment a thread singolo. Tutti i thread di <xref:System.Threading.ThreadPool> sono inclusi in apartment a thread multipli.  
  
-   È necessario disporre di un'identità stabile associata al thread o dedicare un thread a un'attività.  
  
## <a name="thread-pool-characteristics"></a>Caratteristiche del pool di thread  
 I thread del pool sono thread in background. Vedere [in primo piano e i thread in Background](../../../docs/standard/threading/foreground-and-background-threads.md). Ogni thread usa la dimensione dello stack predefinita, viene eseguito con la priorità predefinita e si trova in un apartment a thread multipli.  
  
 È presente un solo pool di thread per processo.  
  
### <a name="exceptions-in-thread-pool-threads"></a>Eccezioni nei thread del pool  
 Le eccezioni non gestite nei thread del pool terminano il processo. Vi sono tre eccezioni a questa regola:  
  
-   Viene generata un'eccezione <xref:System.Threading.ThreadAbortException> in un thread del pool perché è stato chiamato il metodo <xref:System.Threading.Thread.Abort%2A>.  
  
-   Viene generata un'eccezione <xref:System.AppDomainUnloadedException> in un thread del pool perché sta venendo scaricato il dominio dell'applicazione.  
  
-   Common Language Runtime o un processo host termina il thread.  
  
 Per ulteriori informazioni, vedere [eccezioni in thread gestiti](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  In .NET Framework versioni 1.0 e 1.1, Common Language Runtime intercetta automaticamente le eccezioni non gestite nei thread del pool. Ciò potrebbe danneggiare lo stato dell'applicazione e anche provocare il blocco delle applicazioni e il debug potrebbe risultare molto difficoltoso.  
  
### <a name="maximum-number-of-thread-pool-threads"></a>Numero massimo di thread del pool  
 Il numero di operazioni che è possibile accodare nel pool di thread è limitato solo dalla memoria disponibile. Tuttavia, il pool di thread limita il numero di thread che possono essere attivi contemporaneamente nel processo. A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la dimensione predefinita del pool di thread per un processo dipende da diversi fattori, ad esempio la dimensione dello spazio degli indirizzi virtuali. Un processo può chiamare il metodo <xref:System.Threading.ThreadPool.GetMaxThreads%2A> per determinare il numero di thread.  
  
 È possibile controllare il numero massimo di thread usando i metodi <xref:System.Threading.ThreadPool.GetMaxThreads%2A> e <xref:System.Threading.ThreadPool.SetMaxThreads%2A>.  
  
> [!NOTE]
>  In .NET Framework versioni 1.0 e 1.1, la dimensione del pool di thread non può essere impostata dal codice gestito. Il codice che ospita Common Language Runtime può impostare la dimensione tramite `CorSetMaxThreads`, definito in mscoree.h.  
  
### <a name="thread-pool-minimums"></a>Valori minimi del pool di thread  
 Il pool di thread fornisce nuovi thread di lavoro o thread di completamento di I/O su richiesta fino a raggiungere un valore minimo specificato per ogni categoria. È possibile usare il metodo <xref:System.Threading.ThreadPool.GetMinThreads%2A> per ottenere questi valori minimi.  
  
> [!NOTE]
>  Quando la richiesta è bassa, il numero effettivo di thread del pool può scendere sotto i valori minimi.  
  
 Quando viene raggiunto un valore minimo, il pool di thread può creare thread aggiuntivi o attendere il completamento di alcune attività. A partire da [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], il pool di thread crea ed elimina i thread di lavoro per ottimizzare la velocità effettiva, definita come numero di attività completate per unità di tempo. Un numero troppo ridotto di thread potrebbe non usare in modo ottimale le risorse disponibili, mentre troppi thread potrebbero aumentare il conflitto per le risorse.  
  
> [!CAUTION]
>  È possibile usare il metodo <xref:System.Threading.ThreadPool.SetMinThreads%2A> per aumentare il numero minimo di thread inattivi. Tuttavia, un aumento non necessario di questi valori può provocare problemi di prestazioni. Se si avviano troppe attività contemporaneamente, potrebbero sembrare tutte lente. Nella maggior parte dei casi, il pool di thread offre prestazioni migliori con il proprio algoritmo per l'allocazione dei thread.  
  
## <a name="skipping-security-checks"></a>Ignorare i controlli di sicurezza  
 Il pool di thread fornisce anche i metodi <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> e <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType>. Usare questi metodi solo quando si è certi che lo stack del chiamante non sia rilevante per i controlli di sicurezza svolti durante l'esecuzione dell'attività in coda. <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>e <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> entrambi di acquisire lo stack del chiamante, che viene unito nello stack del thread del pool quando il thread inizia a eseguire un'attività. Se è necessario un controllo di sicurezza, deve essere controllato l'intero stack. Sebbene il controllo garantisca la sicurezza, comporta anche una riduzione delle prestazioni.  
  
## <a name="using-the-thread-pool"></a>Uso del pool di thread  
 A partire dal [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], il modo più semplice per usare il pool di thread consiste nell'utilizzare il [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md). Per impostazione predefinita, i tipi di librerie parallele come <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> usano i thread del pool per eseguire le attività. È anche possibile usare il pool di thread chiamando <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> dal codice gestito (o `CorQueueUserWorkItem` dal codice non gestito) e passando un delegato <xref:System.Threading.WaitCallback> che rappresenta il metodo che esegue l'attività. Un altro metodo per usare il pool di thread consiste nell'accodare gli elementi di lavoro correlati a un'operazione di attesa usando il metodo <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> e passando un oggetto <xref:System.Threading.WaitHandle> che, quando viene segnalato o in caso di time out, chiama il metodo rappresentato dal delegato <xref:System.Threading.WaitOrTimerCallback>. I thread del pool vengono usati per richiamare i metodi di callback.  
  
## <a name="threadpool-examples"></a>Esempi di ThreadPool  
 Gli esempi di codice in questa sezione illustrano il pool di thread usando la classe <xref:System.Threading.Tasks.Task>, il metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> e il metodo <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType>.  
  
-   [Esecuzione di attività asincrone con Task Parallel Library](#TaskParallelLibrary)  
  
-   [Esecuzione di codice in modo asincrono con QueueUserWorkItem](#ExecuteCodeWithQUWI)  
  
-   [Invio di dati dell'attività a QueueUserWorkItem](#TaskDataForQUWI)  
  
-   [Uso di RegisterWaitForSingleObject](#RegisterWaitForSingleObject)  
  
<a name="TaskParallelLibrary"></a>   
### <a name="executing-asynchronous-tasks-with-the-task-parallel-library"></a>Esecuzione di attività asincrone con Task Parallel Library  
 L'esempio di codice seguente mostra come creare e usare un oggetto <xref:System.Threading.Tasks.Task> chiamando il metodo <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>. Per un esempio che utilizza il <xref:System.Threading.Tasks.Task%601> classe per restituire un valore da un'attività asincrona, vedere [procedura: restituire un valore da un'attività](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md).  
  
 [!code-csharp[System.Threading.Tasks.Task#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.task/cs/startnew.cs#01)]
 [!code-vb[System.Threading.Tasks.Task#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.task/vb/startnew.vb#01)]  
  
<a name="ExecuteCodeWithQUWI"></a>   
### <a name="executing-code-asynchronously-with-queueuserworkitem"></a>Esecuzione di codice in modo asincrono con QueueUserWorkItem  
 Nell'esempio seguente viene accodata un'attività molto semplice, rappresentata dal metodo `ThreadProc`, usando il metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>.  
  
 [!code-cpp[Conceptual.ThreadPool#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.ThreadPool#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source1.cs#1)]
 [!code-vb[Conceptual.ThreadPool#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source1.vb#1)]  
  
<a name="TaskDataForQUWI"></a>   
### <a name="supplying-task-data-for-queueuserworkitem"></a>Invio di dati dell'attività a QueueUserWorkItem  
 L'esempio di codice seguente usa il metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> per accodare un'attività e fornire i dati per l'attività.  
  
 [!code-cpp[Conceptual.ThreadPool#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.ThreadPool#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source2.cs#2)]
 [!code-vb[Conceptual.ThreadPool#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source2.vb#2)]  
  
<a name="RegisterWaitForSingleObject"></a>   
### <a name="using-registerwaitforsingleobject"></a>Uso di RegisterWaitForSingleObject  
 L'esempio seguente illustra numerose funzionalità di threading.  
  
-   Accodamento di un'attività per l'esecuzione da parte dei thread di <xref:System.Threading.ThreadPool>, con il metodo <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A>.  
  
-   Segnalazione di un'attività da eseguire, con <xref:System.Threading.AutoResetEvent>. Vedere [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md).  
  
-   Gestione di timeout e segnali con un delegato <xref:System.Threading.WaitOrTimerCallback>.  
  
-   Annullamento di un'attività in coda con <xref:System.Threading.RegisteredWaitHandle>.  
  
 [!code-cpp[Conceptual.ThreadPool#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.ThreadPool#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source3.cs#3)]
 [!code-vb[Conceptual.ThreadPool#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source3.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.Tasks.Task>  
 <xref:System.Threading.Tasks.Task%601>  
 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [Procedura: Restituire un valore da un'attività](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)  
 [Thread e Threading](../../../docs/standard/threading/threads-and-threading.md)  
 [I/O di file asincrono](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [Timer](../../../docs/standard/threading/timers.md)
