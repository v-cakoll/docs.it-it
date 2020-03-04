---
title: Eliminazione definitiva di thread
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
ms.openlocfilehash: 842ca4ff17f9cbab3a1518d2dea37436c9b23f9d
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155932"
---
# <a name="destroying-threads"></a><span data-ttu-id="de02f-102">Eliminazione definitiva di thread</span><span class="sxs-lookup"><span data-stu-id="de02f-102">Destroying threads</span></span>

<span data-ttu-id="de02f-103">Per terminare l'esecuzione del thread, in genere si usa il [modello di annullamento cooperativo](cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="de02f-103">To terminate the execution of the thread, you usually use the [cooperative cancellation model](cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="de02f-104">In alcuni casi non è possibile arrestare un thread in modo cooperativo, perché esegue codice di terze parti non progettato per l'annullamento cooperativo.</span><span class="sxs-lookup"><span data-stu-id="de02f-104">Sometimes it is not possible to stop a thread cooperatively, because it runs third-party code not designed for cooperative cancellation.</span></span> <span data-ttu-id="de02f-105">Il metodo <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> in .NET Framework può essere usato per terminare forzatamente un thread gestito.</span><span class="sxs-lookup"><span data-stu-id="de02f-105">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method in .NET Framework can be used to terminate a managed thread forcibly.</span></span> <span data-ttu-id="de02f-106">Quando si chiama <xref:System.Threading.Thread.Abort%2A>, Common Language Runtime genera una <xref:System.Threading.ThreadAbortException> nel thread di destinazione, che può essere intercettata dal thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="de02f-106">When you call <xref:System.Threading.Thread.Abort%2A>, the Common Language Runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="de02f-107">Per altre informazioni, vedere <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de02f-107">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="de02f-108">Il metodo <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> non è supportato in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="de02f-108">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method is not supported in .NET Core.</span></span> <span data-ttu-id="de02f-109">Se è necessario terminare l'esecuzione di codice di terze parti forzatamente in .NET Core, eseguirlo nel processo separato e usare <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de02f-109">If you need to terminate the execution of third-party code forcibly in .NET Core, run it in the separate process and use <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>.</span></span>

> [!NOTE]
> <span data-ttu-id="de02f-110">Se un thread esegue codice non gestito quando viene chiamato il metodo <xref:System.Threading.Thread.Abort%2A>, il runtime lo contrassegna come <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de02f-110">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="de02f-111">L'eccezione viene generata quando il thread torna al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="de02f-111">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="de02f-112">Quando un thread viene interrotto, non può essere riavviato.</span><span class="sxs-lookup"><span data-stu-id="de02f-112">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="de02f-113">Il metodo <xref:System.Threading.Thread.Abort%2A> non determina l'interruzione immediata del thread perché il thread di destinazione può rilevare <xref:System.Threading.ThreadAbortException> ed eseguire quantità arbitrarie di codice in un blocco `finally`.</span><span class="sxs-lookup"><span data-stu-id="de02f-113">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="de02f-114">È possibile chiamare <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> se è necessario attendere il completamento del thread.</span><span class="sxs-lookup"><span data-stu-id="de02f-114">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="de02f-115"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> è una chiamata di blocco che non termina finché il thread non ha effettivamente arrestato l'esecuzione o è trascorso un intervallo di timeout facoltativo.</span><span class="sxs-lookup"><span data-stu-id="de02f-115"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="de02f-116">Il thread interrotto può chiamare il metodo <xref:System.Threading.Thread.ResetAbort%2A> o eseguire un'elaborazione senza vincoli in un blocco `finally`, quindi, se non si specifica un timeout, non è sicuro che l'attesa termini.</span><span class="sxs-lookup"><span data-stu-id="de02f-116">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="de02f-117">I thread in attesa di una chiamata al metodo <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> possono essere interrotti da altri thread che chiamano <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de02f-117">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="de02f-118">Gestione di ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="de02f-118">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="de02f-119">Se si prevede che il thread venga interrotto, in seguito alla chiamata ad <xref:System.Threading.Thread.Abort%2A> dal codice o in seguito allo scaricamento di un dominio applicazione in cui il thread è in esecuzione (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> usa <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> per terminare i thread), il thread deve gestire <xref:System.Threading.ThreadAbortException> ed eseguire un'eventuale elaborazione finale in una clausola `finally`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="de02f-119">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="de02f-120">Il codice di pulizia deve essere nella clausola `catch` o nella clausola `finally`, perché un'eccezione <xref:System.Threading.ThreadAbortException> viene nuovamente generata dal sistema alla fine della clausola `finally` o alla fine della clausola `catch` se non sono presenti clausole `finally`.</span><span class="sxs-lookup"><span data-stu-id="de02f-120">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="de02f-121">È possibile impedire che il sistema generi nuovamente l'eccezione chiamando il metodo <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de02f-121">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="de02f-122">È tuttavia consigliabile farlo solo se il codice ha generato <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="de02f-122">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de02f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de02f-123">See also</span></span>

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="de02f-124">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="de02f-124">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
