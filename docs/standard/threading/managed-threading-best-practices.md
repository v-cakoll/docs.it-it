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
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160261"
---
# <a name="managed-threading-best-practices"></a><span data-ttu-id="4bcbb-102">Suggerimenti per l'uso del threading gestito</span><span class="sxs-lookup"><span data-stu-id="4bcbb-102">Managed threading best practices</span></span>
<span data-ttu-id="4bcbb-103">Il multithreading richiede un'attenta programmazione.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-103">Multithreading requires careful programming.</span></span> <span data-ttu-id="4bcbb-104">È possibile ridurre la complessità della maggior parte delle attività accodando le richieste di esecuzione tramite thread di pool di thread.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-104">For most tasks, you can reduce complexity by queuing requests for execution by thread pool threads.</span></span> <span data-ttu-id="4bcbb-105">In questo argomento vengono analizzate situazioni più complesse, come il coordinamento del lavoro di più thread o la gestione di thread che effettuano un blocco.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-105">This topic addresses more difficult situations, such as coordinating the work of multiple threads, or handling threads that block.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4bcbb-106">A partire da .NET Framework 4, la libreria TPL (Task Parallel Library) e PLINQ specificano API che riducono, in parte, la complessità e i rischi associati alla programmazione multithread.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-106">Starting with the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs that reduce some of the complexity and risks of multi-threaded programming.</span></span> <span data-ttu-id="4bcbb-107">Per altre informazioni, vedere [Programmazione parallela in .NET](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="4bcbb-107">For more information, see [Parallel Programming in .NET](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="deadlocks-and-race-conditions"></a><span data-ttu-id="4bcbb-108">Deadlock e race condition</span><span class="sxs-lookup"><span data-stu-id="4bcbb-108">Deadlocks and race conditions</span></span>  
 <span data-ttu-id="4bcbb-109">Il multithreading consente di risolvere problemi di trasmissione dei dati e velocità di risposta, ma è anche causa di nuovi problemi: i deadlock e le race condition.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-109">Multithreading solves problems with throughput and responsiveness, but in doing so it introduces new problems: deadlocks and race conditions.</span></span>  
  
### <a name="deadlocks"></a><span data-ttu-id="4bcbb-110">Deadlock</span><span class="sxs-lookup"><span data-stu-id="4bcbb-110">Deadlocks</span></span>  
 <span data-ttu-id="4bcbb-111">Un deadlock si verifica quando uno di due thread tenta di bloccare una risorsa già bloccata dall'altro.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-111">A deadlock occurs when each of two threads tries to lock a resource the other has already locked.</span></span> <span data-ttu-id="4bcbb-112">Nessuno dei due è in grado di fare ulteriori progressi.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-112">Neither thread can make any further progress.</span></span>  
  
 <span data-ttu-id="4bcbb-113">È possibile rilevare i deadlock tramite i timeout disponibili in molti metodi delle classi di threading gestito.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-113">Many methods of the managed threading classes provide time-outs to help you detect deadlocks.</span></span> <span data-ttu-id="4bcbb-114">Il codice riportato di seguito, ad esempio, prova ad acquisire un blocco su un oggetto denominato `lockObject`.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-114">For example, the following code attempts to acquire a lock on an object named `lockObject`.</span></span> <span data-ttu-id="4bcbb-115">Se il blocco non viene ottenuto in 300 millisecondi, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-115">If the lock is not obtained in 300 milliseconds, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> returns `false`.</span></span>  
  
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
  
