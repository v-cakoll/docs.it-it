---
title: Panoramica delle primitive di sincronizzazione
description: Informazioni sulle primitive di sincronizzazione di thread .NET usate per sincronizzare l'accesso a una risorsa condivisa o controllare l'interazione tra thread
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization, threads
- threading [.NET],synchronizing threads
- managed threading
ms.assetid: b782bcb8-da6a-4c6a-805f-2eb46d504309
ms.openlocfilehash: 43f78c914b7cb01f9b0de4c258d5882548e52790
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106588"
---
# <a name="overview-of-synchronization-primitives"></a>Panoramica delle primitive di sincronizzazione

.NET offre una gamma di tipi che è possibile usare per sincronizzare l'accesso a una risorsa condivisa o coordinare l'interazione tra thread.

> [!IMPORTANT]
> Usare la stessa istanza di primitiva di sincronizzazione per proteggere l'accesso a una risorsa condivisa. Se si usano istanze di primitive di sincronizzazione diverse per proteggere la stessa risorsa, sarà possibile aggirare la protezione fornita da una primitiva di sincronizzazione.

## <a name="waithandle-class-and-lightweight-synchronization-types"></a>Classe WaitHandle e tipi di sincronizzazione leggeri

Più primitive di sincronizzazione .NET derivano dalla classe <xref:System.Threading.WaitHandle?displayProperty=nameWithType>, che incapsula un handle di sincronizzazione del sistema operativo nativo e usa un meccanismo di segnalazione per l'interazione tra thread. Tali classi includono:

- <xref:System.Threading.Mutex?displayProperty=nameWithType>, che concede l'accesso esclusivo a una risorsa condivisa. Lo stato di un mutex viene segnalato se nessun thread lo possiede.
- <xref:System.Threading.Semaphore?displayProperty=nameWithType>, che limita il numero di thread che possono accedere simultaneamente a una risorsa condivisa o a un pool di risorse. Lo stato di un semaforo denominato è impostato come segnalato quando il relativo conteggio è maggiore di zero e come non segnalato quando il relativo conteggio è zero.
- <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>, che rappresenta un evento di sincronizzazione di thread e può trovarsi in uno stato segnalato o non segnalato.
- <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>, che deriva da <xref:System.Threading.EventWaitHandle> e, quando segnalata si reimposta automaticamente in uno stato non segnalato dopo il rilascio di un singolo thread in attesa.
- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>, che deriva da <xref:System.Threading.EventWaitHandle> e, quando segnalata, rimane in uno stato segnalato finché non viene chiamato il metodo <xref:System.Threading.EventWaitHandle.Reset%2A>.

In .NET Framework, poiché <xref:System.Threading.WaitHandle> deriva da <xref:System.MarshalByRefObject?displayProperty=nameWithType>, questi tipi possono essere usati per sincronizzare le attività dei thread tra limiti dei domini delle applicazioni.

In .NET Framework e .NET Core, alcuni di questi tipi possono rappresentare handle di sincronizzazione di sistema denominati, che sono visibili in tutto il sistema operativo e possono essere usati per la sincronizzazione interprocesso:

- <xref:System.Threading.Mutex> (.NET Framework e .NET Core).
- <xref:System.Threading.Semaphore> (.NET Framework e .NET Core in Windows).
- <xref:System.Threading.EventWaitHandle> (.NET Framework e .NET Core in Windows).

Per altre informazioni, vedere le informazioni di riferimento sull'API <xref:System.Threading.WaitHandle>.

I tipi di sincronizzazione leggeri non si basano su handle del sistema operativo sottostanti e in genere offrono prestazioni migliori. Tuttavia, non possono essere usati per la sincronizzazione interprocesso. Usare tali tipi per la sincronizzazione dei thread all'interno di un'applicazione.

Alcuni di questi tipi rappresentano alternative ai tipi derivati da <xref:System.Threading.WaitHandle>. Ad esempio, <xref:System.Threading.SemaphoreSlim> è un'alternativa leggera a <xref:System.Threading.Semaphore>.

## <a name="synchronization-of-access-to-a-shared-resource"></a>Sincronizzazione dell'accesso a una risorsa condivisa

.NET offre una gamma di primitive di sincronizzazione per controllare l'accesso a una risorsa condivisa da parte di più thread.

