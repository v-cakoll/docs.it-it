---
title: Parametri e valori restituiti per routine multithreading (Visual Basic) | Documenti di Microsoft
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
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
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
ms.openlocfilehash: 6d1eb53454b6e0d964be15df2e320ce189e7d875
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a><span data-ttu-id="0bd7b-102">Parametri e valori restituiti per routine multithreading (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bd7b-102">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>
<span data-ttu-id="0bd7b-103">Invio e la restituzione di valori in un'applicazione multithreading è complesso perché il costruttore della classe di thread deve essere passato un riferimento a una routine che non accetta argomenti e non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="0bd7b-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="0bd7b-104">Le sezioni seguenti mostrano alcuni semplici metodi per fornire i parametri e valori restituiti da procedure su un thread separato.</span><span class="sxs-lookup"><span data-stu-id="0bd7b-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="0bd7b-105">Fornendo i parametri per routine multithreading</span><span class="sxs-lookup"><span data-stu-id="0bd7b-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="0bd7b-106">Il modo migliore per fornire i parametri per una chiamata al metodo multithreading consiste nel racchiudere il metodo di destinazione in una classe e definire i campi per la classe che verrà utilizzato come parametri per il nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="0bd7b-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="0bd7b-107">Il vantaggio di questo approccio è che è possibile creare una nuova istanza della classe, con i propri parametri, ogni volta che si desidera avviare un nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="0bd7b-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="0bd7b-108">Ad esempio, si supponga di che avere una funzione che calcola l'area di un triangolo, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0bd7b-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 <span data-ttu-id="0bd7b-109">È possibile scrivere una classe che esegue il wrapping di `CalcArea` funzione e crea i campi per archiviare i parametri di input, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0bd7b-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
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
  
 <span data-ttu-id="0bd7b-110">Utilizzare il `AreaClass`, è possibile creare un `AreaClass` oggetto e impostare il `Base` e `Height` proprietà come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0bd7b-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
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
  
 <span data-ttu-id="0bd7b-111">Si noti che il `TestArea` routine non verifica il valore di `Area` campo dopo la chiamata di `CalcArea` (metodo).</span><span class="sxs-lookup"><span data-stu-id="0bd7b-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="0bd7b-112">Poiché `CalcArea` viene eseguito in un thread separato, il `Area` campo non è necessariamente impostato se lo si controlla subito dopo aver chiamato `Thread.Start`.</span><span class="sxs-lookup"><span data-stu-id="0bd7b-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="0bd7b-113">Nella sezione successiva viene illustrato un modo migliore per restituire valori dalle routine multithreading.</span><span class="sxs-lookup"><span data-stu-id="0bd7b-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="0bd7b-114">Restituzione di valori da routine multithreading</span><span class="sxs-lookup"><span data-stu-id="0bd7b-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="0bd7b-115">Restituzione di valori da routine eseguite su thread diversi è complicata dal fatto che le procedure non possono essere funzioni e non possono utilizzare `ByRef` argomenti.</span><span class="sxs-lookup"><span data-stu-id="0bd7b-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="0bd7b-116">Il modo più semplice per restituire i valori è utilizzare il <xref:System.ComponentModel.BackgroundWorker>componente per gestire i thread e generare un evento quando viene eseguita l'attività ed elaborare i risultati a un gestore eventi.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="0bd7b-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="0bd7b-117">Nell'esempio seguente restituisce un valore generando un evento da una routine in esecuzione su un thread separato:</span><span class="sxs-lookup"><span data-stu-id="0bd7b-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
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
  
 <span data-ttu-id="0bd7b-118">È possibile fornire parametri e restituire valori ai thread di pool di thread utilizzando l'opzione facoltativa `ByVal` variabile dello stato dell'oggetto del <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>(metodo).</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="0bd7b-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="0bd7b-119">Thread di timer di thread supporta anche un oggetto di stato per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="0bd7b-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="0bd7b-120">Per informazioni sui pool di thread e timer di thread, vedere [(Visual Basic) il pool di Thread](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[il pool di Thread](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) e [il timer di Thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).</span><span class="sxs-lookup"><span data-stu-id="0bd7b-120">For information on thread pooling and thread timers, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Thread Pooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) and [Thread Timers (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd7b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bd7b-121">See Also</span></span>  
 <span data-ttu-id="0bd7b-122">[Procedura dettagliata: Multithreading con il componente BackgroundWorker (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span><span class="sxs-lookup"><span data-stu-id="0bd7b-122">[Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span></span>  
<span data-ttu-id="0bd7b-123"> [(Visual Basic) di pooling dei thread](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span><span class="sxs-lookup"><span data-stu-id="0bd7b-123"> [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span></span>  
<span data-ttu-id="0bd7b-124"> [Sincronizzazione dei thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="0bd7b-124"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md) </span></span>  
<span data-ttu-id="0bd7b-125"> [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bd7b-125"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="0bd7b-126"> [Applicazioni multithreading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="0bd7b-126"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="0bd7b-127"> [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="0bd7b-127"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="0bd7b-128"> [Multithreading nei componenti](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)</span><span class="sxs-lookup"><span data-stu-id="0bd7b-128"> [Multithreading in Components](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)</span></span>
