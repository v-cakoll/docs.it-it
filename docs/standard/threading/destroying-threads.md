---
title: Eliminazione definitiva di thread
description: È possibile verificare le opzioni quando è necessario eliminare un thread in .NET, ad esempio l'annullamento cooperativo o il metodo thread. Abort. Informazioni su come gestire l'eccezione ThreadAbortException.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
ms.openlocfilehash: baf9289413de0e99533f121eb2a404ff0d873511
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768508"
---
# <a name="destroying-threads"></a><span data-ttu-id="27d81-104">Eliminazione definitiva di thread</span><span class="sxs-lookup"><span data-stu-id="27d81-104">Destroying threads</span></span>

<span data-ttu-id="27d81-105">Per terminare l'esecuzione del thread, in genere si usa il [modello di annullamento cooperativo](cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="27d81-105">To terminate the execution of the thread, you usually use the [cooperative cancellation model](cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="27d81-106">In alcuni casi non è possibile arrestare un thread in modo cooperativo, perché esegue codice di terze parti non progettato per l'annullamento cooperativo.</span><span class="sxs-lookup"><span data-stu-id="27d81-106">Sometimes it is not possible to stop a thread cooperatively, because it runs third-party code not designed for cooperative cancellation.</span></span> <span data-ttu-id="27d81-107">Il <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> metodo in .NET Framework può essere utilizzato per terminare forzatamente un thread gestito.</span><span class="sxs-lookup"><span data-stu-id="27d81-107">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method in .NET Framework can be used to terminate a managed thread forcibly.</span></span> <span data-ttu-id="27d81-108">Quando si chiama <xref:System.Threading.Thread.Abort%2A> , Common Language Runtime genera un'eccezione <xref:System.Threading.ThreadAbortException> nel thread di destinazione, che può essere intercettato dal thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="27d81-108">When you call <xref:System.Threading.Thread.Abort%2A>, the Common Language Runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="27d81-109">Per altre informazioni, vedere <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27d81-109">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="27d81-110">Il <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> metodo non è supportato in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="27d81-110">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method is not supported in .NET Core.</span></span> <span data-ttu-id="27d81-111">Se è necessario terminare l'esecuzione di codice di terze parti forzatamente in .NET Core, eseguirlo nel processo separato e usare <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="27d81-111">If you need to terminate the execution of third-party code forcibly in .NET Core, run it in the separate process and use <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>.</span></span>

> [!NOTE]
> <span data-ttu-id="27d81-112">Se un thread esegue codice non gestito quando viene chiamato il metodo <xref:System.Threading.Thread.Abort%2A>, il runtime lo contrassegna come <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27d81-112">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="27d81-113">L'eccezione viene generata quando il thread torna al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="27d81-113">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="27d81-114">Quando un thread viene interrotto, non può essere riavviato.</span><span class="sxs-lookup"><span data-stu-id="27d81-114">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="27d81-115">Il metodo <xref:System.Threading.Thread.Abort%2A> non determina l'interruzione immediata del thread perché il thread di destinazione può rilevare <xref:System.Threading.ThreadAbortException> ed eseguire quantità arbitrarie di codice in un blocco `finally`.</span><span class="sxs-lookup"><span data-stu-id="27d81-115">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="27d81-116">È possibile chiamare <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> se è necessario attendere il completamento del thread.</span><span class="sxs-lookup"><span data-stu-id="27d81-116">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="27d81-117"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> è una chiamata di blocco che non termina finché il thread non ha effettivamente arrestato l'esecuzione o è trascorso un intervallo di timeout facoltativo.</span><span class="sxs-lookup"><span data-stu-id="27d81-117"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="27d81-118">Il thread interrotto può chiamare il metodo <xref:System.Threading.Thread.ResetAbort%2A> o eseguire un'elaborazione senza vincoli in un blocco `finally`, quindi, se non si specifica un timeout, non è sicuro che l'attesa termini.</span><span class="sxs-lookup"><span data-stu-id="27d81-118">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="27d81-119">I thread in attesa di una chiamata al metodo <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> possono essere interrotti da altri thread che chiamano <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27d81-119">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="27d81-120">Gestione di ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="27d81-120">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="27d81-121">Se si prevede che il thread venga interrotto, in seguito alla chiamata ad <xref:System.Threading.Thread.Abort%2A> dal codice o in seguito allo scaricamento di un dominio applicazione in cui il thread è in esecuzione (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> usa <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> per terminare i thread), il thread deve gestire <xref:System.Threading.ThreadAbortException> ed eseguire un'eventuale elaborazione finale in una clausola `finally`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="27d81-121">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try
{  
    // Code that is executing when the thread is aborted.  
}
catch (ThreadAbortException ex)
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.
}  
// Do not put clean-up code here, because the exception
// is rethrown at the end of the Finally clause.  
```  
  
 <span data-ttu-id="27d81-122">Il codice di pulizia deve essere nella clausola `catch` o nella clausola `finally`, perché un'eccezione <xref:System.Threading.ThreadAbortException> viene nuovamente generata dal sistema alla fine della clausola `finally` o alla fine della clausola `catch` se non sono presenti clausole `finally`.</span><span class="sxs-lookup"><span data-stu-id="27d81-122">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="27d81-123">È possibile impedire che il sistema generi nuovamente l'eccezione chiamando il metodo <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27d81-123">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="27d81-124">È tuttavia consigliabile farlo solo se il codice ha generato <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="27d81-124">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d81-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27d81-125">See also</span></span>

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="27d81-126">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="27d81-126">Using Threads and Threading</span></span>](using-threads-and-threading.md)
