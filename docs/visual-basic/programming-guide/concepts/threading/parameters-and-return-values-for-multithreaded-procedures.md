---
title: Parametri e valori restituiti per routine multithreading (Visual Basic)
ms.date: 07/20/2015
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
ms.openlocfilehash: 545da3e89d44c29c67784b5f01812d87350030c6
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874611"
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a><span data-ttu-id="221b5-102">Parametri e valori restituiti per routine multithreading (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="221b5-102">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>
<span data-ttu-id="221b5-103">L'invio e la restituzione di valori in un'applicazione multithreading è un processo complesso poiché è necessario che il costruttore della classe di thread riceva un riferimento a una routine che non accetta alcun argomento e non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="221b5-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="221b5-104">Le sezioni seguenti descrivono alcuni metodi semplici per l'inserimento di parametri e la restituzione di valori da routine su thread diversi.</span><span class="sxs-lookup"><span data-stu-id="221b5-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="221b5-105">Inserimento di parametri per routine multithreading</span><span class="sxs-lookup"><span data-stu-id="221b5-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="221b5-106">Il modo migliore per inserire i parametri per una chiamata di metodo multithreading consiste nel racchiudere il metodo di destinazione in una classe e definire per la classe campi che verranno usati come parametri per il nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="221b5-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="221b5-107">Il vantaggio di questo approccio consiste nella possibilità di creare una nuova istanza della classe con parametri propri ogni volta che si vuole iniziare un nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="221b5-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="221b5-108">Ad esempio, si supponga di avere una funzione che calcola l'area di un triangolo come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="221b5-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 <span data-ttu-id="221b5-109">È possibile scrivere una classe che racchiuda la funzione `CalcArea` e crei i campi in cui memorizzare i parametri di input come segue:</span><span class="sxs-lookup"><span data-stu-id="221b5-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
```vb  
Class AreaClass  
    Public Base As Double  
    Public Height As Double  
    Public Area As Double  
    Sub CalcArea()  
        Area = 0.5 * Base * Height  
        MessageBox.Show("The area is: " & Area.ToString)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="221b5-110">Per usare `AreaClass`, è possibile creare un oggetto `AreaClass` e impostare le proprietà `Base` e `Height` come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="221b5-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
```vb  
Protected Sub TestArea()  
    Dim AreaObject As New AreaClass  
    Dim Thread As New System.Threading.Thread(  
                        AddressOf AreaObject.CalcArea)  
    AreaObject.Base = 30  
    AreaObject.Height = 40  
    Thread.Start()  
End Sub  
```  
  
 <span data-ttu-id="221b5-111">Si noti che la routine `TestArea` non verifica il valore del campo `Area` dopo che è stato chiamato il metodo `CalcArea`.</span><span class="sxs-lookup"><span data-stu-id="221b5-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="221b5-112">Poiché `CalcArea` viene eseguita su un thread separato, il campo `Area` non sarà necessariamente impostato se lo si controlla subito dopo avere chiamato `Thread.Start`.</span><span class="sxs-lookup"><span data-stu-id="221b5-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="221b5-113">La sezione seguente illustra un metodo più efficace per la restituzione di valori dalle routine multithreading.</span><span class="sxs-lookup"><span data-stu-id="221b5-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="221b5-114">Restituzione di valori da routine multithreading</span><span class="sxs-lookup"><span data-stu-id="221b5-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="221b5-115">La restituzione di valori da routine eseguite su thread diversi è resa complessa dal fatto che le routine non possono essere funzioni e non possono usare argomenti `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="221b5-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="221b5-116">Il modo più semplice per restituire i valori consiste nell'usare il componente <xref:System.ComponentModel.BackgroundWorker> per gestire i thread e generare un evento dopo aver completato l'attività e quindi elaborare i risultati con un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="221b5-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="221b5-117">L'esempio seguente restituisce un valore generando un evento da una routine eseguita su un thread separato:</span><span class="sxs-lookup"><span data-stu-id="221b5-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
```vb  
Private Class AreaClass2  
    Public Base As Double  
    Public Height As Double  
    Function CalcArea() As Double  
        ' Calculate the area of a triangle.  
        Return 0.5 * Base * Height  
    End Function  
End Class  
  
Private WithEvents BackgroundWorker1 As New System.ComponentModel.BackgroundWorker  
  
Private Sub TestArea2()  
    Dim AreaObject2 As New AreaClass2  
    AreaObject2.Base = 30  
    AreaObject2.Height = 40  
  
    ' Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2)  
End Sub  
  
' This method runs on the background thread when it starts.  
Private Sub BackgroundWorker1_DoWork(  
    ByVal sender As Object,   
    ByVal e As System.ComponentModel.DoWorkEventArgs  
    ) Handles BackgroundWorker1.DoWork  
  
    Dim AreaObject2 As AreaClass2 = CType(e.Argument, AreaClass2)  
    ' Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea()  
End Sub  
  
' This method runs on the main thread when the background thread finishes.  
Private Sub BackgroundWorker1_RunWorkerCompleted(  
    ByVal sender As Object,  
    ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
    ) Handles BackgroundWorker1.RunWorkerCompleted  
  
    ' Access the result through the Result property.  
    Dim Area As Double = CDbl(e.Result)  
    MessageBox.Show("The area is: " & Area.ToString)  
End Sub  
```  
  
 <span data-ttu-id="221b5-118">La variabile facoltativa dell'oggetto di stato `ByVal` del metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> consente di inserire parametri e restituire valori ai thread del pool di thread.</span><span class="sxs-lookup"><span data-stu-id="221b5-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="221b5-119">Un oggetto di stato è supportato a questo scopo anche dai thread dei timer di thread.</span><span class="sxs-lookup"><span data-stu-id="221b5-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="221b5-120">Per informazioni sul pooling dei thread e i timer di thread, vedere [pool di Thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[pool di Thread](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) e [timer](../../../../standard/threading/timers.md).</span><span class="sxs-lookup"><span data-stu-id="221b5-120">For information on thread pooling and thread timers, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Thread Pooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) and [Timers](../../../../standard/threading/timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221b5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="221b5-121">See Also</span></span>  
 [<span data-ttu-id="221b5-122">Procedura dettagliata: Multithreading con il componente BackgroundWorker (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="221b5-122">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [<span data-ttu-id="221b5-123">Creazione di pool di thread (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="221b5-123">Thread Pooling (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="221b5-124">Sincronizzazione di thread (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="221b5-124">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="221b5-125">Eventi</span><span class="sxs-lookup"><span data-stu-id="221b5-125">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="221b5-126">Applicazioni multithreading (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="221b5-126">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="221b5-127">Delegati</span><span class="sxs-lookup"><span data-stu-id="221b5-127">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="221b5-128">Multithreading nei componenti</span><span class="sxs-lookup"><span data-stu-id="221b5-128">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
