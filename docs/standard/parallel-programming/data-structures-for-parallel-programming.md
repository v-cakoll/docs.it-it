---
title: Strutture di dati per la programmazione in parallelo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f35c5382455021f0a001604367e59204ce4ad93c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="data-structures-for-parallel-programming"></a>Strutture di dati per la programmazione in parallelo
.NET Framework versione 4 introduce numerosi nuovi tipi che consentono la programmazione in parallelo, tra cui un set di classi collection simultanee, le primitive di sincronizzazione leggera e tipi per l'inizializzazione differita. È possibile utilizzare questi tipi con qualsiasi codice di applicazione multithreading, inclusa la libreria Task Parallel Library e PLINQ.  
  
## <a name="concurrent-collection-classes"></a>Classi Collection simultanei  
 Le classi di raccolte di <xref:System.Collections.Concurrent?displayProperty=nameWithType> dello spazio dei nomi forniscono thread-safe aggiunta e rimozione di operazioni che, se possibile, evitare blocchi e utilizza il blocco con granularità fine in cui i blocchi sono necessari. A differenza delle raccolte che sono state introdotte in .NET Framework versioni 1.0 e 2.0, una classe collection simultanee non richiede il codice utente per l'acquisizione di blocchi quando accede agli elementi. Le classi di raccolta simultanea possono migliorare significativamente le prestazioni dei tipi, ad esempio <xref:System.Collections.ArrayList?displayProperty=nameWithType> e <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (con blocco implementato dall'utente) in scenari in cui più thread aggiungere e rimuovere elementi da una raccolta.  
  
 Nella tabella seguente sono elencate le nuove classi di raccolte simultanee:  
  
|Tipo|Descrizione|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|Fornisce funzionalità di blocco e limitazione per le raccolte thread-safe che implementano <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType>. Thread producer si bloccano se non sono disponibili slot o se la raccolta è di tipo completa. I thread consumer si bloccano se la raccolta è vuota. Questo tipo supporta inoltre l'accesso non bloccante dal producer e consumer. <xref:System.Collections.Concurrent.BlockingCollection%601>può essere utilizzato come classe base o l'archivio di backup per fornire il blocco e limitazione per qualsiasi classe di raccolta che supporta <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|Un'implementazione del contenitore thread-safe che fornisce scalabili e aggiungere le operazioni.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|Un tipo di dizionario simultaneo e scalabile.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|Una coda FIFO simultanea e scalabile.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|Stack LIFO simultaneo e scalabile.|  
  
 Per altre informazioni, vedere [Raccolte thread-safe](../../../docs/standard/collections/thread-safe/index.md).  
  
## <a name="synchronization-primitives"></a>Primitive di sincronizzazione  
 Le primitive di sincronizzazione di nuovo nel <xref:System.Threading?displayProperty=nameWithType> dello spazio dei nomi consentono di concorrenza con granularità fine e migliorare le prestazioni evitando dispendiosi meccanismi di blocco rilevati nel codice multithreading legacy. Alcuni dei nuovi tipi, ad esempio <xref:System.Threading.Barrier?displayProperty=nameWithType> e <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> non esiste alcuna controparte nelle versioni precedenti di .NET Framework.  
  
 Nella tabella seguente sono elencati i nuovi tipi di sincronizzazione:  
  
|Tipo|Descrizione|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|Consente di utilizzare un algoritmo in parallelo, fornendo un punto in cui ogni attività possono segnalare l'arrivo e quindi si bloccano fino a quando non sono arrivato alcune o tutte le attività di più thread. Per altre informazioni, vedere [Barriera](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|Semplifica gli scenari di fork e join fornendo un meccanismo semplice rendezvous. Per ulteriori informazioni, vedere [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|Primitiva di sincronizzazione simile a <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>. <xref:System.Threading.ManualResetEventSlim>è più semplice, ma può essere utilizzato solo per comunicazioni interne del processo. Per ulteriori informazioni, vedere [ManualResetEvent e ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md).|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|Primitiva di sincronizzazione che limita il numero di thread che possono accedere simultaneamente a una risorsa o a un pool di risorse. Per ulteriori informazioni, vedere [Semaphore e SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|Una primitiva di blocco a esclusione reciproca che determina che il thread che sta tentando di acquisire il blocco di attesa in un ciclo, o *selezione*, per un periodo di tempo prima di restituire il quantum. Negli scenari in cui l'attesa del blocco deve essere breve, <xref:System.Threading.SpinLock> offre migliori prestazioni rispetto alle altre forme di blocco. Per ulteriori informazioni, vedere [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|Un tipo di piccolo e leggero che eseguirà spin per un determinato periodo e infine inserito il thread in uno stato di attesa, se viene superato il numero di selezione.  Per ulteriori informazioni, vedere [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Per altre informazioni, vedere:  
  
-   [Procedura: Usare SpinLock per la sincronizzazione di basso livello](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [Procedura: sincronizzare operazioni simultanee con una barriera](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="lazy-initialization-classes"></a>Classi di inizializzazione differita  
 Con inizializzazione differita, la memoria per un oggetto non è allocata fino a quando non è necessaria. L'inizializzazione differita può migliorare le prestazioni suddividendo le allocazioni di oggetti in modo uniforme per tutta la durata di un programma. È possibile abilitare l'inizializzazione differita per qualsiasi tipo personalizzato eseguendo il wrapping del tipo <xref:System.Lazy%601>.  
  
 Nella tabella seguente sono elencati i tipi di inizializzazione differita:  
  
|Tipo|Descrizione|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|Fornisce leggero, thread-safe con inizializzazione differita.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|Fornisce un valore di inizializzazione differita in base al thread, con ogni thread in modo differito-richiamando la funzione di inizializzazione.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|Fornisce metodi statici che evitare la necessità di allocare un'istanza dedicata con inizializzazione differita. Al contrario, usano i riferimenti per verificare le destinazioni sono state inizializzate al momento dell'accesso.|  
  
 Per altre informazioni, vedere [Inizializzazione differita](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="aggregate-exceptions"></a>Eccezioni di aggregazione  
 Il <xref:System.AggregateException?displayProperty=nameWithType> tipo può essere usato per acquisire più eccezioni generate contemporaneamente su un thread separato e restituiscono al thread di unione come singola eccezione. Il <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> tipi e PLINQ utilizzano <xref:System.AggregateException> ampiamente a questo scopo. Per ulteriori informazioni, vedere [NIB: procedura: gestire le eccezioni generate dalle attività](http://msdn.microsoft.com/en-us/d6c47ec8-9de9-4880-beb3-ff19ae51565d) e [come: gestire le eccezioni in una Query PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 <xref:System.Threading?displayProperty=nameWithType>  
 [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)
