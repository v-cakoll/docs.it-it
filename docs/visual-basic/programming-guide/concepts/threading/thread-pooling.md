---
title: (Visual Basic) di pooling dei thread | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: eea7c94dffe525bb36c677bf3414f25ed0210074
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="thread-pooling-visual-basic"></a><span data-ttu-id="76847-102">(Visual Basic) di pooling dei thread</span><span class="sxs-lookup"><span data-stu-id="76847-102">Thread Pooling (Visual Basic)</span></span>
<span data-ttu-id="76847-103">Oggetto *pool di thread* è una raccolta di thread che può essere utilizzato per eseguire diverse attività in background.</span><span class="sxs-lookup"><span data-stu-id="76847-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="76847-104">(Vedere [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) per le informazioni.) In questo modo il thread principale può eseguire altre attività in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="76847-104">(See [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="76847-105">Pool di thread vengono spesso utilizzati nelle applicazioni server.</span><span class="sxs-lookup"><span data-stu-id="76847-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="76847-106">Ogni richiesta in ingresso viene assegnato a un thread dal pool di thread, in modo che la richiesta può essere elaborata in modo asincrono, senza bloccare il thread principale o ritardare l'elaborazione delle richieste successive.</span><span class="sxs-lookup"><span data-stu-id="76847-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="76847-107">Una volta un thread nel pool di completamento dell'attività, viene restituito a una coda di thread in attesa, in cui può essere riutilizzato.</span><span class="sxs-lookup"><span data-stu-id="76847-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="76847-108">In questo modo le applicazioni evitare il costo di creazione di un nuovo thread per ogni attività.</span><span class="sxs-lookup"><span data-stu-id="76847-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="76847-109">Pool di thread sono in genere un numero massimo di thread.</span><span class="sxs-lookup"><span data-stu-id="76847-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="76847-110">Se tutti i thread sono occupati, attività aggiuntive vengono inserite nella coda finché non può essere gestite come diventano disponibili thread.</span><span class="sxs-lookup"><span data-stu-id="76847-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="76847-111">È possibile implementare un pool di thread, ma è più semplice utilizzare il pool di thread fornito da .NET Framework tramite la <xref:System.Threading.ThreadPool>classe.</xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="76847-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="76847-112">Pool di thread, si chiama il <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>metodo con un delegato per la procedura da eseguire e Visual Basic viene creato il thread ed eseguita la procedura.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="76847-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName> method with a delegate for the procedure you want to run, and Visual Basic creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="76847-113">Esempio di pooling dei thread</span><span class="sxs-lookup"><span data-stu-id="76847-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="76847-114">Nell'esempio seguente viene illustrato come utilizzare pooling dei thread per avviare diverse attività.</span><span class="sxs-lookup"><span data-stu-id="76847-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
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
  
 <span data-ttu-id="76847-115">Un vantaggio del pool di thread consiste nel fatto che è possibile passare argomenti in un oggetto di stato per la routine dell'attività.</span><span class="sxs-lookup"><span data-stu-id="76847-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="76847-116">Se la procedura che si sta chiamando richiede più di un argomento, è possibile impostare una struttura o un'istanza di una classe in un `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="76847-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="76847-117">Parametri del Pool di thread e i valori restituiti</span><span class="sxs-lookup"><span data-stu-id="76847-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="76847-118">Restituzione di valori da un thread di pool di thread non è semplice.</span><span class="sxs-lookup"><span data-stu-id="76847-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="76847-119">Il metodo standard per la restituzione di valori da una chiamata di funzione non è consentito perché `Sub` procedure sono l'unico tipo di routine che può essere accodate al pool di thread.</span><span class="sxs-lookup"><span data-stu-id="76847-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="76847-120">Un modo per fornire parametri e restituire valori è incapsulando i parametri, i valori restituiti, e i metodi in un classe wrapper come descritto in [parametri e valori restituiti per routine multithreading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="76847-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="76847-121">Un modo di soluzione per fornire parametri e valori restituiti è tramite facoltativo `ByVal` variabile oggetto di stato del <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>(metodo).</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="76847-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="76847-122">Se si utilizza questa variabile per passare un riferimento a un'istanza di una classe, i membri dell'istanza possono essere modificati dal thread del pool di thread e utilizzati come valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="76847-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="76847-123">Inizialmente potrebbe non essere evidente che è possibile modificare un oggetto a cui fa riferimento una variabile che viene passata per valore.</span><span class="sxs-lookup"><span data-stu-id="76847-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="76847-124">È possibile farlo perché solo il riferimento all'oggetto viene passato per valore.</span><span class="sxs-lookup"><span data-stu-id="76847-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="76847-125">Quando si apportano modifiche ai membri dell'oggetto a cui fa riferimento il riferimento all'oggetto, le modifiche applicate all'istanza di classe effettiva.</span><span class="sxs-lookup"><span data-stu-id="76847-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="76847-126">Le strutture non possono essere utilizzate per restituire i valori all'interno di oggetti di stato.</span><span class="sxs-lookup"><span data-stu-id="76847-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="76847-127">Poiché le strutture sono tipi di valore, le modifiche apportate dal processo asincrono non modificano i membri della struttura originale.</span><span class="sxs-lookup"><span data-stu-id="76847-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="76847-128">Utilizzare le strutture per fornire parametri quando non sono necessari i valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="76847-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76847-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76847-129">See Also</span></span>  
 <span data-ttu-id="76847-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="76847-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span></span>   
 <span data-ttu-id="76847-131"><xref:System.Threading></xref:System.Threading></span><span class="sxs-lookup"><span data-stu-id="76847-131"><xref:System.Threading></span></span>   
 <span data-ttu-id="76847-132"><xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="76847-132"><xref:System.Threading.ThreadPool></span></span>   
<span data-ttu-id="76847-133"> [Procedura: utilizzare un Pool di Thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span><span class="sxs-lookup"><span data-stu-id="76847-133"> [How to: Use a Thread Pool (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span></span>  
<span data-ttu-id="76847-134"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="76847-134"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
<span data-ttu-id="76847-135"> [Applicazioni multithreading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="76847-135"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="76847-136"> [Sincronizzazione dei thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="76847-136"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span></span>
