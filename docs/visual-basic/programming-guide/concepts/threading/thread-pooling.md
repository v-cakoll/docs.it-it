---
title: (Visual Basic) di Pooling dei thread
ms.date: 07/20/2015
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
ms.openlocfilehash: 445c1c70cc1371ef918f32046e0c30ae2a473da2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647833"
---
# <a name="thread-pooling-visual-basic"></a><span data-ttu-id="d71b7-102">(Visual Basic) di Pooling dei thread</span><span class="sxs-lookup"><span data-stu-id="d71b7-102">Thread Pooling (Visual Basic)</span></span>
<span data-ttu-id="d71b7-103">Un *pool di thread* è una Collection di thread che è possibile usare per eseguire diverse attività in background.</span><span class="sxs-lookup"><span data-stu-id="d71b7-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="d71b7-104">(Vedere [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) per informazioni generali.) In questo modo il thread primario è libero di eseguire altre attività in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="d71b7-104">(See [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="d71b7-105">I pool di thread vengono spesso usati nelle applicazioni server.</span><span class="sxs-lookup"><span data-stu-id="d71b7-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="d71b7-106">Ad ogni richiesta in arrivo viene assegnato un thread del pool. In questo modo la richiesta può essere elaborata in modo asincrono, senza bloccare il thread primario o ritardare l'elaborazione delle richieste successive.</span><span class="sxs-lookup"><span data-stu-id="d71b7-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="d71b7-107">Una volta completata l'attività, il thread del pool torna in una coda di thread in attesa, dove potrà essere riusato</span><span class="sxs-lookup"><span data-stu-id="d71b7-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="d71b7-108">evitando in questo modo la necessità di creare un nuovo thread per ogni attività.</span><span class="sxs-lookup"><span data-stu-id="d71b7-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="d71b7-109">Esiste in genere un numero massimo di thread che è possibile inserire in un pool.</span><span class="sxs-lookup"><span data-stu-id="d71b7-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="d71b7-110">Se tutti i thread sono occupati, le altre attività vengono inserite in coda finché non potranno essere eseguite dai thread che si renderanno disponibili.</span><span class="sxs-lookup"><span data-stu-id="d71b7-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="d71b7-111">È possibile implementare un pool di thread personalizzato, ma risulta più agevole usare quello fornito con .NET Framework tramite la classe <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="d71b7-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="d71b7-112">Pool di thread, si chiama il <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> metodo con un delegato per la procedura da eseguire e Visual Basic viene creato il thread e viene eseguita la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d71b7-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method with a delegate for the procedure you want to run, and Visual Basic creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="d71b7-113">Esempio di limitazione delle richieste di thread</span><span class="sxs-lookup"><span data-stu-id="d71b7-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="d71b7-114">Nell'esempio seguente viene illustrato come usare la limitazione delle richieste di thread per avviare svariate attività.</span><span class="sxs-lookup"><span data-stu-id="d71b7-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 <span data-ttu-id="d71b7-115">Uno dei vantaggi offerti dalla limitazione di richieste di thread consiste nella possibilità di passare argomenti in un oggetto di stato alla routine di attività.</span><span class="sxs-lookup"><span data-stu-id="d71b7-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="d71b7-116">Se per la routine chiamata è necessario più di un argomento, è possibile eseguire il cast di una struttura o un'istanza di una classe in un tipo di dati `Object`.</span><span class="sxs-lookup"><span data-stu-id="d71b7-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="d71b7-117">Parametri e valori restituiti del pool di thread</span><span class="sxs-lookup"><span data-stu-id="d71b7-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="d71b7-118">La restituzione di valori da un thread del pool di thread non risulta semplicissima.</span><span class="sxs-lookup"><span data-stu-id="d71b7-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="d71b7-119">Non è possibile avvalersi della soluzione standard per la restituzione di valori da una chiamata di funzione, poiché in un pool di thread possono essere accodate solo le routine `Sub`.</span><span class="sxs-lookup"><span data-stu-id="d71b7-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="d71b7-120">Un modo per specificare i parametri e restituire valori è incapsulando i parametri, valori restituiti, e i metodi in un classe wrapper come descritto in [parametri e valori restituiti per routine multithreading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d71b7-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="d71b7-121">La variabile facoltativa dell'oggetto di stato `ByVal` del metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> offre un metodo più semplice per fornire i parametri e restituire valori.</span><span class="sxs-lookup"><span data-stu-id="d71b7-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="d71b7-122">Se si usa tale variabile per passare un riferimento a un'istanza di una classe, i membri dell'istanza potranno essere modificati dal thread del pool di thread e usati come valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="d71b7-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="d71b7-123">Inizialmente potrebbe non essere evidente che è possibile modificare un oggetto a cui fa riferimento una variabile che viene passata per valore.</span><span class="sxs-lookup"><span data-stu-id="d71b7-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="d71b7-124">Questa operazione può essere eseguita perché solo il riferimento oggetto viene inviato dal valore.</span><span class="sxs-lookup"><span data-stu-id="d71b7-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="d71b7-125">Quando si apportano modifiche ai membri dell'oggetto indicato dal riferimento all'oggetto, le modifiche vengono applicate all'istanza di classe effettiva.</span><span class="sxs-lookup"><span data-stu-id="d71b7-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="d71b7-126">Non è possibile usare le strutture per restituire valori all'interno di oggetti di stato.</span><span class="sxs-lookup"><span data-stu-id="d71b7-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="d71b7-127">Poiché le strutture sono tipi valore, le modifiche apportate dal processo asincrono non comportano la modifica dei membri della struttura originale.</span><span class="sxs-lookup"><span data-stu-id="d71b7-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="d71b7-128">Utilizzare le strutture per fornire parametri nei casi in cui non sono necessari i valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="d71b7-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d71b7-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d71b7-129">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="d71b7-130">Procedura: Usare un pool di thread (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d71b7-130">How to: Use a Thread Pool (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [<span data-ttu-id="d71b7-131">Threading (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d71b7-131">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="d71b7-132">Applicazioni multithreading (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d71b7-132">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="d71b7-133">Sincronizzazione di thread (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d71b7-133">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