### <a name="monitor-class"></a>Monitor (classe)

La classe <xref:System.Threading.Monitor?displayProperty=nameWithType> concede l'accesso con esclusione reciproca a una risorsa condivisa tramite l'acquisizione o il rilascio di un blocco sull'oggetto che identifica la risorsa. Mentre è attivo un blocco, il thread che contiene il blocco può ancora acquisire e rilasciare il blocco. Gli altri thread non possono acquisire il blocco e il metodo <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> attende il rilascio del blocco. Il metodo <xref:System.Threading.Monitor.Enter%2A> acquisisce un blocco rilasciato. È anche possibile usare il metodo <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> per specificare l'intervallo di tempo durante il quale un thread cerca di acquisire un blocco. Poiché la classe <xref:System.Threading.Monitor> presenta affinità di thread, il thread che ha acquisito un blocco deve rilasciare il blocco chiamando il metodo <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>.

È possibile coordinare l'interazione tra i thread che acquisiscono un blocco sullo stesso oggetto usando i metodi <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType>.

Per altre informazioni, vedere le informazioni di riferimento sull'API <xref:System.Threading.Monitor>.

> [!NOTE]
> Usare l'istruzione [lock](../../csharp/language-reference/keywords/lock-statement.md) in C# e l'istruzione [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) in Visual Basic per sincronizzare l'accesso a una risorsa condivisa invece di usare direttamente la classe <xref:System.Threading.Monitor>. Queste istruzioni vengono implementate usando i metodi <xref:System.Threading.Monitor.Enter%2A> e <xref:System.Threading.Monitor.Exit%2A> e un blocco `try…finally` per garantire che il blocco acquisito venga sempre rilasciato.

### <a name="mutex-class"></a>Mutex (classe)

La classe <xref:System.Threading.Mutex?displayProperty=nameWithType>, analogamente a <xref:System.Threading.Monitor>, concede l'accesso esclusivo a una risorsa condivisa. Usare uno degli overload del metodo [Mutex.WaitOne](<xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>) per richiedere la proprietà di un mutex. Analogamente a <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> presenta affinità di thread e il thread che ha acquisito un mutex deve rilasciarlo chiamando il metodo <xref:System.Threading.Mutex.ReleaseMutex%2A?displayProperty=nameWithType>.

A differenza di <xref:System.Threading.Monitor>, la classe <xref:System.Threading.Mutex> può essere usata per la sincronizzazione interprocesso. A tale scopo, usare un mutex denominato, visibile in tutto il sistema operativo. Per creare un'istanza di mutex denominata, usare un [costruttore di Mutex](<xref:System.Threading.Mutex.%23ctor%2A>) che specifica un nome. È anche possibile chiamare il metodo <xref:System.Threading.Mutex.OpenExisting%2A?displayProperty=nameWithType> per aprire un mutex di sistema denominato esistente.
  
Per altre informazioni, vedere l'articolo [Mutex](mutexes.md) e le informazioni di riferimento sull'API <xref:System.Threading.Mutex>.

### <a name="spinlock-structure"></a>Struttura SpinLock

La struttura <xref:System.Threading.SpinLock?displayProperty=nameWithType>, analogamente a <xref:System.Threading.Monitor>, concede l'accesso esclusivo a una risorsa condivisa in base alla disponibilità di un blocco. Quando <xref:System.Threading.SpinLock> cerca di acquisire un blocco che non è disponibile, rimane in attesa in un ciclo eseguendo controlli ripetuti finché il blocco non diventa disponibile.

Per altre informazioni sui vantaggi e sugli svantaggi dell'uso del meccanismo di spinlock, vedere l'articolo [SpinLock](spinlock.md) e le informazioni di riferimento sull'API <xref:System.Threading.SpinLock>.

### <a name="readerwriterlockslim-class"></a>Classe ReaderWriterLockSlim

