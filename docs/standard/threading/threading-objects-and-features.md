---
title: Oggetti e funzionalità del threading
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
ms.openlocfilehash: dd9b7b8cb194353d0a1c285af10d54dc7366896e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73128963"
---
# <a name="threading-objects-and-features"></a>Oggetti e funzionalità del threading

Oltre alla classe <xref:System.Threading.Thread?displayProperty=nameWithType>, .NET offre diverse classi utili per lo sviluppo di applicazioni multithreading. Gli articoli seguenti offrono una panoramica di queste classi:

|Titolo|Descrizione|  
|-----------|-----------------|  
|[Pool di thread gestiti](the-managed-thread-pool.md)|Descrive la classe <xref:System.Threading.ThreadPool?displayProperty=nameWithType> che offre un pool di thread di lavoro gestiti da .NET.|  
|[Timer](timers.md)|Descrive i timer .NET che possono essere usati in un ambiente con multithreading.|
|[Panoramica delle primitive di sincronizzazione](overview-of-synchronization-primitives.md)|Descrive i tipi che possono essere usati per sincronizzare l'accesso a una risorsa condivisa o controllare l'interazione tra thread.|
|[EventWaitHandle](eventwaithandle.md)|Descrive la classe <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> che rappresenta un evento di sincronizzazione di thread.|
|[CountdownEvent](countdownevent.md)|Descrive la classe <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> che rappresenta un evento di sincronizzazione di thread che viene impostato quando il conteggio è zero.|
|[Mutex](mutexes.md)|Descrive la classe <xref:System.Threading.Mutex?displayProperty=nameWithType> che concede accesso esclusivo a una risorsa condivisa.|
|[Semaphore e SemaphoreSlim](semaphore-and-semaphoreslim.md)|Descrive la classe <xref:System.Threading.Semaphore?displayProperty=nameWithType>, che limita il numero di thread che possono accedere simultaneamente a una risorsa condivisa o a un pool di risorse.|
|[Barriera](barrier.md)|Descrive la classe <xref:System.Threading.Barrier?displayProperty=nameWithType> che implementa lo schema della barriera per il coordinamento dei thread nelle operazioni a più fasi.|
|[Spinlock](spinlock.md)|Descrive la struttura <xref:System.Threading.SpinLock?displayProperty=nameWithType>, che rappresenta un'alternativa leggera alla classe <xref:System.Threading.Monitor?displayProperty=nameWithType> per alcuni scenari di blocco di basso livello.|
|[SpinWait](spinwait.md)|Descrive la struttura <xref:System.Threading.SpinWait?displayProperty=nameWithType>, che fornisce supporto per l'attesa basata su rotazione.|

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
