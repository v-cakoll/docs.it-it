---
title: 'Procedura: Usare un pool di thread (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 210a9235-83a6-420b-af52-2d6a58e5133f
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9ad5ffb224821c67d227297f8a5a4a1476d77b0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-thread-pool-c"></a><span data-ttu-id="1aebd-102">Procedura: Usare un pool di thread (C#)</span><span class="sxs-lookup"><span data-stu-id="1aebd-102">How to: Use a Thread Pool (C#)</span></span>
<span data-ttu-id="1aebd-103">La *creazione di un pool di thread* è una forma di multithreading che prevede l'aggiunta di attività a una coda e l'avvio automatico di tali attività nel corso della creazione dei thread.</span><span class="sxs-lookup"><span data-stu-id="1aebd-103">*Thread pooling* is a form of multithreading in which tasks are added to a queue and automatically started when threads are created.</span></span> <span data-ttu-id="1aebd-104">Per altre informazioni, vedere [Creazione di pool di thread (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="1aebd-104">For more information, see [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md).</span></span>  
  
 <span data-ttu-id="1aebd-105">Nell'esempio seguente viene usato il pool di thread di .NET Framework per calcolare il risultato della sequenza di `Fibonacci` relativa a 10 numeri compresi tra 20 e 40.</span><span class="sxs-lookup"><span data-stu-id="1aebd-105">The following example uses the .NET Framework thread pool to calculate the `Fibonacci` result for ten numbers between 20 and 40.</span></span> <span data-ttu-id="1aebd-106">Ogni risultato di `Fibonacci` viene rappresentato dalla classe `Fibonacci`, che fornisce un metodo denominato `ThreadPoolCallback` per l'esecuzione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="1aebd-106">Each `Fibonacci` result is represented by the `Fibonacci` class, which provides a method named `ThreadPoolCallback` that performs the calculation.</span></span> <span data-ttu-id="1aebd-107">Viene creato un oggetto che rappresenta ogni valore `Fibonacci`, il metodo `ThreadPoolCallback` viene passato a <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, che assegna un thread disponibile del pool per eseguire il metodo.</span><span class="sxs-lookup"><span data-stu-id="1aebd-107">An object that represents each `Fibonacci` value is created, and the `ThreadPoolCallback` method is passed to <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, which assigns an available thread in the pool to execute the method.</span></span>  
  
 <span data-ttu-id="1aebd-108">Poiché a ogni oggetto `Fibonacci` viene assegnato un valore semi-casuale da calcolare e poiché ogni thread è in competizione con gli altri per ottenere il tempo del processore, non è possibile prevedere quanto tempo richiederà il calcolo di tutti e 10 i risultati.</span><span class="sxs-lookup"><span data-stu-id="1aebd-108">Because each `Fibonacci` object is given a semi-random value to compute, and because each thread will be competing for processor time, you cannot know in advance how long it will take for all ten results to be calculated.</span></span> <span data-ttu-id="1aebd-109">Per questo motivo a ogni oggetto `Fibonacci` viene passata un'istanza della classe <xref:System.Threading.ManualResetEvent> durante la costruzione.</span><span class="sxs-lookup"><span data-stu-id="1aebd-109">That is why each `Fibonacci` object is passed an instance of the <xref:System.Threading.ManualResetEvent> class during construction.</span></span> <span data-ttu-id="1aebd-110">Dopo aver completato il calcolo, ogni oggetto segnala l'oggetto evento specificato. In questo modo il thread primario può bloccare l'esecuzione con `Fibonacci` finché tutti e dieci gli oggetti <xref:System.Threading.WaitHandle.WaitAll%2A> non hanno calcolato un risultato.</span><span class="sxs-lookup"><span data-stu-id="1aebd-110">Each object signals the provided event object when its calculation is complete, which allows the primary thread to block execution with <xref:System.Threading.WaitHandle.WaitAll%2A> until all ten `Fibonacci` objects have calculated a result.</span></span> <span data-ttu-id="1aebd-111">Il metodo `Main` visualizza quindi ogni risultato `Fibonacci`.</span><span class="sxs-lookup"><span data-stu-id="1aebd-111">The `Main` method then displays each `Fibonacci` result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1aebd-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="1aebd-112">Example</span></span>  
  
```csharp  
using System;  
using System.Threading;  
  
public class Fibonacci  
{  
    private int _n;  
    private int _fibOfN;  
    private ManualResetEvent _doneEvent;  
  
    public int N { get { return _n; } }  
    public int FibOfN { get { return _fibOfN; } }  
  
    // Constructor.  
    public Fibonacci(int n, ManualResetEvent doneEvent)  
    {  
        _n = n;  
        _doneEvent = doneEvent;  
    }  
  
    // Wrapper method for use with thread pool.  
    public void ThreadPoolCallback(Object threadContext)  
    {  
        int threadIndex = (int)threadContext;  
        Console.WriteLine("thread {0} started...", threadIndex);  
        _fibOfN = Calculate(_n);  
        Console.WriteLine("thread {0} result calculated...", threadIndex);  
        _doneEvent.Set();  
    }  
  
    // Recursive method that calculates the Nth Fibonacci number.  
    public int Calculate(int n)  
    {  
        if (n <= 1)  
        {  
            return n;  
        }  
  
        return Calculate(n - 1) + Calculate(n - 2);  
    }  
}  
  
public class ThreadPoolExample  
{  
    static void Main()  
    {  
        const int FibonacciCalculations = 10;  
  
        // One event is used for each Fibonacci object.  
        ManualResetEvent[] doneEvents = new ManualResetEvent[FibonacciCalculations];  
        Fibonacci[] fibArray = new Fibonacci[FibonacciCalculations];  
        Random r = new Random();  
  
        // Configure and start threads using ThreadPool.  
        Console.WriteLine("launching {0} tasks...", FibonacciCalculations);  
        for (int i = 0; i < FibonacciCalculations; i++)  
        {  
            doneEvents[i] = new ManualResetEvent(false);  
            Fibonacci f = new Fibonacci(r.Next(20, 40), doneEvents[i]);  
            fibArray[i] = f;  
            ThreadPool.QueueUserWorkItem(f.ThreadPoolCallback, i);  
        }  
  
        // Wait for all threads in pool to calculate.  
        WaitHandle.WaitAll(doneEvents);  
        Console.WriteLine("All calculations are complete.");  
  
        // Display the results.  
        for (int i= 0; i<FibonacciCalculations; i++)  
        {  
            Fibonacci f = fibArray[i];  
            Console.WriteLine("Fibonacci({0}) = {1}", f.N, f.FibOfN);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="1aebd-113">Di seguito viene riportato un esempio dell'output.</span><span class="sxs-lookup"><span data-stu-id="1aebd-113">Following is an example of the output.</span></span>  
  
```  
launching 10 tasks...  
thread 0 started...  
thread 1 started...  
thread 1 result calculated...  
thread 2 started...  
thread 2 result calculated...  
thread 3 started...  
thread 3 result calculated...  
thread 4 started...  
thread 0 result calculated...  
thread 5 started...  
thread 5 result calculated...  
thread 6 started...  
thread 4 result calculated...  
thread 7 started...  
thread 6 result calculated...  
thread 8 started...  
thread 8 result calculated...  
thread 9 started...  
thread 9 result calculated...  
thread 7 result calculated...  
All calculations are complete.  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(25) = 75025  
Fibonacci(22) = 17711  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(29) = 514229  
Fibonacci(38) = 39088169  
Fibonacci(21) = 10946  
Fibonacci(27) = 196418  
```  
  
## <a name="see-also"></a><span data-ttu-id="1aebd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aebd-114">See Also</span></span>  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.WaitHandle.WaitAll%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.EventWaitHandle.Set%2A>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="1aebd-115">Creazione di pool di thread (C#)</span><span class="sxs-lookup"><span data-stu-id="1aebd-115">Thread Pooling (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="1aebd-116">Threading (C#)</span><span class="sxs-lookup"><span data-stu-id="1aebd-116">Threading (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="1aebd-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1aebd-117">Security</span></span>](../../../../standard/security/index.md)
