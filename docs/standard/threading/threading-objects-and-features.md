---
title: Oggetti e funzionalità del threading
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a355c2e996ddb00dad804dfeb22987923d91aa6
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144520"
---
# <a name="threading-objects-and-features"></a>Oggetti e funzionalità del threading

Oltre alla classe <xref:System.Threading.Thread?displayProperty=nameWithType>, .NET offre diverse classi utili per lo sviluppo di applicazioni multithreading. Gli articoli seguenti offrono una panoramica di queste classi:

|Titolo|Description|  
|-----------|-----------------|  
|[Pool di thread gestiti](the-managed-thread-pool.md)|Descrive la classe <xref:System.Threading.ThreadPool?displayProperty=nameWithType> che offre un pool di thread di lavoro gestiti da .NET.|  
|[Timer](timers.md)|Descrive i timer .NET che possono essere usati in un ambiente con multithreading.|
|[Cenni preliminari sulle primitive di sincronizzazione](overview-of-synchronization-primitives.md)|Descrive i tipi che possono essere usati per sincronizzare l'accesso a una risorsa condivisa o controllare l'interazione tra thread.|
|[EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|Descrive gli handle di attesa eventi gestiti, usati per sincronizzare le attività dei thread effettuando segnalazioni e attendendo segnali.|
|[Mutex](mutexes.md)|Descrive <xref:System.Threading.Mutex?displayProperty=nameWithType>, che concede l'accesso esclusivo a una risorsa condivisa.|
|[Semaphore e SemaphoreSlim](semaphore-and-semaphoreslim.md)|Descrive la classe <xref:System.Threading.Semaphore?displayProperty=nameWithType>, che limita il numero di thread che possono accedere simultaneamente a una risorsa condivisa o a un pool di risorse.|
|[Barrier](barrier.md)|Descrive la classe <xref:System.Threading.Barrier?displayProperty=nameWithType> che implementa lo schema della barriera per il coordinamento dei thread nelle operazioni in più fasi.|
|[SpinLock](spinlock.md)|Descrive la struttura <xref:System.Threading.SpinLock?displayProperty=nameWithType>, che rappresenta un'alternativa leggera alla classe <xref:System.Threading.Monitor?displayProperty=nameWithType> per alcuni scenari di blocco di basso livello.|
|[SpinWait](spinwait.md)|Descrive la struttura <xref:System.Threading.SpinWait?displayProperty=nameWithType>, che fornisce supporto per l'attesa basata su rotazione.|

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [Utilizzo di thread e threading](using-threads-and-threading.md)
- [Asynchronous File I/O](../io/asynchronous-file-i-o.md)
- [Programmazione parallela](../parallel-programming/index.md)
- [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md)
