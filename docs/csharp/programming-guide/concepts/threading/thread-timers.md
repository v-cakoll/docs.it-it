---
title: Timer di thread (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 52ed71e8-4fd9-43a4-ae40-04cce7cff23f
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9702360408340b28fcdcc8f197467a002f77ee51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="thread-timers-c"></a><span data-ttu-id="b844a-102">Timer di thread (C#)</span><span class="sxs-lookup"><span data-stu-id="b844a-102">Thread Timers (C#)</span></span>
<span data-ttu-id="b844a-103">La classe <xref:System.Threading.Timer?displayProperty=nameWithType> è utile per l'esecuzione periodica di un'attività in un thread distinto.</span><span class="sxs-lookup"><span data-stu-id="b844a-103">The <xref:System.Threading.Timer?displayProperty=nameWithType> class is useful for periodically running a task on a separate thread.</span></span> <span data-ttu-id="b844a-104">Ad esempio, è possibile usare un timer di thread per controllare lo stato e l'integrità di un database o per eseguire il backup dei file critici.</span><span class="sxs-lookup"><span data-stu-id="b844a-104">For example, you could use a thread timer to check the status and integrity of a database or to back up critical files.</span></span>  
  
## <a name="thread-timer-example"></a><span data-ttu-id="b844a-105">Esempio di timer di thread</span><span class="sxs-lookup"><span data-stu-id="b844a-105">Thread Timer Example</span></span>  
 <span data-ttu-id="b844a-106">Nell'esempio seguente viene avviata un'attività ogni due secondi e viene usato un flag per avviare il metodo <xref:System.IDisposable.Dispose%2A> che arresta il timer.</span><span class="sxs-lookup"><span data-stu-id="b844a-106">The following example starts a task every two seconds and uses a flag to initiate the <xref:System.IDisposable.Dispose%2A> method that stops the timer.</span></span> <span data-ttu-id="b844a-107">Lo stato viene inserito nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="b844a-107">This example posts status to the output window.</span></span>  
  
```csharp  
private class StateObjClass  
{  
    // Used to hold parameters for calls to TimerTask.  
    public int SomeValue;  
    public System.Threading.Timer TimerReference;  
    public bool TimerCanceled;  
}  
  
public void RunTimer()  
{  
    StateObjClass StateObj = new StateObjClass();  
    StateObj.TimerCanceled = false;  
    StateObj.SomeValue = 1;  
    System.Threading.TimerCallback TimerDelegate =  
        new System.Threading.TimerCallback(TimerTask);  
  
    // Create a timer that calls a procedure every 2 seconds.  
    // Note: There is no Start method; the timer starts running as soon as   
    // the instance is created.  
    System.Threading.Timer TimerItem =  
        new System.Threading.Timer(TimerDelegate, StateObj, 2000, 2000);  
  
    // Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem;    
  
    // Run for ten loops.  
    while (StateObj.SomeValue < 10)   
    {  
        // Wait one second.  
        System.Threading.Thread.Sleep(1000);    
    }  
  
    // Request Dispose of the timer object.  
    StateObj.TimerCanceled = true;    
}  
  
private void TimerTask(object StateObj)  
{  
    StateObjClass State = (StateObjClass)StateObj;  
    // Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(ref State.SomeValue);  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " + DateTime.Now.ToString());  
    if (State.TimerCanceled)      
    // Dispose Requested.  
    {  
        State.TimerReference.Dispose();  
        System.Diagnostics.Debug.WriteLine("Done  " + DateTime.Now.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="b844a-108">I timer di thread risultano particolarmente utili quando l'oggetto <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> non è disponibile, come nel caso dello sviluppo di applicazioni console.</span><span class="sxs-lookup"><span data-stu-id="b844a-108">Thread timers are particularly useful when the <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> object is unavailable, such as when you are developing console applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b844a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b844a-109">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="b844a-110">Applicazioni multithreading (C#)</span><span class="sxs-lookup"><span data-stu-id="b844a-110">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)
