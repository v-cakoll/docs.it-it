---
title: Pool di thread gestiti
description: Informazioni sui pool di thread .NET che include thread di lavoro in background
ms.date: 08/02/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- thread pooling [.NET]
- thread pools [.NET]
- threading [.NET], thread pool
- threading [.NET], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
ms.openlocfilehash: 2671ce7c9721b15de8a3805da27040e973a62804
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79400631"
---
# <a name="the-managed-thread-pool"></a>Pool di thread gestiti

La classe <xref:System.Threading.ThreadPool?displayProperty=nameWithType> fornisce all'applicazione un pool di thread di lavoro gestiti dal sistema, per consentire di concentrarsi sulle attività dell'applicazione anziché sulla gestione dei thread. Se si dispone di attività brevi che richiedono l'elaborazione in background, il pool di thread gestiti consente di sfruttare in modo semplice i vantaggi di più thread. L'uso del pool di thread è molto più semplice in Framework 4 e versioni successive, perché è possibile creare oggetti <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> che eseguono attività asincrone nei thread del pool.  
  
.NET usa i thread del pool per numerosi scopi, tra cui operazioni [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md), completamento I/O asincrono, callback [timer](timers.md), operazioni di attesa registrate, chiamate asincrone di metodi tramite delegati e connessioni socket <xref:System.Net?displayProperty=nameWithType>.  

## <a name="thread-pool-characteristics"></a>Caratteristiche del pool di thread

I thread del pool sono thread in [background](foreground-and-background-threads.md). Ogni thread usa la dimensione dello stack predefinita, viene eseguito con la priorità predefinita e si trova in un apartment a thread multipli. Dopo il completamento dell'attività, il thread del pool torna in una coda di thread in attesa. Da questo momento il thread può essere riusato, evitando in questo modo la necessità di creare un nuovo thread per ogni attività.
  
È presente un solo pool di thread per processo.  
  
### <a name="exceptions-in-thread-pool-threads"></a>Eccezioni nei thread del pool

Le eccezioni non gestite nei thread del pool terminano il processo. Sono previste tre eccezioni a questa regola:  
  
- L'eccezione <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> viene generata in un thread del pool perché è stato chiamato <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  
- L'eccezione <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> viene generata in un thread del pool perché è in corso lo scaricamento del dominio dell'applicazione.  
- Common Language Runtime o un processo host termina il thread.  
  
Per altre informazioni, vedere [Eccezioni in thread gestiti](exceptions-in-managed-threads.md).  
  
### <a name="maximum-number-of-thread-pool-threads"></a>Numero massimo di thread del pool

Il numero di operazioni che possono essere accodate al pool di thread è limitato solo dalla memoria disponibile. Tuttavia il pool di thread limita il numero di thread che possono essere attivi contemporaneamente nel processo. Se tutti i thread del pool sono occupati, gli elementi di lavoro aggiuntivi vengono accodati fino a quando non tornano disponibili thread per l'esecuzione degli elementi stessi. A partire da .NET Framework 4 la dimensione predefinita del pool di thread per un processo dipende da diversi fattori, ad esempio la dimensione dello spazio degli indirizzi virtuali. Un processo può chiamare il metodo <xref:System.Threading.ThreadPool.GetMaxThreads%2A?displayProperty=nameWithType> per determinare il numero di thread.  
  
È possibile controllare il numero massimo di thread usando i metodi <xref:System.Threading.ThreadPool.GetMaxThreads%2A?displayProperty=nameWithType> e <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.  

> [!NOTE]
> Il codice che ospita Common Language Runtime [`ICorThreadpool::CorSetMaxThreads`](../../framework/unmanaged-api/hosting/icorthreadpool-corsetmaxthreads-method.md) può impostare la dimensione utilizzando il metodo .  
  
### <a name="thread-pool-minimums"></a>Valori minimi del pool di thread

Il pool di thread fornisce nuovi thread di lavoro o thread di completamento di I/O su richiesta fino a raggiungere un valore minimo specificato per ogni categoria. È possibile usare il metodo <xref:System.Threading.ThreadPool.GetMinThreads%2A?displayProperty=nameWithType> per ottenere questi valori minimi.  
  
