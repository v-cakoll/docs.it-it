---
title: "Oggetti e funzionalità del threading"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a73e5c60a661c171e9e46e6307484cf5e0e6b80
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="threading-objects-and-features"></a>Oggetti e funzionalità del threading
.NET Framework fornisce numerosi oggetti che consentono di creare e gestire applicazioni multithread. I thread gestiti sono rappresentati dalla classe <xref:System.Threading.Thread>. La classe <xref:System.Threading.ThreadPool> consente di creare e gestire facilmente attività multithreading in background. La classe <xref:System.ComponentModel.BackgroundWorker> ha la stessa funzione per le attività che interagiscono con l'interfaccia utente. La classe <xref:System.Threading.Timer> esegue attività in background a intervalli fissi.  
  
 Esistono anche numerose classi che sincronizzano le attività dei thread, tra cui le classi <xref:System.Threading.Semaphore> e <xref:System.Threading.EventWaitHandle> introdotte in .NET Framework versione 2.0. Le funzionalità di queste classi sono messe a confronto nella [panoramica sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Pool di thread gestiti](../../../docs/standard/threading/the-managed-thread-pool.md)  
 Illustra la classe **ThreadPool**, che consente di richiedere un thread per eseguire un'attività senza dover gestire manualmente il thread.  
  
 [Timer](../../../docs/standard/threading/timers.md)  
 Illustra come usare un **timer** per specificare un delegato da chiamare a un'ora specificata.  
  
 [Monitoraggi](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 Illustra come usare la classe **Monitor** per sincronizzare l'accesso a un membro o per creare i propri tipi di gestione dei thread.  
  
 [Handle di attesa](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 Descrive la classe <xref:System.Threading.WaitHandle>, la classe base astratta per gli handle di attesa eventi, i mutex e i semafori, che consente di attendere più eventi di sincronizzazione.  
  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 Descrive gli handle di attesa eventi gestiti, usati per sincronizzare le attività dei thread effettuando segnalazioni e attendendo segnali.  
  
 [Mutex](../../../docs/standard/threading/mutexes.md)  
 Viene illustrato come utilizzare un <xref:System.Threading.Mutex> per sincronizzare l'accesso a un oggetto o per creare i propri meccanismi di sincronizzazione.  
  
 [Operazioni interlocked](../../../docs/standard/threading/interlocked-operations.md)  
 Illustra come usare la classe <xref:System.Threading.Interlocked> per incrementare o decrementare un valore e archiviarlo in una sola operazione atomica.  
  
 [Blocchi in lettura/scrittura](../../../docs/standard/threading/reader-writer-locks.md)  
 Definisce un blocco che implementa la semantica writer singolo/visualizzatori multipli.  
  
 [Semaphore e SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 Descrive gli oggetti <xref:System.Threading.Semaphore> e illustra come usarli per controllare l'accesso alle risorse limitate.  
  
 [Cenni preliminari sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Confronta le funzionalità delle classi di .NET Framework fornite per bloccare e sincronizzare i thread gestiti.  
  
 [Barrier](../../../docs/standard/threading/barrier.md)  
 Descrive gli oggetti <xref:System.Threading.Barrier> che implementano lo schema della barriera per il coordinamento dei thread nelle operazioni in più fasi.  
  
 [SpinLock](../../../docs/standard/threading/spinlock.md)  
 Descrive <xref:System.Threading.SpinLock>, una semplice alternativa alla classe Monitor per alcuni scenari di basso livello.  
  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 Descrive <xref:System.Threading.SpinWait>, una primitiva di sincronizzazione di basso livello che esegue la rotazione con stato occupato prima di iniziare un'attesa basata sul kernel.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Threading.Thread>  
 Rende disponibile la documentazione di riferimento per la classe **Thread**, che rappresenta un thread gestito, indipendentemente dal fatto che derivi da codice non gestito o sia stato creato in un'applicazione gestita.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Consente le attività in background che interagiscono con l'interfaccia utente, comunicando tramite gli eventi generati nel thread di interfaccia utente.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [I/O di file asincrono](../../../docs/standard/io/asynchronous-file-i-o.md)  
 Descrive come le porte di completamento asincrono di I/O usano il pool di thread per richiedere l'elaborazione solo quando un'operazione di input/output viene completata.  
  
 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Descrive l'approccio consigliato per la programmazione multithreading in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] e versioni successive.
