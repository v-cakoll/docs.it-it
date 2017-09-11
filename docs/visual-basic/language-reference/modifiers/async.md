---
title: Async (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 009b4ab71c185aec0cf54bb2360dcd897cdf7850
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="async-visual-basic"></a><span data-ttu-id="50aae-102">Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50aae-102">Async (Visual Basic)</span></span>
<span data-ttu-id="50aae-103">Il `Async` modificatore indica che il metodo o [espressione lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) che ha modificato è asincrono.</span><span class="sxs-lookup"><span data-stu-id="50aae-103">The `Async` modifier indicates that the method or [lambda expression](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) that it modifies is asynchronous.</span></span> <span data-ttu-id="50aae-104">Tali metodi sono definiti come *metodi async*.</span><span class="sxs-lookup"><span data-stu-id="50aae-104">Such methods are referred to as *async methods*.</span></span>  
  
 <span data-ttu-id="50aae-105">Un metodo asincrono è un modo pratico per eseguire le operazioni potenzialmente di lunga durata senza bloccare il thread del chiamante.</span><span class="sxs-lookup"><span data-stu-id="50aae-105">An async method provides a convenient way to do potentially long-running work without blocking the caller's thread.</span></span> <span data-ttu-id="50aae-106">Il chiamante di un metodo asincrono può riprendere un'operazione senza attendere il fine del metodo async.</span><span class="sxs-lookup"><span data-stu-id="50aae-106">The caller of an async method can resume its work without waiting for the async method to finish.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50aae-107">Le parole chiave `Async` e `Await` sono state introdotte in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="50aae-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="50aae-108">Per un'introduzione alla programmazione asincrona, vedere [la programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="50aae-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="50aae-109">Nell'esempio seguente viene illustrata la struttura di un metodo async.</span><span class="sxs-lookup"><span data-stu-id="50aae-109">The following example shows the structure of an async method.</span></span> <span data-ttu-id="50aae-110">Per convenzione, i nomi dei metodi async terminano con "Async".</span><span class="sxs-lookup"><span data-stu-id="50aae-110">By convention, async method names end in "Async."</span></span>  
  
```vb  
  
Public Async Function ExampleMethodAsync() As Task(Of Integer)  
    ' . . .  
  
    ' At the Await expression, execution in this method is suspended and,  
    ' if AwaitedProcessAsync has not already finished, control returns  
    ' to the caller of ExampleMethodAsync. When the awaited task is   
    ' completed, this method resumes execution.   
    Dim exampleInt As Integer = Await AwaitedProcessAsync()  
  
    ' . . .  
  
    ' The return statement completes the task. Any method that is   
    ' awaiting ExampleMethodAsync can now get the integer result.  
    Return exampleInt  
End Function  
```  
  
 <span data-ttu-id="50aae-111">In genere, un metodo modificato dal `Async` (parola chiave) contiene almeno un [Await](../../../visual-basic/language-reference/modifiers/async.md) espressione o un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="50aae-111">Typically, a method modified by the `Async` keyword contains at least one [Await](../../../visual-basic/language-reference/modifiers/async.md) expression or statement.</span></span> <span data-ttu-id="50aae-112">Il metodo funziona in modo sincrono fino al primo `Await`, a quel punto viene sospeso finché l'attività di cui si è in attesa non viene completata.</span><span class="sxs-lookup"><span data-stu-id="50aae-112">The method runs synchronously until it reaches the first `Await`, at which point it suspends until the awaited task completes.</span></span> <span data-ttu-id="50aae-113">Nel frattempo, il controllo viene restituito al chiamante del metodo.</span><span class="sxs-lookup"><span data-stu-id="50aae-113">In the meantime, control is returned to the caller of the method.</span></span> <span data-ttu-id="50aae-114">Se il metodo non contiene un'espressione o un'istruzione `Await`, il metodo non viene sospeso e viene eseguito come un metodo sincrono.</span><span class="sxs-lookup"><span data-stu-id="50aae-114">If the method doesn’t contain an `Await` expression or statement, the method isn’t suspended and executes as a synchronous method does.</span></span> <span data-ttu-id="50aae-115">Un avviso del compilatore segnala eventuali metodi asincroni che non contengono `Await` perché questa situazione potrebbe indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="50aae-115">A compiler warning alerts you to any async methods that don't contain `Await` because that situation might indicate an error.</span></span> <span data-ttu-id="50aae-116">Per ulteriori informazioni, vedere il [errore del compilatore](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="50aae-116">For more information, see the [compiler error](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).</span></span>  
  
 <span data-ttu-id="50aae-117">La parola chiave `Async` è una parola chiave non riservata.</span><span class="sxs-lookup"><span data-stu-id="50aae-117">The `Async` keyword is an unreserved keyword.</span></span> <span data-ttu-id="50aae-118">È una parola chiave quando si modifica un metodo o un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="50aae-118">It is a keyword when it modifies a method or a lambda expression.</span></span> <span data-ttu-id="50aae-119">In tutti gli altri contesti, viene interpretata come identificatore.</span><span class="sxs-lookup"><span data-stu-id="50aae-119">In all other contexts, it is interpreted as an identifier.</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="50aae-120">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="50aae-120">Return Types</span></span>  
 <span data-ttu-id="50aae-121">Un metodo asincrono è un [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedura, o un [funzione](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) procedura con un tipo restituito <xref:System.Threading.Tasks.Task>o <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="50aae-121">An async method is either a [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure, or a [Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) procedure that has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="50aae-122">Il metodo non può dichiarare [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parametri.</span><span class="sxs-lookup"><span data-stu-id="50aae-122">The method cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="50aae-123">Specificare `Task(Of TResult)` per il tipo restituito di un metodo async se il [restituire](../../../visual-basic/language-reference/statements/return-statement.md) istruzione del metodo include un operando di tipo TResult.</span><span class="sxs-lookup"><span data-stu-id="50aae-123">You specify `Task(Of TResult)` for the return type of an async method if the [Return](../../../visual-basic/language-reference/statements/return-statement.md) statement of the method has an operand of type TResult.</span></span> <span data-ttu-id="50aae-124">Utilizzare `Task` se non viene restituito alcun valore significativo al completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="50aae-124">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="50aae-125">In altre parole, una chiamata al metodo restituisce `Task`, ma quando `Task` viene completato, ogni istruzione `Await` in attesa di `Task` non produce un valore risultante.</span><span class="sxs-lookup"><span data-stu-id="50aae-125">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `Await` statement that's awaiting the `Task` doesn’t produce a result value.</span></span>  
  
 <span data-ttu-id="50aae-126">Le subroutine async vengono utilizzate principalmente per definire i gestori eventi in cui è richiesta una procedura `Sub`.</span><span class="sxs-lookup"><span data-stu-id="50aae-126">Async subroutines are used primarily to define event handlers where a `Sub` procedure is required.</span></span> <span data-ttu-id="50aae-127">Il chiamante di una subroutine async non può attendere il metodo e non può intercettare le eccezioni generate dal metodo.</span><span class="sxs-lookup"><span data-stu-id="50aae-127">The caller of an async subroutine can't await it and can't catch exceptions that the method throws.</span></span>  
  
 <span data-ttu-id="50aae-128">Per ulteriori informazioni ed esempi, vedere [Async restituire tipi](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="50aae-128">For more information and examples, see [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="50aae-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="50aae-129">Example</span></span>  
 <span data-ttu-id="50aae-130">Negli esempi seguenti viene illustrato un gestore eventi async, un'espressione lambda async e un metodo async.</span><span class="sxs-lookup"><span data-stu-id="50aae-130">The following examples show an async event handler, an async lambda expression, and an async method.</span></span> <span data-ttu-id="50aae-131">Per un esempio completo che utilizza questi elementi, vedere [procedura dettagliata: accesso al Web tramite Async e Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="50aae-131">For a full example that uses these elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="50aae-132">È possibile scaricare il codice di questa procedura dettagliata da [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span><span class="sxs-lookup"><span data-stu-id="50aae-132">You can download the walkthrough code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
  
```vb  
  
' An event handler must be a Sub procedure.  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
    textBox1.Clear()  
    ' SumPageSizesAsync is a method that returns a Task.  
    Await SumPageSizesAsync()  
    textBox1.Text = vbCrLf & "Control returned to button1_Click."  
End Sub  
  
' The following async lambda expression creates an equivalent anonymous  
' event handler.  
AddHandler button1.Click, Async Sub(sender, e)  
                              textBox1.Clear()  
                              ' SumPageSizesAsync is a method that returns a Task.  
                              Await SumPageSizesAsync()  
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."  
                          End Sub  
  
' The following async method returns a Task(Of T).  
' A typical call awaits the Byte array result:  
'      Dim result As Byte() = Await GetURLContents("http://msdn.com")  
Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
    ' The downloaded resource ends up in the variable named content.  
    Dim content = New MemoryStream()  
  
    ' Initialize an HttpWebRequest for the current URL.  
    Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
    ' Send the request to the Internet resource and wait for  
    ' the response.  
    Using response As WebResponse = Await webReq.GetResponseAsync()  
        ' Get the data stream that is associated with the specified URL.  
        Using responseStream As Stream = response.GetResponseStream()  
            ' Read the bytes in responseStream and copy them to content.    
            ' CopyToAsync returns a Task, not a Task<T>.  
            Await responseStream.CopyToAsync(content)  
        End Using  
    End Using  
  
    ' Return the result as a byte array.  
    Return content.ToArray()  
End Function  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="50aae-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50aae-133">See Also</span></span>  
 <span data-ttu-id="50aae-134"><xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute></xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute></span><span class="sxs-lookup"><span data-stu-id="50aae-134"><xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute></span></span>   
<span data-ttu-id="50aae-135"> [Await (operatore)](../../../visual-basic/language-reference/operators/await-operator.md) </span><span class="sxs-lookup"><span data-stu-id="50aae-135"> [Await Operator](../../../visual-basic/language-reference/operators/await-operator.md) </span></span>  
<span data-ttu-id="50aae-136"> [Programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="50aae-136"> [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="50aae-137"> [Procedura dettagliata: Accesso al Web tramite Async e Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span><span class="sxs-lookup"><span data-stu-id="50aae-137"> [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