La classe <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType> concede l'accesso esclusivo a una risorsa condivisa per la scrittura e permette a più thread di accedere alla risorsa simultaneamente per la lettura. È possibile usare <xref:System.Threading.ReaderWriterLockSlim> per sincronizzare l'accesso a una struttura dei dati condivisa che supporta operazioni di lettura thread-safe, ma richiede accesso esclusivo per eseguire le operazioni di scrittura. Quando un thread richiede l'accesso esclusivo, ad esempio chiamando il metodo <xref:System.Threading.ReaderWriterLockSlim.EnterWriteLock%2A?displayProperty=nameWithType>, le richieste di lettore e scrittore successive vengono bloccate finché tutti i lettori esistenti non escono dal blocco e lo scrittore non è entrato e uscito dal blocco.
  
Per altre informazioni, vedere le informazioni di riferimento sull'API <xref:System.Threading.ReaderWriterLockSlim>.

### <a name="semaphore-and-semaphoreslim-classes"></a>Classi Semaphore e SemaphoreSlim

Le classi <xref:System.Threading.Semaphore?displayProperty=nameWithType> e <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> limitano il numero di thread che possono accedere simultaneamente a una risorsa condivisa o a un pool di risorse. I thread aggiuntivi che richiedono la risorsa rimangono in attesa finché un thread non rilascia il semaforo. Poiché il semaforo non presenta affinità di thread, un thread può acquisire il semaforo e un altro può rilasciarlo.

La classe <xref:System.Threading.SemaphoreSlim> è un'alternativa leggera a <xref:System.Threading.Semaphore> e può essere usata solo per la sincronizzazione all'interno di un unico processo.

In Windows è possibile usare <xref:System.Threading.Semaphore> per la sincronizzazione interprocesso. A tale scopo, creare un'istanza di <xref:System.Threading.Semaphore> che rappresenta un semaforo di sistema denominato usando uno dei [costruttori di Semaphore](<xref:System.Threading.Semaphore.%23ctor%2A>) che specifica un nome o il metodo <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType>. <xref:System.Threading.SemaphoreSlim> non supporta semafori di sistema denominati.

Per altre informazioni, vedere l'articolo [Semaphore e SemaphoreSlim](semaphore-and-semaphoreslim.md) e le informazioni di riferimento sull'API <xref:System.Threading.Semaphore> o <xref:System.Threading.SemaphoreSlim>.

## <a name="thread-interaction-or-signaling"></a>Interazione tra thread o segnalazione

L'interazione tra thread (o segnalazione tra thread) significa che un thread deve attendere la notifica, o un segnale, da uno o più thread per procedere. Se, ad esempio, il thread A chiama il metodo <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> del thread B, il thread A è bloccato fino al completamento del thread B. Le primitive di sincronizzazione descritte nella sezione precedente forniscono un meccanismo diverso per la segnalazione. Rilasciando un blocco, un thread notifica a un altro thread che quest'ultimo può procedere acquisendo il blocco.

Questa sezione descrive i costrutti di segnalazione aggiuntivi forniti da .NET.

### <a name="eventwaithandle-autoresetevent-manualresetevent-and-manualreseteventslim-classes"></a>Classi EventWaitHandle, AutoResetEvent, ManualResetEvent e ManualResetEventSlim

La classe <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> rappresenta un evento di sincronizzazione di thread.

Un evento di sincronizzazione può trovarsi in uno stato segnalato o non segnalato. Quando lo stato di un evento è non segnalato, un thread che chiama l'overload <xref:System.Threading.WaitHandle.WaitOne%2A?> dell'evento rimane bloccato fino a quando un evento non viene segnalato. Il metodo <xref:System.Threading.EventWaitHandle.Set%2A?displayProperty=nameWithType> imposta lo stato di un evento come segnalato.

Il comportamento di un oggetto <xref:System.Threading.EventWaitHandle> che è stato segnalato dipende dalla modalità di reimpostazione:

- Un oggetto <xref:System.Threading.EventWaitHandle> creato con il flag <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> si reimposta automaticamente dopo il rilascio di un singolo thread in attesa. Può essere paragonato a un tornello che lascia passare un solo thread ogni volta che viene segnalato. La classe <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>, che deriva da <xref:System.Threading.EventWaitHandle>, rappresenta questo comportamento.
- Un oggetto <xref:System.Threading.EventWaitHandle> creato con il flag <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> rimane segnalato fino a quando non viene chiamato il relativo metodo <xref:System.Threading.EventWaitHandle.Reset%2A>. Può essere paragonato a un cancello che rimane chiuso fino a quando non viene segnalato e quindi rimane aperto fino a quando non viene chiuso. La classe <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>, che deriva da <xref:System.Threading.EventWaitHandle>, rappresenta questo comportamento. La classe <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> è un'alternativa leggera a <xref:System.Threading.ManualResetEvent>.

