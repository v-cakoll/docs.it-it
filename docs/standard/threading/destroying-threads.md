---
title: Eliminazione definitiva di thread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a><span data-ttu-id="aaf5c-102">Eliminazione definitiva di thread</span><span class="sxs-lookup"><span data-stu-id="aaf5c-102">Destroying Threads</span></span>
<span data-ttu-id="aaf5c-103">Il <xref:System.Threading.Thread.Abort%2A> metodo viene utilizzato per interrompere un thread gestito in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-103">The <xref:System.Threading.Thread.Abort%2A> method is used to stop a managed thread permanently.</span></span> <span data-ttu-id="aaf5c-104">Quando si chiama <xref:System.Threading.Thread.Abort%2A>, common language runtime genera un <xref:System.Threading.ThreadAbortException> nel thread di destinazione, in grado di rilevare il thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-104">When you call <xref:System.Threading.Thread.Abort%2A>, the common language runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="aaf5c-105">Per altre informazioni, vedere <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-105">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aaf5c-106">Se è in esecuzione un thread non gestito il codice quando il relativo <xref:System.Threading.Thread.Abort%2A> metodo viene chiamato, il runtime contrassegna <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-106">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="aaf5c-107">L'eccezione viene generata quando il thread viene restituito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-107">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="aaf5c-108">Quando un thread viene interrotto, non può essere riavviato.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-108">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="aaf5c-109">Il <xref:System.Threading.Thread.Abort%2A> metodo non determina l'interruzione immediata, il thread perché il thread di destinazione può intercettare il <xref:System.Threading.ThreadAbortException> ed eseguire quantità arbitraria di codice in un `finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-109">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="aaf5c-110">È possibile chiamare <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> se è necessario attendere che il thread è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-110">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="aaf5c-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>è una chiamata di blocco non termina finché il thread effettivamente ha interrotto l'esecuzione o è trascorso un intervallo di timeout facoltativo.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="aaf5c-112">Il thread interrotto può chiamare il <xref:System.Threading.Thread.ResetAbort%2A> metodo o eseguire un'elaborazione illimitata in una `finally` blocca, pertanto se non si specifica un timeout, il tempo di attesa non è garantita per terminare.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-112">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="aaf5c-113">Thread in attesa su una chiamata al <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> metodo può essere interrotta da altri thread che chiamano <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-113">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="aaf5c-114">Gestione di ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="aaf5c-114">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="aaf5c-115">Se si prevede che il thread viene interrotta, come risultato della chiamata <xref:System.Threading.Thread.Abort%2A> dal proprio codice o in seguito a un dominio applicazione in cui viene eseguito il thread di scaricamento (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> utilizza <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> per interrompere i thread), il thread deve gestire il <xref:System.Threading.ThreadAbortException> ed eseguire un'eventuale elaborazione finale in un `finally` clausola, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-115">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="aaf5c-116">Il codice di pulizia deve essere nel `catch` clausola o `finally` clausola, perché un <xref:System.Threading.ThreadAbortException> viene nuovamente generata dal sistema alla fine del `finally` clausola, o alla fine del `catch` clausola se è presente alcun `finally` clausola.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-116">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="aaf5c-117">È possibile impedire che il sistema rigenerare l'eccezione chiamando il <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-117">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="aaf5c-118">Tuttavia, deve farlo solo se il proprio codice che ha causato il <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="aaf5c-118">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf5c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaf5c-119">See Also</span></span>  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="aaf5c-120">Utilizzo di thread e threading</span><span class="sxs-lookup"><span data-stu-id="aaf5c-120">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