> [!NOTE]
> Quando la richiesta è bassa, il numero effettivo di thread del pool può scendere sotto i valori minimi.  
  
Quando viene raggiunto un valore minimo, il pool di thread può creare thread aggiuntivi o attendere il completamento di alcune attività. A partire da .NET Framework 4 il pool di thread crea ed elimina thread di lavoro per ottimizzare la velocità effettiva, definita come numero di attività completate per unità di tempo. Un numero troppo ridotto di thread potrebbe non usare in modo ottimale le risorse disponibili, mentre troppi thread potrebbero aumentare il conflitto per le risorse.  
  
> [!CAUTION]
> È possibile usare il metodo <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> per aumentare il numero minimo di thread inattivi. Tuttavia, un aumento non necessario di questi valori può provocare problemi di prestazioni. Se si avviano troppe attività contemporaneamente, potrebbero sembrare tutte lente. Nella maggior parte dei casi, il pool di thread offre prestazioni migliori con il proprio algoritmo per l'allocazione dei thread.  

## <a name="using-the-thread-pool"></a>Uso del pool di thread

A partire da .NET Framework 4 il modo più semplice per usare il pool di thread consiste nell'uso di [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md). Per impostazione predefinita i tipi TPL come <xref:System.Threading.Tasks.Task> e <xref:System.Threading.Tasks.Task%601> usano i thread del pool per eseguire le attività.

È inoltre possibile utilizzare il <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> pool di [`ICorThreadpool::CorQueueUserWorkItem`](../../framework/unmanaged-api/hosting/icorthreadpool-corqueueuserworkitem-method.md) thread chiamando da codice <xref:System.Threading.WaitCallback?displayProperty=nameWithType> gestito (o da codice non gestito) e passando un delegato che rappresenta il metodo che esegue l'attività.

Un altro metodo per usare il pool di thread consiste nell'accodare gli elementi di lavoro correlati a un'operazione di attesa usando il metodo <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> e passando un oggetto <xref:System.Threading.WaitHandle?displayProperty=nameWithType> che, quando viene segnalato o in caso di time out, chiama il metodo rappresentato dal delegato <xref:System.Threading.WaitOrTimerCallback?displayProperty=nameWithType>. I thread del pool vengono usati per richiamare i metodi di callback.  

Per esempi, vedere le pagine delle API di riferimento.
  
## <a name="skipping-security-checks"></a>Ignorare i controlli di sicurezza

Il pool di thread fornisce anche i metodi <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> e <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType>. Usare questi metodi solo quando si è certi che lo stack del chiamante non sia rilevante per i controlli di sicurezza svolti durante l'esecuzione dell'attività in coda. I metodi <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> e <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> consentono entrambi di acquisire lo stack del chiamante, che viene unito nello stack del thread del pool quando il thread inizia a eseguire un'attività. Se è necessario un controllo di sicurezza, deve essere controllato l'intero stack. Sebbene il controllo garantisca la sicurezza, comporta anche una riduzione delle prestazioni.  

## <a name="when-not-to-use-thread-pool-threads"></a>Quando non usare i thread del pool

Vi sono diversi scenari in cui è opportuno creare e gestire i propri thread anziché usare i thread del pool, come nei casi seguenti:  
  
- È necessario un thread in primo piano.  
- È necessario che un thread abbia una priorità specifica.  
- Sono presenti attività che causano il blocco del thread per lunghi periodi di tempo. Il pool di thread prevede un numero massimo di thread, pertanto un numero elevato di thread del pool bloccati potrebbe impedire l'avvio delle attività.  
- È necessario inserire thread di un apartment a thread singolo. Tutti i thread di <xref:System.Threading.ThreadPool> sono inclusi in apartment a thread multipli.  
- È necessario disporre di un'identità stabile associata al thread o dedicare un thread a un'attività.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md)
- [Procedura: Restituire un valore da un'attività](../parallel-programming/how-to-return-a-value-from-a-task.md)
- [Funzionalità e oggetti di threading](threading-objects-and-features.md)
- [Thread e threading](threads-and-threading.md)
- [I/O di file asincrono](../io/asynchronous-file-i-o.md)
- [Timer](timers.md)
