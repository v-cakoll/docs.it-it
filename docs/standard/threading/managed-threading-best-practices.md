---
title: Suggerimenti per l'utilizzo del threading gestito
ms.date: 10/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threading [.NET Framework], design guidelines
- threading [.NET Framework], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
ms.openlocfilehash: a76cc40f308ac2f636a650cd4a17da0e94e23a34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160261"
---
# <a name="managed-threading-best-practices"></a>Suggerimenti per l'uso del threading gestito
Il multithreading richiede un'attenta programmazione. È possibile ridurre la complessità della maggior parte delle attività accodando le richieste di esecuzione tramite thread di pool di thread. In questo argomento vengono analizzate situazioni più complesse, come il coordinamento del lavoro di più thread o la gestione di thread che effettuano un blocco.  
  
> [!NOTE]
> A partire da .NET Framework 4, la libreria TPL (Task Parallel Library) e PLINQ specificano API che riducono, in parte, la complessità e i rischi associati alla programmazione multithread. Per altre informazioni, vedere [Programmazione parallela in .NET](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="deadlocks-and-race-conditions"></a>Deadlock e race condition  
 Il multithreading consente di risolvere problemi di trasmissione dei dati e velocità di risposta, ma è anche causa di nuovi problemi: i deadlock e le race condition.  
  
### <a name="deadlocks"></a>Deadlock  
 Un deadlock si verifica quando uno di due thread tenta di bloccare una risorsa già bloccata dall'altro. Nessuno dei due è in grado di fare ulteriori progressi.  
  
 È possibile rilevare i deadlock tramite i timeout disponibili in molti metodi delle classi di threading gestito. Il codice riportato di seguito, ad esempio, prova ad acquisire un blocco su un oggetto denominato `lockObject`. Se il blocco non viene ottenuto in 300 millisecondi, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> restituisce `false`.  
  
```vb  
If Monitor.TryEnter(lockObject, 300) Then  
    Try  
        ' Place code protected by the Monitor here.  
    Finally  
        Monitor.Exit(lockObject)  
    End Try  
Else  
    ' Code to execute if the attempt times out.  
End If  
```  
  
```csharp  
if (Monitor.TryEnter(lockObject, 300)) {  
    try {  
        // Place code protected by the Monitor here.  
    }  
    finally {  
        Monitor.Exit(lockObject);  
    }  
}  
else {  
    // Code to execute if the attempt times out.  
}  
```  
  
### <a name="race-conditions"></a>Race condition  
 Una race condition è un bug che si verifica quando il risultato di un programma dipende da quale tra due o più thread raggiunge per primo un determinato blocco di codice. L'esecuzione ripetuta del programma produce ogni volta risultati diversi che non è possibile prevedere in anticipo.  
  
 Un semplice esempio di race condition è l'incremento di un campo. Si supponga che una classe possieda un campo **statico** (**Shared** in Visual Basic) che viene incrementato ogni volta che viene creata un'istanza della classe tramite codice come `objCt++;` (C#) o `objCt += 1` (Visual Basic). Per eseguire questa operazione, è necessario caricare il valore da `objCt` in un registro, incrementare il valore e archiviarlo in `objCt`.  
  
 In un'applicazione multithreading, un thread che abbia caricato e incrementato il valore potrebbe venire interrotto da un altro thread che esegue tutti e tre i passaggi. Quando il primo thread riprende l'esecuzione e archivia il valore, sovrascrive `objCt` anche se nel frattempo il valore è stato modificato.  
  
 Questa particolare race condition è facilmente evitabile usando i metodi della classe <xref:System.Threading.Interlocked>, ad esempio <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>. Per informazioni sulle altre tecniche di sincronizzazione dei dati tra più thread, vedere [Sincronizzazione dei dati per il multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).  
  
 Le race condition possono verificarsi anche quando si sincronizzano le attività di più thread. Quando si scrive una riga di codice, è necessario considerare le possibili conseguenze nel caso in cui un thread venisse interrotto prima dell'esecuzione della riga o di una qualsiasi delle singole istruzioni del computer che costituiscono la riga e un altro thread lo raggiungesse.  
  
## <a name="static-members-and-static-constructors"></a>Membri e costruttori statici  
 Una classe non viene inizializzata finché non termina l'esecuzione del relativo costruttore (costruttore `static` in C#, `Shared Sub New` in Visual Basic). Per impedire l'esecuzione di codice su un tipo non inizializzato, Common Language Runtime blocca tutte le chiamate degli altri thread ai membri `static` della classe (membri `Shared` in Visual Basic) fino al termine dell'esecuzione del costruttore.  
  
 Se ad esempio il costruttore di una classe avvia un nuovo thread e la routine del thread chiama un membro `static` della classe, il nuovo thread si bloccherà fino al completamento dell'esecuzione del costruttore.  
  
 Ciò è valido per qualsiasi tipo che può avere un costruttore `static`.  

## <a name="number-of-processors"></a>Numero di processori

L'architettura multithreading può essere influenzata dal fatto che nel sistema siano presenti più processori o ve ne sia solo uno. Per altre informazioni, vedere [Numero di processori](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/1c9txz50(v%3dvs.71)#number-of-processors).

Usare la proprietà <xref:System.Environment.ProcessorCount?displayProperty=nameWithType> per determinare il numero di processori disponibili in fase di esecuzione.
  
## <a name="general-recommendations"></a>Raccomandazioni generali  
 Quando si usano più thread, attenersi alle seguenti linee guida:  
  
- Non usare <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> per terminare altri thread. Chiamare **Abort** su un altro thread equivale a generare un'eccezione su tale thread, senza conoscere il punto raggiunto dal thread nell'elaborazione.  
  
- Non usare <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> e <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> per sincronizzare le attività di più thread. Usare <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> e <xref:System.Threading.Monitor>.  
  
- Non controllare l'esecuzione dei thread in funzione dal programma principale, ad esempio tramite gli eventi. Progettare invece il programma in modo che i thread in funzione siano responsabili di attendere finché il lavoro non è disponibile, eseguirlo e informare gli altri componenti del programma del termine dell'esecuzione. Se i thread di lavoro non consentono il blocco, prendere in considerazione l'uso di thread del pool di thread. <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> è utile nelle situazioni in cui i thread di lavoro si bloccano.  
  
- Non usare tipi come oggetti di blocco. Ciò significa evitare codice come `lock(typeof(X))` in C# o `SyncLock(GetType(X))` in Visual Basic oppure l'uso di <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> con oggetti <xref:System.Type>. Per un determinato tipo, è disponibile una sola istanza di <xref:System.Type?displayProperty=nameWithType> per ogni dominio dell'applicazione. Se il tipo per cui si acquisisce un blocco è pubblico, anche codice diverso dal proprio può acquisire blocchi su di esso, con il conseguente verificarsi di deadlock. Per informazioni su altre problematiche, vedere [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md) (Procedure consigliate per l'ottimizzazione dell'affidabilità).  
  
- Procedere con cautela in caso di blocco sulle istanze, ad esempio `lock(this)` in C# o `SyncLock(Me)` in Visual Basic. Se altro codice dell'applicazione, esterno al tipo, acquisisce un blocco sull'oggetto, potrebbero verificarsi situazioni di deadlock.  
  
- Assicurarsi che un thread entrato in un monitor lasci sempre il monitor, anche se si verifica un'eccezione mentre il thread si trova nel monitor. L'istruzione [lock](../../csharp/language-reference/keywords/lock-statement.md) di C# e l'istruzione [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) di Visual Basic generano automaticamente questo comportamento, impiegando un blocco **finally** per garantire che venga chiamato <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>. Se non è possibile garantire che **Exit** verrà chiamato, modificare la progettazione in modo da usare **Mutex**. Un mutex viene rilasciato automaticamente quando il thread che ne è attualmente proprietario termina.  
  
- Usare più thread per le attività che richiedono risorse diverse ed evitare di assegnare più thread a una sola risorsa. Alcune attività, ad esempio, che hanno un proprio thread, usufruiscono dei vantaggi di I/O, poiché il thread si bloccherà durante le operazioni di I/O consentendo l'esecuzione di altri thread. Anche l'input utente è una risorsa che trae vantaggio da un thread dedicato. In un computer a processore unico, un'attività che comporta un calcolo a elevato utilizzo di risorse coesiste con l'input utente e con attività che coinvolgono I/O, ma più attività con un elevato utilizzo di risorse competono fra loro.  
  
- Si prenda in considerazione l'uso dei metodi della classe <xref:System.Threading.Interlocked> per le modifiche semplici allo stato, invece dell'uso dell'istruzione `lock` (`SyncLock` in Visual Basic). L'istruzione `lock` è un valido strumento generico, ma la classe <xref:System.Threading.Interlocked> offre prestazioni migliori per gli aggiornamenti che devono essere atomici. Internamente esegue un unico prefisso lock se non esistono conflitti. Nelle analisi di codice controllare il codice simile a quello indicato negli esempi riportati di seguito. Nel primo esempio viene incrementata una variabile di stato:  
  
    ```vb  
    SyncLock lockObject  
        myField += 1  
    End SyncLock  
    ```  
  
    ```csharp  
    lock(lockObject)
    {  
        myField++;  
    }  
    ```  
  
     Per migliorare le prestazioni, è possibile usare il metodo <xref:System.Threading.Interlocked.Increment%2A> invece dell'istruzione `lock`, come illustrato di seguito:  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    > In .NET Framework 2.0 e versioni successive usare il metodo <xref:System.Threading.Interlocked.Add%2A> per incrementi atomici maggiori di 1.  
  
     Nel secondo esempio una variabile del tipo di riferimento viene aggiornata solo se corrisponde a un riferimento Null (`Nothing` in Visual Basic).  
  
    ```vb  
    If x Is Nothing Then  
        SyncLock lockObject  
            If x Is Nothing Then  
                x = y  
            End If  
        End SyncLock  
    End If  
    ```  
  
    ```csharp  
    if (x == null)  
    {  
        lock (lockObject)  
        {  
            x ??= y;
        }  
    }  
    ```  
  
     Per migliorare le prestazioni, è invece possibile usare il metodo <xref:System.Threading.Interlocked.CompareExchange%2A>, come indicato di seguito:  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    > A partire da .NET Framework 2.0, l'overload del metodo <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> offre un'alternativa indipendente dai tipi per i tipo di riferimento.
  
## <a name="recommendations-for-class-libraries"></a>Suggerimenti per le librerie di classi  
 Si prendano in considerazione le linee guida riportate di seguito per la progettazione di librerie di classi per il multithreading:  
  
- Se possibile, evitare che sia necessario eseguire la sincronizzazione. Ciò è valido soprattutto nel caso di codice di uso più frequente. È ad esempio possibile modificare un algoritmo per tollerare una race condition piuttosto che per eliminarla. L'esecuzione di operazioni di sincronizzazione non necessarie riduce le prestazioni e crea la possibilità di deadlock e race condition.  
  
- Rendere i dati statici (`Shared` in Visual Basic) thread-safe per impostazione predefinita.  
  
- Non rendere i dati di istanza thread-safe per impostazione predefinita. Se si aggiungono blocchi per creare codice thread-safe le prestazioni vengono ridotte, aumentano i conflitti di blocco ed è possibile che si verifichino deadlock. Nei modelli applicativi comuni, solo un thread per volta esegue il codice utente riducendo la necessità di thread safety. Per questo motivo le librerie di classi di .NET Framework non sono thread-safe per impostazione predefinita.  
  
- Evitare di specificare metodi statici che modificano lo stato statico. Negli scenari server comuni, lo stato statico viene condiviso tra le richieste e, pertanto, più thread possono eseguire contemporaneamente tale codice. In questo modo è possibile che si verifichino bug dei thread. È consigliabile provare a usare un modello di progettazione che incapsula i dati nelle istanze che non sono condivise tra le richieste. Se si sincronizzano i dati statici, inoltre, le chiamate tra i metodi statici che modificano lo stato possono determinare deadlock o sincronizzazione ridondante e influire negativamente sulle prestazioni.  
  
## <a name="see-also"></a>Vedere anche

- [Threading](../../../docs/standard/threading/index.md)
- [Thread e threading](../../../docs/standard/threading/threads-and-threading.md)
