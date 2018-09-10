---
title: Oggetti e funzionalità del threading
ms.date: 08/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d56d962279120a03a6e4b89154ac1429ea5479e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44039329"
---
# <a name="threading-objects-and-features"></a>Oggetti e funzionalità del threading

Oltre alla classe <xref:System.Threading.Thread?displayProperty=nameWithType>, .NET offre diverse classi utili per lo sviluppo di applicazioni multithreading. Gli articoli seguenti offrono una panoramica di queste classi:

|Titolo|Descrizione|  
|-----------|-----------------|  
|[Pool di thread gestiti](the-managed-thread-pool.md)|Descrive la classe <xref:System.Threading.ThreadPool?displayProperty=nameWithType> che offre un pool di thread di lavoro gestiti da .NET.|  
|[Timer](timers.md)|Descrive i timer che possono essere usati in un ambiente multithreading.|
|[Cenni preliminari sulle primitive di sincronizzazione](overview-of-synchronization-primitives.md)|Descrive le classi che possono essere usate per sincronizzare l'accesso ai dati o controllare l'interazione tra thread.|
|[EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|Descrive gli handle di attesa eventi gestiti, usati per sincronizzare le attività dei thread effettuando segnalazioni e attendendo segnali.|
|[Mutex](mutexes.md)|Descrive come usare un <xref:System.Threading.Mutex?displayProperty=nameWithType> per sincronizzare l'accesso a un oggetto o creare i propri meccanismi di sincronizzazione.|
|[Operazioni interlocked](interlocked-operations.md)|Descrive la classe <xref:System.Threading.Interlocked?displayProperty=nameWithType> che offre operazioni atomiche per variabili condivise da più thread.|
|[Blocchi in lettura/scrittura](reader-writer-locks.md)|Descrive la classe <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType> che offre la semantica autore singolo/più lettori.|
|[Semaphore e SemaphoreSlim](semaphore-and-semaphoreslim.md)|Descrive la classe <xref:System.Threading.Semaphore?displayProperty=nameWithType> e illustra come usarla per controllare l'accesso alle risorse limitate.|
|[Barrier](barrier.md)|Descrive la classe <xref:System.Threading.Barrier?displayProperty=nameWithType> che implementa lo schema della barriera per il coordinamento dei thread nelle operazioni in più fasi.|
|[SpinLock](spinlock.md)|Descrive la classe <xref:System.Threading.SpinLock?displayProperty=nameWithType>, un'alternativa semplice alla classe <xref:System.Threading.Monitor?displayProperty=nameWithType> per alcuni scenari di basso livello.|
|[SpinWait](spinwait.md)|Descrive la classe <xref:System.Threading.SpinWait?displayProperty=nameWithType>, una primitiva di sincronizzazione di basso livello che esegue la rotazione con stato occupato prima di iniziare un'attesa basata sul kernel.|

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [Utilizzo di thread e threading](using-threads-and-threading.md)
- [I/O di file asincrono](../io/asynchronous-file-i-o.md)
- [Programmazione parallela](../parallel-programming/index.md)
- [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md)
