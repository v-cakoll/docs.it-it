---
title: Parametri e valori restituiti per routine multithreading (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ba63c30c-d9f0-4962-b5c7-9d83ba851e6a
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fec0ad955439f0cd683ad56c8d6433eed2417304
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-c"></a><span data-ttu-id="271be-102">Parametri e valori restituiti per routine multithreading (C#)</span><span class="sxs-lookup"><span data-stu-id="271be-102">Parameters and Return Values for Multithreaded Procedures (C#)</span></span>
<span data-ttu-id="271be-103">L'invio e la restituzione di valori in un'applicazione multithreading è un processo complesso poiché è necessario che il costruttore della classe di thread riceva un riferimento a una routine che non accetta alcun argomento e non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="271be-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="271be-104">Le sezioni seguenti descrivono alcuni metodi semplici per l'inserimento di parametri e la restituzione di valori da routine su thread diversi.</span><span class="sxs-lookup"><span data-stu-id="271be-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="271be-105">Inserimento di parametri per routine multithreading</span><span class="sxs-lookup"><span data-stu-id="271be-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="271be-106">Il modo migliore per inserire i parametri per una chiamata di metodo multithreading consiste nel racchiudere il metodo di destinazione in una classe e definire per la classe campi che verranno usati come parametri per il nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="271be-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="271be-107">Il vantaggio di questo approccio consiste nella possibilità di creare una nuova istanza della classe con parametri propri ogni volta che si vuole iniziare un nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="271be-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="271be-108">Ad esempio, si supponga di avere una funzione che calcola l'area di un triangolo come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="271be-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```csharp  
double CalcArea(double Base, double Height)  
{  
    return 0.5 * Base * Height;  
}  
```  
  
 <span data-ttu-id="271be-109">È possibile scrivere una classe che racchiuda la funzione `CalcArea` e crei i campi in cui memorizzare i parametri di input come segue:</span><span class="sxs-lookup"><span data-stu-id="271be-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
```csharp  
class AreaClass  
{  
    public double Base;  
    public double Height;  
    public double Area;  
    public void CalcArea()  
    {  
        Area = 0.5 * Base * Height;  
        MessageBox.Show("The area is: " + Area.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="271be-110">Per usare `AreaClass`, è possibile creare un oggetto `AreaClass` e impostare le proprietà `Base` e `Height` come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="271be-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
```csharp  
protected void TestArea()  
{  
    AreaClass AreaObject = new AreaClass();  
  
    System.Threading.Thread Thread =  
        new System.Threading.Thread(AreaObject.CalcArea);  
    AreaObject.Base = 30;  
    AreaObject.Height = 40;  
    Thread.Start();  
}  
```  
  
 <span data-ttu-id="271be-111">Si noti che la routine `TestArea` non verifica il valore del campo `Area` dopo che è stato chiamato il metodo `CalcArea`.</span><span class="sxs-lookup"><span data-stu-id="271be-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="271be-112">Poiché `CalcArea` viene eseguita su un thread separato, il campo `Area` non sarà necessariamente impostato se lo si controlla subito dopo avere chiamato `Thread.Start`.</span><span class="sxs-lookup"><span data-stu-id="271be-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="271be-113">La sezione seguente illustra un metodo più efficace per la restituzione di valori dalle routine multithreading.</span><span class="sxs-lookup"><span data-stu-id="271be-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="271be-114">Restituzione di valori da routine multithreading</span><span class="sxs-lookup"><span data-stu-id="271be-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="271be-115">La restituzione di valori da routine eseguite su thread diversi è resa complessa dal fatto che le routine non possono essere funzioni e non possono usare argomenti `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="271be-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="271be-116">Il modo più semplice per restituire i valori consiste nell'usare il componente <xref:System.ComponentModel.BackgroundWorker> per gestire i thread e generare un evento dopo aver completato l'attività e quindi elaborare i risultati con un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="271be-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="271be-117">L'esempio seguente restituisce un valore generando un evento da una routine eseguita su un thread separato:</span><span class="sxs-lookup"><span data-stu-id="271be-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
```csharp  
class AreaClass2  
{  
    public double Base;  
    public double Height;  
    public double CalcArea()  
    {  
        // Calculate the area of a triangle.  
        return 0.5 * Base * Height;  
    }  
}  
  
private System.ComponentModel.BackgroundWorker BackgroundWorker1  
    = new System.ComponentModel.BackgroundWorker();  
  
private void TestArea2()  
{  
    InitializeBackgroundWorker();  
  
    AreaClass2 AreaObject2 = new AreaClass2();  
    AreaObject2.Base = 30;  
    AreaObject2.Height = 40;  
  
    // Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2);  
}  
  
private void InitializeBackgroundWorker()  
{  
    // Attach event handlers to the BackgroundWorker object.  
    BackgroundWorker1.DoWork +=  
        new System.ComponentModel.DoWorkEventHandler(BackgroundWorker1_DoWork);  
    BackgroundWorker1.RunWorkerCompleted +=  
        new System.ComponentModel.RunWorkerCompletedEventHandler(BackgroundWorker1_RunWorkerCompleted);  
}  
  
private void BackgroundWorker1_DoWork(  
    object sender,  
    System.ComponentModel.DoWorkEventArgs e)  
{  
    AreaClass2 AreaObject2 = (AreaClass2)e.Argument;  
    // Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea();  
}  
  
private void BackgroundWorker1_RunWorkerCompleted(  
    object sender,  
    System.ComponentModel.RunWorkerCompletedEventArgs e)  
{  
    // Access the result through the Result property.  
    double Area = (double)e.Result;  
    MessageBox.Show("The area is: " + Area.ToString());  
}  
```  
  
 <span data-ttu-id="271be-118">La variabile facoltativa dell'oggetto di stato `ByVal` del metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> consente di inserire parametri e restituire valori ai thread del pool di thread.</span><span class="sxs-lookup"><span data-stu-id="271be-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="271be-119">Un oggetto di stato è supportato a questo scopo anche dai thread dei timer di thread.</span><span class="sxs-lookup"><span data-stu-id="271be-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="271be-120">Per informazioni sul pooling dei thread e i timer di thread, vedere [Creazione di pool di thread (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) e [Timer di thread (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).</span><span class="sxs-lookup"><span data-stu-id="271be-120">For information on thread pooling and thread timers, see [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) and [Thread Timers (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="271be-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="271be-121">See Also</span></span>  
 [<span data-ttu-id="271be-122">Procedura dettagliata: Multithreading con il componente BackgroundWorker (C#)</span><span class="sxs-lookup"><span data-stu-id="271be-122">Walkthrough: Multithreading with the BackgroundWorker Component (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [<span data-ttu-id="271be-123">Creazione di pool di thread (C#)</span><span class="sxs-lookup"><span data-stu-id="271be-123">Thread Pooling (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="271be-124">Sincronizzazione di thread (C#)</span><span class="sxs-lookup"><span data-stu-id="271be-124">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="271be-125">Eventi</span><span class="sxs-lookup"><span data-stu-id="271be-125">Events</span></span>](../../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="271be-126">Applicazioni multithreading (C#)</span><span class="sxs-lookup"><span data-stu-id="271be-126">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="271be-127">Delegati</span><span class="sxs-lookup"><span data-stu-id="271be-127">Delegates</span></span>](../../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="271be-128">Multithreading nei componenti</span><span class="sxs-lookup"><span data-stu-id="271be-128">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
