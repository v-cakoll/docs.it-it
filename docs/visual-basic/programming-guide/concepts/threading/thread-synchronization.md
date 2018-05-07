---
title: Sincronizzazione dei thread (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 04f485d1-8333-4510-9e72-c334e7427e7e
ms.openlocfilehash: 9922230e1c7f2bd30c575bd66387feb4850a298b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="thread-synchronization-visual-basic"></a>Sincronizzazione dei thread (Visual Basic)
Le sezioni seguenti descrivono le funzionalità e le classi che possono essere usate per sincronizzare l'accesso alle risorse nelle applicazioni multithreading.  
  
 Uno dei vantaggi dell'uso di più thread in un'applicazione consiste nel fatto che ogni thread viene eseguito in modo asincrono. Per le applicazioni Windows, questo consente l'esecuzione di attività che richiedono molto tempo per essere eseguite in background, mentre la finestra dell'applicazione e i controlli rimangono attivi. Per le applicazioni server, il multithreading offre la capacità di gestire ogni richiesta in ingresso con un thread differente. In caso contrario, ogni nuova richiesta non viene gestita fino a quando la richiesta precedente non è stata completamente soddisfatta.  
  
 Tuttavia, la natura asincrona dei thread implica che l'accesso alle risorse, quali handle di file, connessioni di rete e memoria deve essere coordinato. In caso contrario, due o più thread potrebbero accedere alla stessa risorsa nello stesso momento, inconsapevoli delle azioni dell'altro. Il risultato è un danneggiamento imprevisto dei dati.  
  
 Per operazioni semplici sui tipi di dati numerici integrali, la sincronizzazione dei thread può essere eseguita con i membri della classe <xref:System.Threading.Interlocked>. Per tutti gli altri tipi di dati e risorse non thread-safe, il multithreading può essere eseguito in modo sicuro solo usando i costrutti forniti in questo argomento.  
  
 Per informazioni di base sulla programmazione multithreading, vedere:  
  
-   [Nozioni di base sul threading gestito](../../../../standard/threading/managed-threading-basics.md)  
  
-   [Utilizzo di thread e threading](../../../../standard/threading/using-threads-and-threading.md)  
  
-   [Suggerimenti per l'utilizzo del threading gestito](../../../../standard/threading/managed-threading-best-practices.md)  
  
## <a name="the-lock-and-synclock-keywords"></a>Il blocco e parole chiave SyncLock  
 Visual Basic `SyncLock` istruzione può essere utilizzata per garantire l'esecuzione di un blocco di codice fino al completamento senza interruzioni da altri thread. Questa operazione viene portata a termine ottenendo un blocco a esclusione reciproca per un determinato oggetto per la durata del blocco del codice.  
  
 Un'istruzione `SyncLock` viene assegnata a un oggetto come argomento, seguita da un blocco di codice che deve essere eseguito da un solo thread alla volta. Ad esempio:  
  
```vb  
Public Class TestThreading  
    Dim lockThis As New Object  
  
    Public Sub Process()  
        SyncLock lockThis  
            ' Access thread-sensitive resources.  
        End SyncLock  
    End Sub  
End Class  
```  
  
 L'argomento fornito per la parola chiave `SyncLock` deve essere un oggetto basato su un tipo di riferimento e viene usato per definire l'ambito del blocco. Nell'esempio precedente, l'ambito del blocco è limitato a questa funzione perché non esiste alcun riferimento all'oggetto `lockThis` all'esterno della funzione. Se esiste un riferimento, l'ambito del blocco si estende anche a tale oggetto. In pratica, l'oggetto fornito viene usato esclusivamente per identificare la risorsa condivisa tra più thread, che pertanto può essere un'istanza di classe arbitraria. Tuttavia, questo oggetto rappresenta in genere la risorsa per cui si rende necessaria la sincronizzazione del thread. Ad esempio, se un oggetto contenitore deve essere usato da più thread, può essere passato al blocco e il blocco di codice sincronizzato che segue il blocco accede al contenitore. Se altri thread vengano bloccati nello stesso contenitore prima dell'accesso, l'accesso all'oggetto è sincronizzato in modo sicuro.  
  
 In genere, è consigliabile evitare il blocco di un tipo`public` o di istanze di oggetti sotto il controllo dell'applicazione. Ad esempio, `lockThis` può risultare problematico se l'istanza è accessibile pubblicamente, perché il codice non controllato potrebbe causare anche il blocco dell'oggetto. Questo fattore può creare situazioni di deadlock in cui due o più thread rimangono in attesa della versione dello stesso oggetto. Per lo stesso motivo, il blocco di un tipo di dati pubblici, invece di un oggetto, può causare problemi. Il blocco di stringhe letterali è particolarmente rischioso poiché le stringhe letterali sono *inserite* da Common Language Runtime (CLR). Ciò significa che è presente un'istanza di un dato valore letterale di stringa per l'intero programma e che lo stesso oggetto rappresenta il valore letterale in tutti i domini dell'applicazione in esecuzione su tutti i thread. Di conseguenza, un blocco collocato su una stringa con lo stesso contenuto in qualsiasi posizione del processo dell'applicazione blocca tutte le istanze di tale stringa nell'applicazione. Si consiglia quindi di bloccare un membro privato o protetto non inserito. Alcune classi forniscono membri specifici per il blocco. Il tipo <xref:System.Array>, ad esempio, fornisce <xref:System.Array.SyncRoot%2A>. Anche molti tipi di raccolta forniscono un membro `SyncRoot`.  
  
 Per altre informazioni sull'istruzione `SyncLock`, vedere i seguenti argomenti:  
  
-   [Istruzione SyncLock](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
  
-   <xref:System.Threading.Monitor>  
  
## <a name="monitors"></a>Monitoraggi  
 Come la parola chiave `SyncLock`, i monitoraggi impediscono che il codice si blocchi durante l'esecuzione simultanea di più thread. Il metodo <xref:System.Threading.Monitor.Enter%2A> consente a un solo thread di procedere nelle istruzioni seguenti; tutti gli altri thread sono bloccati fino a quando il thread in esecuzione esegue una chiamata a <xref:System.Threading.Monitor.Exit%2A>. Questa operazione equivale all'uso della parola chiave `SyncLock`. Ad esempio:  
  
```vb  
SyncLock x  
    DoSomething()  
End SyncLock  
```  
  
 Equivale a:  
  
```vb  
Dim obj As Object = CType(x, Object)  
System.Threading.Monitor.Enter(obj)  
Try  
    DoSomething()  
Finally  
    System.Threading.Monitor.Exit(obj)  
End Try  
```  
  
 L'uso della parola chiave `SyncLock` viene generalmente preferito all'uso diretto della classe <xref:System.Threading.Monitor>, sia perché `SyncLock` è più concisa, sia perché `SyncLock` garantisce che il monitoraggio sottostante venga rilasciato, anche se il codice protetto genera un'eccezione. Questa operazione viene eseguita con la parola chiave `Finally` che esegue il blocco di codice associato indipendentemente dal fatto che venga generata un'eccezione.  
  
## <a name="synchronization-events-and-wait-handles"></a>Eventi di sincronizzazione ed handle di attesa  
 L'uso di un blocco o di un monitoraggio è utile per impedire l'esecuzione simultanea di blocchi di codice sensibili ai thread, ma questi costrutti non consentono a un solo thread di comunicare un evento a un altro. Questa operazione richiede *eventi di sincronizzazione*, che sono oggetti che presentano uno dei due stati, segnalato e non segnalato, utile per attivare e sospendere i thread. I thread possono essere sospesi mettendoli in attesa di un evento di sincronizzazione non segnalato e attivati impostando lo stato dell'evento su segnalato. Se un thread tenta di attendere un evento già segnalato, il thread continua l'esecuzione senza ritardo.  
  
 Esistono due tipi di eventi di sincronizzazione: <xref:System.Threading.AutoResetEvent> e <xref:System.Threading.ManualResetEvent>. L'unica differenza consiste nel fatto che <xref:System.Threading.AutoResetEvent> passa automaticamente dallo stato segnalato allo stato non segnalato ogni volta che attiva un thread. Viceversa <xref:System.Threading.ManualResetEvent> consente l'attivazione di un numero qualsiasi di thread con lo stato segnalato e torna allo stato non segnalato solo quando viene chiamato il suo metodo <xref:System.Threading.EventWaitHandle.Reset%2A>.  
  
 I thread possono attendere gli eventi mediante la chiamata a uno dei metodi di attesa disponibili, ad esempio <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> o <xref:System.Threading.WaitHandle.WaitAll%2A>. <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType> lascia il thread in attesa finché un singolo evento non diventa segnalato, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> blocca un thread finché uno o più degli eventi indicati non diventano segnalati e <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> blocca il thread finché tutti gli eventi indicati non diventano segnalati. L'evento diventa segnalato quando viene chiamato il relativo metodo <xref:System.Threading.EventWaitHandle.Set%2A>.  
  
 Nell'esempio seguente viene creato un thread e avviato dalla funzione `Main`. Il nuovo thread attende un evento usando il metodo <xref:System.Threading.WaitHandle.WaitOne%2A>. Il thread viene sospeso fino a quando l'evento viene segnalato dal thread principale che esegue la funzione `Main`. Una volta che viene segnalato l'evento, viene restituito il thread ausiliario. In questo caso, poiché l'evento viene usato solo per l'attivazione di un thread, è possibile usare la classe <xref:System.Threading.AutoResetEvent> o <xref:System.Threading.ManualResetEvent>.  
  
```vb  
Imports System.Threading  
  
Module Module1  
    Dim autoEvent As AutoResetEvent  
  
    Sub DoWork()  
        Console.WriteLine("   worker thread started, now waiting on event...")  
        autoEvent.WaitOne()  
        Console.WriteLine("   worker thread reactivated, now exiting...")  
    End Sub  
  
    Sub Main()  
        autoEvent = New AutoResetEvent(False)  
  
        Console.WriteLine("main thread starting worker thread...")  
        Dim t As New Thread(AddressOf DoWork)  
        t.Start()  
  
        Console.WriteLine("main thread sleeping for 1 second...")  
        Thread.Sleep(1000)  
  
        Console.WriteLine("main thread signaling worker thread...")  
        autoEvent.Set()  
    End Sub  
End Module  
```  
  
## <a name="mutex-object"></a>Oggetto mutex  
 Un *mutex* è simile a un monitoraggio: impedisce l'esecuzione simultanea di un blocco di codice da più thread contemporaneamente. Infatti, il nome "mutex" vuol dire "reciproca esclusione". A differenza dei monitoraggi, tuttavia, un mutex consente di sincronizzare i thread tra i processi. Un mutex è rappresentato dalla classe <xref:System.Threading.Mutex>.  
  
 Quando usato per la sincronizzazione tra processi, il mutex viene definito *mutex con nome*  perché deve essere impiegato in un'altra applicazione e pertanto non può essere condiviso tramite una variabile globale o statica. Per consentire a entrambe le applicazioni di accedere allo stesso oggetto mutex, è necessario assegnargli un nome.  
  
 Anche se è possibile usare un mutex per la sincronizzazione dei thread tra processi, è in genere preferibile usare <xref:System.Threading.Monitor>, perché i monitor sono stati concepiti appositamente per .NET Framework e pertanto usano le risorse in modo più efficace. Viceversa la classe <xref:System.Threading.Mutex> è un wrapper per un costrutto Win32. Sebbene sia più potente di un monitor, un mutex richiede transizioni di interoperabilità più dispendiose in termini di calcolo rispetto a quelle richieste dalla classe <xref:System.Threading.Monitor>. Per un esempio di uso di un mutex, vedere [Mutex](../../../../standard/threading/mutexes.md).  
  
## <a name="interlocked-class"></a>Classe Interlocked  
 È possibile usare metodi della classe <xref:System.Threading.Interlocked> per prevenire i problemi che si verificano quando più thread tentano di aggiornare o confrontare contemporaneamente lo stesso valore. I metodi di questa classe consentono di incrementare, ridurre, scambiare e confrontare in modo sicuro i valori provenienti da qualsiasi thread.  
  
## <a name="readerwriter-locks"></a>Blocchi ReaderWriter  
 In alcuni casi, si desidera bloccare una risorsa solo durante la scrittura di dati e consentire a più client di leggere simultaneamente i dati quando non si trovano in fase di aggiornamento. La classe <xref:System.Threading.ReaderWriterLock> impone l'accesso esclusivo a una risorsa mentre un thread la sta modificando, ma consente accesso non esclusivo durante la lettura della risorsa stessa. I blocchi ReaderWriter rappresentano un'alternativa utile ai blocchi esclusivi, che causano l'attesa di altri thread, anche quando i thread non hanno bisogno di aggiornare i dati.  
  
## <a name="deadlocks"></a>Deadlock  
 La sincronizzazione dei thread si rivela particolarmente utile nelle applicazioni multithreading, ma è sempre presente il pericolo di creazione di un `deadlock`, in cui più thread si attendono tra loro e l'applicazione si blocca. Un deadlock è analogo a una situazione in cui le automobili si fermano su un incrocio a quattro vie e ognuna attende che passi l'altra. Evitare i deadlock è importante. La chiave è un'attenta pianificazione. È spesso possibile prevedere situazioni di deadlock creando diagrammi delle applicazioni multithreading prima di iniziare la codifica.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.WaitHandle.WaitOne%2A>  
 <xref:System.Threading.WaitHandle.WaitAny%2A>  
 <xref:System.Threading.WaitHandle.WaitAll%2A>  
 <xref:System.Threading.Thread.Join%2A>  
 <xref:System.Threading.Thread.Start%2A>  
 <xref:System.Threading.Thread.Sleep%2A>  
 <xref:System.Threading.Monitor>  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading>  
 <xref:System.Threading.EventWaitHandle.Set%2A>  
 <xref:System.Threading.Monitor>  
 [Applicazioni multithreading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Istruzione SyncLock](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
 [Mutex](../../../../standard/threading/mutexes.md)  
 [Operazioni interlocked](../../../../standard/threading/interlocked-operations.md)  
 [AutoResetEvent](../../../../standard/threading/autoresetevent.md)  
 [Sincronizzazione dei dati per il multithreading](../../../../standard/threading/synchronizing-data-for-multithreading.md)