In Windows è possibile usare <xref:System.Threading.EventWaitHandle> per la sincronizzazione interprocesso. A tale scopo, creare un'istanza di <xref:System.Threading.EventWaitHandle> che rappresenta un evento di sincronizzazione di sistema denominato usando uno dei [costruttori di EventWaitHandle](<xref:System.Threading.EventWaitHandle.%23ctor%2A>) che specifica un nome o il metodo <xref:System.Threading.EventWaitHandle.OpenExisting%2A?displayProperty=nameWithType>.

Per altre informazioni, vedere l'articolo [EventWaitHandle](eventwaithandle.md). Per informazioni di riferimento sulle API, vedere <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.AutoResetEvent>, <xref:System.Threading.ManualResetEvent> e <xref:System.Threading.ManualResetEventSlim>.

### <a name="countdownevent-class"></a>Classe CountdownEvent

La classe <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> rappresenta un evento che viene impostato quando il relativo conteggio è zero. Quando <xref:System.Threading.CountdownEvent.CurrentCount?displayProperty=nameWithType> è maggiore di zero, un thread che chiama <xref:System.Threading.CountdownEvent.Wait%2A?displayProperty=nameWithType> viene bloccato. Chiamare <xref:System.Threading.CountdownEvent.Signal%2A?displayProperty=nameWithType> per ridurre il conteggio di un evento.

A differenza di <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim>, che è possibile usare per sbloccare più thread con un segnale da un thread, è possibile usare <xref:System.Threading.CountdownEvent> per sbloccare uno o più thread con segnali da più thread.

Per altre informazioni, vedere l'articolo [CountdownEvent](countdownevent.md) e le informazioni di riferimento sull'API <xref:System.Threading.CountdownEvent>.

### <a name="barrier-class"></a>Classe Barrier

La classe <xref:System.Threading.Barrier?displayProperty=nameWithType> rappresenta una barriera di esecuzione di thread. Un thread che chiama il metodo <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> segnala di aver raggiunto la barriera e attende fino a quando gli altri thread partecipanti non raggiungono la barriera. Quando tutti i thread partecipanti raggiungono la barriera, procedono e la barriera viene reimpostata e può essere usata di nuovo.

È possibile usare <xref:System.Threading.Barrier> quando uno o più thread richiedono i risultati di altri thread prima di continuare con la fase di calcolo successiva.

Per altre informazioni, vedere l'articolo [Barrier](barrier.md) e le informazioni di riferimento sull'API <xref:System.Threading.Barrier>.

## <a name="interlocked-class"></a>Interlocked (classe)

La classe <xref:System.Threading.Interlocked?displayProperty=nameWithType> fornisce metodi statici che eseguono operazioni atomiche semplici su una variabile. Queste operazioni atomiche includono addizione, incremento e decremento, scambio e scambio condizionale in base a un confronto, oltre che l'operazione di lettura di un valore intero a 64 bit.

Per altre informazioni, vedere le informazioni di riferimento sull'API <xref:System.Threading.Interlocked>.

## <a name="spinwait-structure"></a>Struttura SpinWait

La struttura <xref:System.Threading.SpinWait?displayProperty=nameWithType> fornisce supporto per l'attesa basata su rotazione. È possibile usare questa struttura quando un thread deve attendere che un evento venga segnalato o una condizione soddisfatta, ma quando si prevede che il tempo di attesa effettivo sia inferiore a quello richiesto usando un handle di attesa o bloccando in altro modo il thread corrente. Usando <xref:System.Threading.SpinWait>, è possibile specificare un breve intervallo di tempo di rotazione durante l'attesa e quindi produrre un risultato (ad esempio, mediante l'attesa o la sospensione) solo se la condizione non viene soddisfatta nel tempo specificato.

Per altre informazioni, vedere l'articolo [SpinWait](spinwait.md) e le informazioni di riferimento sull'API <xref:System.Threading.SpinWait>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Raccolte thread-safe](../collections/thread-safe/index.md)
- [Oggetti e funzionalità del threading](threading-objects-and-features.md)