### <a name="race-conditions"></a><span data-ttu-id="4bcbb-116">Race condition</span><span class="sxs-lookup"><span data-stu-id="4bcbb-116">Race conditions</span></span>  
 <span data-ttu-id="4bcbb-117">Una race condition è un bug che si verifica quando il risultato di un programma dipende da quale tra due o più thread raggiunge per primo un determinato blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-117">A race condition is a bug that occurs when the outcome of a program depends on which of two or more threads reaches a particular block of code first.</span></span> <span data-ttu-id="4bcbb-118">L'esecuzione ripetuta del programma produce ogni volta risultati diversi che non è possibile prevedere in anticipo.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-118">Running the program many times produces different results, and the result of any given run cannot be predicted.</span></span>  
  
 <span data-ttu-id="4bcbb-119">Un semplice esempio di race condition è l'incremento di un campo.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-119">A simple example of a race condition is incrementing a field.</span></span> <span data-ttu-id="4bcbb-120">Si supponga che una classe possieda un campo **statico** (**Shared** in Visual Basic) che viene incrementato ogni volta che viene creata un'istanza della classe tramite codice come `objCt++;` (C#) o `objCt += 1` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4bcbb-120">Suppose a class has a private **static** field (**Shared** in Visual Basic) that is incremented every time an instance of the class is created, using code such as `objCt++;` (C#) or `objCt += 1` (Visual Basic).</span></span> <span data-ttu-id="4bcbb-121">Per eseguire questa operazione, è necessario caricare il valore da `objCt` in un registro, incrementare il valore e archiviarlo in `objCt`.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-121">This operation requires loading the value from `objCt` into a register, incrementing the value, and storing it in `objCt`.</span></span>  
  
 <span data-ttu-id="4bcbb-122">In un'applicazione multithreading, un thread che abbia caricato e incrementato il valore potrebbe venire interrotto da un altro thread che esegue tutti e tre i passaggi. Quando il primo thread riprende l'esecuzione e archivia il valore, sovrascrive `objCt` anche se nel frattempo il valore è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-122">In a multithreaded application, a thread that has loaded and incremented the value might be preempted by another thread which performs all three steps; when the first thread resumes execution and stores its value, it overwrites `objCt` without taking into account the fact that the value has changed in the interim.</span></span>  
  
 <span data-ttu-id="4bcbb-123">Questa particolare race condition è facilmente evitabile usando i metodi della classe <xref:System.Threading.Interlocked>, ad esempio <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-123">This particular race condition is easily avoided by using methods of the <xref:System.Threading.Interlocked> class, such as <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4bcbb-124">Per informazioni sulle altre tecniche di sincronizzazione dei dati tra più thread, vedere [Sincronizzazione dei dati per il multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).</span><span class="sxs-lookup"><span data-stu-id="4bcbb-124">To read about other techniques for synchronizing data among multiple threads, see [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).</span></span>  
  
 <span data-ttu-id="4bcbb-125">Le race condition possono verificarsi anche quando si sincronizzano le attività di più thread.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-125">Race conditions can also occur when you synchronize the activities of multiple threads.</span></span> <span data-ttu-id="4bcbb-126">Quando si scrive una riga di codice, è necessario considerare le possibili conseguenze nel caso in cui un thread venisse interrotto prima dell'esecuzione della riga o di una qualsiasi delle singole istruzioni del computer che costituiscono la riga e un altro thread lo raggiungesse.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-126">Whenever you write a line of code, you must consider what might happen if a thread were preempted before executing the line (or before any of the individual machine instructions that make up the line), and another thread overtook it.</span></span>  
  
## <a name="static-members-and-static-constructors"></a><span data-ttu-id="4bcbb-127">Membri e costruttori statici</span><span class="sxs-lookup"><span data-stu-id="4bcbb-127">Static members and static constructors</span></span>  
 <span data-ttu-id="4bcbb-128">Una classe non viene inizializzata finché non termina l'esecuzione del relativo costruttore (costruttore `static` in C#, `Shared Sub New` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4bcbb-128">A class is not initialized until its class constructor (`static` constructor in C#, `Shared Sub New` in Visual Basic) has finished running.</span></span> <span data-ttu-id="4bcbb-129">Per impedire l'esecuzione di codice su un tipo non inizializzato, Common Language Runtime blocca tutte le chiamate degli altri thread ai membri `static` della classe (membri `Shared` in Visual Basic) fino al termine dell'esecuzione del costruttore.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-129">To prevent the execution of code on a type that is not initialized, the common language runtime blocks all calls from other threads to `static` members of the class (`Shared` members in Visual Basic) until the class constructor has finished running.</span></span>  
  
 <span data-ttu-id="4bcbb-130">Se ad esempio il costruttore di una classe avvia un nuovo thread e la routine del thread chiama un membro `static` della classe, il nuovo thread si bloccherà fino al completamento dell'esecuzione del costruttore.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-130">For example, if a class constructor starts a new thread, and the thread procedure calls a `static` member of the class, the new thread blocks until the class constructor completes.</span></span>  
  
 <span data-ttu-id="4bcbb-131">Ciò è valido per qualsiasi tipo che può avere un costruttore `static`.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-131">This applies to any type that can have a `static` constructor.</span></span>  

## <a name="number-of-processors"></a><span data-ttu-id="4bcbb-132">Numero di processori</span><span class="sxs-lookup"><span data-stu-id="4bcbb-132">Number of processors</span></span>

<span data-ttu-id="4bcbb-133">L'architettura multithreading può essere influenzata dal fatto che nel sistema siano presenti più processori o ve ne sia solo uno.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-133">Whether there are multiple processors or only one processor available on a system can influence multithreaded architecture.</span></span> <span data-ttu-id="4bcbb-134">Per altre informazioni, vedere [Numero di processori](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/1c9txz50(v%3dvs.71)#number-of-processors).</span><span class="sxs-lookup"><span data-stu-id="4bcbb-134">For more information, see [Number of Processors](https://docs.microsoft.com/previous-versions/dotnet/netframework-1.1/1c9txz50(v%3dvs.71)#number-of-processors).</span></span>

<span data-ttu-id="4bcbb-135">Usare la proprietà <xref:System.Environment.ProcessorCount?displayProperty=nameWithType> per determinare il numero di processori disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-135">Use the <xref:System.Environment.ProcessorCount?displayProperty=nameWithType> property to determine the number of processors available at runtime.</span></span>
  
## <a name="general-recommendations"></a><span data-ttu-id="4bcbb-136">Raccomandazioni generali</span><span class="sxs-lookup"><span data-stu-id="4bcbb-136">General recommendations</span></span>  
 <span data-ttu-id="4bcbb-137">Quando si usano più thread, attenersi alle seguenti linee guida:</span><span class="sxs-lookup"><span data-stu-id="4bcbb-137">Consider the following guidelines when using multiple threads:</span></span>  
  
- <span data-ttu-id="4bcbb-138">Non usare <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> per terminare altri thread.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-138">Don't use <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate other threads.</span></span> <span data-ttu-id="4bcbb-139">Chiamare **Abort** su un altro thread equivale a generare un'eccezione su tale thread, senza conoscere il punto raggiunto dal thread nell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-139">Calling **Abort** on another thread is akin to throwing an exception on that thread, without knowing what point that thread has reached in its processing.</span></span>  
  
- <span data-ttu-id="4bcbb-140">Non usare <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> e <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> per sincronizzare le attività di più thread.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-140">Don't use <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> to synchronize the activities of multiple threads.</span></span> <span data-ttu-id="4bcbb-141">Usare <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> e <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-141">Do use <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.Monitor>.</span></span>  
  
- <span data-ttu-id="4bcbb-142">Non controllare l'esecuzione dei thread in funzione dal programma principale, ad esempio tramite gli eventi.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-142">Don't control the execution of worker threads from your main program (using events, for example).</span></span> <span data-ttu-id="4bcbb-143">Progettare invece il programma in modo che i thread in funzione siano responsabili di attendere finché il lavoro non è disponibile, eseguirlo e informare gli altri componenti del programma del termine dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-143">Instead, design your program so that worker threads are responsible for waiting until work is available, executing it, and notifying other parts of your program when finished.</span></span> <span data-ttu-id="4bcbb-144">Se i thread di lavoro non consentono il blocco, prendere in considerazione l'uso di thread del pool di thread.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-144">If your worker threads do not block, consider using thread pool threads.</span></span> <span data-ttu-id="4bcbb-145"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> è utile nelle situazioni in cui i thread di lavoro si bloccano.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-145"><xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> is useful in situations where worker threads block.</span></span>  
  
- <span data-ttu-id="4bcbb-146">Non usare tipi come oggetti di blocco.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-146">Don't use types as lock objects.</span></span> <span data-ttu-id="4bcbb-147">Ciò significa evitare codice come `lock(typeof(X))` in C# o `SyncLock(GetType(X))` in Visual Basic oppure l'uso di <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> con oggetti <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-147">That is, avoid code such as `lock(typeof(X))` in C# or `SyncLock(GetType(X))` in Visual Basic, or the use of <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> with <xref:System.Type> objects.</span></span> <span data-ttu-id="4bcbb-148">Per un determinato tipo, è disponibile una sola istanza di <xref:System.Type?displayProperty=nameWithType> per ogni dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-148">For a given type, there is only one instance of <xref:System.Type?displayProperty=nameWithType> per application domain.</span></span> <span data-ttu-id="4bcbb-149">Se il tipo per cui si acquisisce un blocco è pubblico, anche codice diverso dal proprio può acquisire blocchi su di esso, con il conseguente verificarsi di deadlock.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-149">If the type you take a lock on is public, code other than your own can take locks on it, leading to deadlocks.</span></span> <span data-ttu-id="4bcbb-150">Per informazioni su altre problematiche, vedere [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md) (Procedure consigliate per l'ottimizzazione dell'affidabilità).</span><span class="sxs-lookup"><span data-stu-id="4bcbb-150">For additional issues, see [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md).</span></span>  
  
- <span data-ttu-id="4bcbb-151">Procedere con cautela in caso di blocco sulle istanze, ad esempio `lock(this)` in C# o `SyncLock(Me)` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-151">Use caution when locking on instances, for example `lock(this)` in C# or `SyncLock(Me)` in Visual Basic.</span></span> <span data-ttu-id="4bcbb-152">Se altro codice dell'applicazione, esterno al tipo, acquisisce un blocco sull'oggetto, potrebbero verificarsi situazioni di deadlock.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-152">If other code in your application, external to the type, takes a lock on the object, deadlocks could occur.</span></span>  
  
- <span data-ttu-id="4bcbb-153">Assicurarsi che un thread entrato in un monitor lasci sempre il monitor, anche se si verifica un'eccezione mentre il thread si trova nel monitor.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-153">Do ensure that a thread that has entered a monitor always leaves that monitor, even if an exception occurs while the thread is in the monitor.</span></span> <span data-ttu-id="4bcbb-154">L'istruzione [lock](../../csharp/language-reference/keywords/lock-statement.md) di C# e l'istruzione [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) di Visual Basic generano automaticamente questo comportamento, impiegando un blocco **finally** per garantire che venga chiamato <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-154">The C# [lock](../../csharp/language-reference/keywords/lock-statement.md) statement and the Visual Basic [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) statement provide this behavior automatically, employing a **finally** block to ensure that <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> is called.</span></span> <span data-ttu-id="4bcbb-155">Se non è possibile garantire che **Exit** verrà chiamato, modificare la progettazione in modo da usare **Mutex**.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-155">If you cannot ensure that **Exit** will be called, consider changing your design to use **Mutex**.</span></span> <span data-ttu-id="4bcbb-156">Un mutex viene rilasciato automaticamente quando il thread che ne è attualmente proprietario termina.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-156">A mutex is automatically released when the thread that currently owns it terminates.</span></span>  
  
- <span data-ttu-id="4bcbb-157">Usare più thread per le attività che richiedono risorse diverse ed evitare di assegnare più thread a una sola risorsa.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-157">Do use multiple threads for tasks that require different resources, and avoid assigning multiple threads to a single resource.</span></span> <span data-ttu-id="4bcbb-158">Alcune attività, ad esempio, che hanno un proprio thread, usufruiscono dei vantaggi di I/O, poiché il thread si bloccherà durante le operazioni di I/O consentendo l'esecuzione di altri thread.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-158">For example, any task involving I/O benefits from having its own thread, because that thread will block during I/O operations and thus allow other threads to execute.</span></span> <span data-ttu-id="4bcbb-159">Anche l'input utente è una risorsa che trae vantaggio da un thread dedicato.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-159">User input is another resource that benefits from a dedicated thread.</span></span> <span data-ttu-id="4bcbb-160">In un computer a processore unico, un'attività che comporta un calcolo a elevato utilizzo di risorse coesiste con l'input utente e con attività che coinvolgono I/O, ma più attività con un elevato utilizzo di risorse competono fra loro.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-160">On a single-processor computer, a task that involves intensive computation coexists with user input and with tasks that involve I/O, but multiple computation-intensive tasks contend with each other.</span></span>  
  
- <span data-ttu-id="4bcbb-161">Si prenda in considerazione l'uso dei metodi della classe <xref:System.Threading.Interlocked> per le modifiche semplici allo stato, invece dell'uso dell'istruzione `lock` (`SyncLock` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4bcbb-161">Consider using methods of the <xref:System.Threading.Interlocked> class for simple state changes, instead of using the `lock` statement (`SyncLock` in Visual Basic).</span></span> <span data-ttu-id="4bcbb-162">L'istruzione `lock` è un valido strumento generico, ma la classe <xref:System.Threading.Interlocked> offre prestazioni migliori per gli aggiornamenti che devono essere atomici.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-162">The `lock` statement is a good general-purpose tool, but the <xref:System.Threading.Interlocked> class provides better performance for updates that must be atomic.</span></span> <span data-ttu-id="4bcbb-163">Internamente esegue un unico prefisso lock se non esistono conflitti.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-163">Internally, it executes a single lock prefix if there is no contention.</span></span> <span data-ttu-id="4bcbb-164">Nelle analisi di codice controllare il codice simile a quello indicato negli esempi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-164">In code reviews, watch for code like that shown in the following examples.</span></span> <span data-ttu-id="4bcbb-165">Nel primo esempio viene incrementata una variabile di stato:</span><span class="sxs-lookup"><span data-stu-id="4bcbb-165">In the first example, a state variable is incremented:</span></span>  
  
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
  
     <span data-ttu-id="4bcbb-166">Per migliorare le prestazioni, è possibile usare il metodo <xref:System.Threading.Interlocked.Increment%2A> invece dell'istruzione `lock`, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4bcbb-166">You can improve performance by using the <xref:System.Threading.Interlocked.Increment%2A> method instead of the `lock` statement, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="4bcbb-167">In .NET Framework 2.0 e versioni successive usare il metodo <xref:System.Threading.Interlocked.Add%2A> per incrementi atomici maggiori di 1.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-167">In the .NET Framework 2.0 and later, use the <xref:System.Threading.Interlocked.Add%2A> method for atomic increments larger than 1.</span></span>  
  
     <span data-ttu-id="4bcbb-168">Nel secondo esempio una variabile del tipo di riferimento viene aggiornata solo se corrisponde a un riferimento Null (`Nothing` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="4bcbb-168">In the second example, a reference type variable is updated only if it is a null reference (`Nothing` in Visual Basic).</span></span>  
  
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
  
     <span data-ttu-id="4bcbb-169">Per migliorare le prestazioni, è invece possibile usare il metodo <xref:System.Threading.Interlocked.CompareExchange%2A>, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4bcbb-169">Performance can be improved by using the <xref:System.Threading.Interlocked.CompareExchange%2A> method instead, as follows:</span></span>  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="4bcbb-170">A partire da .NET Framework 2.0, l'overload del metodo <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> offre un'alternativa indipendente dai tipi per i tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-170">Beginning with .NET Framework 2.0, the <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> method overload provides a type-safe alternative for reference types.</span></span>
  
## <a name="recommendations-for-class-libraries"></a><span data-ttu-id="4bcbb-171">Suggerimenti per le librerie di classi</span><span class="sxs-lookup"><span data-stu-id="4bcbb-171">Recommendations for class libraries</span></span>  
 <span data-ttu-id="4bcbb-172">Si prendano in considerazione le linee guida riportate di seguito per la progettazione di librerie di classi per il multithreading:</span><span class="sxs-lookup"><span data-stu-id="4bcbb-172">Consider the following guidelines when designing class libraries for multithreading:</span></span>  
  
- <span data-ttu-id="4bcbb-173">Se possibile, evitare che sia necessario eseguire la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-173">Avoid the need for synchronization, if possible.</span></span> <span data-ttu-id="4bcbb-174">Ciò è valido soprattutto nel caso di codice di uso più frequente.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-174">This is especially true for heavily used code.</span></span> <span data-ttu-id="4bcbb-175">È ad esempio possibile modificare un algoritmo per tollerare una race condition piuttosto che per eliminarla.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-175">For example, an algorithm might be adjusted to tolerate a race condition rather than eliminate it.</span></span> <span data-ttu-id="4bcbb-176">L'esecuzione di operazioni di sincronizzazione non necessarie riduce le prestazioni e crea la possibilità di deadlock e race condition.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-176">Unnecessary synchronization decreases performance and creates the possibility of deadlocks and race conditions.</span></span>  
  
- <span data-ttu-id="4bcbb-177">Rendere i dati statici (`Shared` in Visual Basic) thread-safe per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-177">Make static data (`Shared` in Visual Basic) thread safe by default.</span></span>  
  
- <span data-ttu-id="4bcbb-178">Non rendere i dati di istanza thread-safe per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-178">Do not make instance data thread safe by default.</span></span> <span data-ttu-id="4bcbb-179">Se si aggiungono blocchi per creare codice thread-safe le prestazioni vengono ridotte, aumentano i conflitti di blocco ed è possibile che si verifichino deadlock.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-179">Adding locks to create thread-safe code decreases performance, increases lock contention, and creates the possibility for deadlocks to occur.</span></span> <span data-ttu-id="4bcbb-180">Nei modelli applicativi comuni, solo un thread per volta esegue il codice utente riducendo la necessità di thread safety.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-180">In common application models, only one thread at a time executes user code, which minimizes the need for thread safety.</span></span> <span data-ttu-id="4bcbb-181">Per questo motivo le librerie di classi di .NET Framework non sono thread-safe per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-181">For this reason, the .NET Framework class libraries are not thread safe by default.</span></span>  
  
- <span data-ttu-id="4bcbb-182">Evitare di specificare metodi statici che modificano lo stato statico.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-182">Avoid providing static methods that alter static state.</span></span> <span data-ttu-id="4bcbb-183">Negli scenari server comuni, lo stato statico viene condiviso tra le richieste e, pertanto, più thread possono eseguire contemporaneamente tale codice.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-183">In common server scenarios, static state is shared across requests, which means multiple threads can execute that code at the same time.</span></span> <span data-ttu-id="4bcbb-184">In questo modo è possibile che si verifichino bug dei thread.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-184">This opens up the possibility of threading bugs.</span></span> <span data-ttu-id="4bcbb-185">È consigliabile provare a usare un modello di progettazione che incapsula i dati nelle istanze che non sono condivise tra le richieste.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-185">Consider using a design pattern that encapsulates data into instances that are not shared across requests.</span></span> <span data-ttu-id="4bcbb-186">Se si sincronizzano i dati statici, inoltre, le chiamate tra i metodi statici che modificano lo stato possono determinare deadlock o sincronizzazione ridondante e influire negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-186">Furthermore, if static data are synchronized, calls between static methods that alter state can result in deadlocks or redundant synchronization, adversely affecting performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bcbb-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bcbb-187">See also</span></span>

- [<span data-ttu-id="4bcbb-188">Threading</span><span class="sxs-lookup"><span data-stu-id="4bcbb-188">Threading</span></span>](../../../docs/standard/threading/index.md)
- <span data-ttu-id="4bcbb-189">[Threads and Threading](../../../docs/standard/threading/threads-and-threading.md) (Thread e threading)</span><span class="sxs-lookup"><span data-stu-id="4bcbb-189">[Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)</span></span>
