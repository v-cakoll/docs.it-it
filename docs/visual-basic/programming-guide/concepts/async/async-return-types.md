---
title: Tipi restituiti asincroni (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a62556fb93a3d8547d880e4ea6770b206ead900
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="async-return-types-visual-basic"></a><span data-ttu-id="67c78-102">Tipi restituiti asincroni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67c78-102">Async Return Types (Visual Basic)</span></span>
<span data-ttu-id="67c78-103">Metodi asincroni hanno tre possibili tipi restituiti: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>e void.</span><span class="sxs-lookup"><span data-stu-id="67c78-103">Async methods have three possible return types: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, and void.</span></span> <span data-ttu-id="67c78-104">In Visual Basic il tipo restituito void è scritto come routine [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="67c78-104">In Visual Basic, the void return type is written as a [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure.</span></span> <span data-ttu-id="67c78-105">Per ulteriori informazioni sui metodi asincroni, vedere [la programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="67c78-105">For more information about async methods, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="67c78-106">Ogni tipo restituito viene esaminato in una delle sezioni seguenti e alla fine dell'argomento è disponibile un esempio completo che usa tutti i tre tipi.</span><span class="sxs-lookup"><span data-stu-id="67c78-106">Each return type is examined in one of the following sections, and you can find a full example that uses all three types at the end of the topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67c78-107">Per eseguire l'esempio, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.</span><span class="sxs-lookup"><span data-stu-id="67c78-107">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="67c78-108"><a name="BKMK_TaskTReturnType"></a> Tipo restituito task(T)</span><span class="sxs-lookup"><span data-stu-id="67c78-108"><a name="BKMK_TaskTReturnType"></a> Task(T) Return Type</span></span>  
 <span data-ttu-id="67c78-109">Il <xref:System.Threading.Tasks.Task%601> tipo restituito viene utilizzato per un metodo asincrono che contiene un [restituire](../../../../visual-basic/language-reference/statements/return-statement.md) istruzione in cui l'operando è di tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="67c78-109">The <xref:System.Threading.Tasks.Task%601> return type is used for an async method that contains a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement in which the operand has type `TResult`.</span></span>  
  
 <span data-ttu-id="67c78-110">Nell'esempio seguente il metodo asincrono `TaskOfT_MethodAsync` contiene un'istruzione return che restituisce un valore intero.</span><span class="sxs-lookup"><span data-stu-id="67c78-110">In the following example, the `TaskOfT_MethodAsync` async method contains a return statement that returns an integer.</span></span> <span data-ttu-id="67c78-111">La dichiarazione del metodo deve quindi specificare un tipo restituito di `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="67c78-111">Therefore, the method declaration must specify a return type of `Task(Of Integer)`.</span></span>  
  
```vb  
' TASK(OF T) EXAMPLE  
Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.FromResult is a placeholder for actual work that returns a string.  
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
    ' The method then can process the result in some way.  
    Dim leisureHours As Integer  
    If today.First() = "S" Then  
        leisureHours = 16  
    Else  
        leisureHours = 5  
    End If  
  
    ' Because the return statement specifies an operand of type Integer, the   
    ' method must have a return type of Task(Of Integer).   
    Return leisureHours  
End Function  
```  
  
 <span data-ttu-id="67c78-112">Quando `TaskOfT_MethodAsync` viene chiamato da un'espressione await, l'espressione recupera il valore intero (valore di `leisureHours`) archiviato nell'attività restituita da `TaskOfT_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="67c78-112">When `TaskOfT_MethodAsync` is called from within an await expression, the await expression retrieves the integer value (the value of `leisureHours`) that's stored in the task that's returned by `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="67c78-113">Per ulteriori informazioni sulle espressioni await, vedere [operatore Await](../../../../visual-basic/language-reference/operators/await-operator.md).</span><span class="sxs-lookup"><span data-stu-id="67c78-113">For more information about await expressions, see [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md).</span></span>  
  
 <span data-ttu-id="67c78-114">Il codice seguente chiama e attende il metodo `TaskOfT_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="67c78-114">The following code calls and awaits method `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="67c78-115">Il risultato viene assegnato alla variabile `result1`.</span><span class="sxs-lookup"><span data-stu-id="67c78-115">The result is assigned to the `result1` variable.</span></span>  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 <span data-ttu-id="67c78-116">È possibile capire meglio il modo in cui ciò avviene separando la chiamata a `TaskOfT_MethodAsync` dall'applicazione di `Await`, come illustrato dal codice seguente.</span><span class="sxs-lookup"><span data-stu-id="67c78-116">You can better understand how this happens by separating the call to `TaskOfT_MethodAsync` from the application of `Await`, as the following code shows.</span></span> <span data-ttu-id="67c78-117">Una chiamata al metodo `TaskOfT_MethodAsync` che non viene immediatamente attesa restituisce un tipo `Task(Of Integer)`, come ci si aspetterebbe dalla dichiarazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="67c78-117">A call to method `TaskOfT_MethodAsync` that isn't immediately awaited returns a `Task(Of Integer)`, as you would expect from the declaration of the method.</span></span> <span data-ttu-id="67c78-118">Nell'esempio, l'attività viene assegnata alla variabile `integerTask`.</span><span class="sxs-lookup"><span data-stu-id="67c78-118">The task is assigned to the `integerTask` variable in the example.</span></span> <span data-ttu-id="67c78-119">Poiché `integerTask` è un <xref:System.Threading.Tasks.Task%601>, contiene una proprietà <xref:System.Threading.Tasks.Task%601.Result> di tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="67c78-119">Because `integerTask` is a <xref:System.Threading.Tasks.Task%601>, it contains a <xref:System.Threading.Tasks.Task%601.Result> property of type `TResult`.</span></span> <span data-ttu-id="67c78-120">In questo caso, TResult rappresenta un tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="67c78-120">In this case, TResult represents an integer type.</span></span> <span data-ttu-id="67c78-121">Quando si applica `Await` a `integerTask`, l'espressione await restituisce il contenuto della proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> di `integerTask`.</span><span class="sxs-lookup"><span data-stu-id="67c78-121">When `Await` is applied to `integerTask`, the await expression evaluates to the contents of the <xref:System.Threading.Tasks.Task%601.Result%2A> property of `integerTask`.</span></span> <span data-ttu-id="67c78-122">Il valore viene assegnato alla variabile `result2`.</span><span class="sxs-lookup"><span data-stu-id="67c78-122">The value is assigned to the `result2` variable.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="67c78-123">La proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> è una proprietà di blocco.</span><span class="sxs-lookup"><span data-stu-id="67c78-123">The <xref:System.Threading.Tasks.Task%601.Result%2A> property is a blocking property.</span></span> <span data-ttu-id="67c78-124">Se si prova ad accedervi prima del completamento dell'attività, il thread attualmente attivo viene bloccato fino a quando l'attività non viene completata e il valore non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="67c78-124">If you try to access it before its task is finished, the thread that's currently active is blocked until the task completes and the value is available.</span></span> <span data-ttu-id="67c78-125">Nella maggior parte dei casi, è consigliabile accedere al valore usando `Await` invece di accedere direttamente alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="67c78-125">In most cases, you should access the value by using `Await` instead of accessing the property directly.</span></span>  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 <span data-ttu-id="67c78-126">Le istruzioni di visualizzazione nel codice seguente verificano che i valori della variabile `result1`, della variabile `result2` e della proprietà `Result` siano identici.</span><span class="sxs-lookup"><span data-stu-id="67c78-126">The display statements in the following code verify that the values of the `result1` variable, the `result2` variable, and the `Result` property are the same.</span></span> <span data-ttu-id="67c78-127">Si noti che la proprietà `Result` è una proprietà di blocco e non ci si deve accedere prima che la sua attività sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="67c78-127">Remember that the `Result` property is a blocking property and shouldn't be accessed before its task has been awaited.</span></span>  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <span data-ttu-id="67c78-128"><a name="BKMK_TaskReturnType"></a> Tipo restituito Task</span><span class="sxs-lookup"><span data-stu-id="67c78-128"><a name="BKMK_TaskReturnType"></a> Task Return Type</span></span>  
 <span data-ttu-id="67c78-129">I metodi asincroni che non contengono un'istruzione return o che contengono un'istruzione return che non restituisce un operando in genere hanno un tipo restituito di <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="67c78-129">Async methods that don't contain a return statement or that contain a return statement that doesn't return an operand usually have a return type of <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="67c78-130">Tali metodi sarebbero [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure se fossero scritti per l'esecuzione sincrona.</span><span class="sxs-lookup"><span data-stu-id="67c78-130">Such methods would be [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedures if they were written to run synchronously.</span></span> <span data-ttu-id="67c78-131">Se si usa un tipo restituito `Task` per un metodo asincrono, un metodo chiamante può usare un operatore `Await` per sospendere il completamento del chiamante fino a quando il metodo asincrono chiamato non abbia terminato l'operazione.</span><span class="sxs-lookup"><span data-stu-id="67c78-131">If you use a `Task` return type for an async method, a calling method can use an `Await` operator to suspend the caller's completion until the called async method has finished.</span></span>  
  
 <span data-ttu-id="67c78-132">Nell'esempio seguente il metodo asincrono `Task_MethodAsync` non contiene un'istruzione return.</span><span class="sxs-lookup"><span data-stu-id="67c78-132">In the following example, async method `Task_MethodAsync` doesn't contain a return statement.</span></span> <span data-ttu-id="67c78-133">Di conseguenza, si specifica un tipo restituito `Task` per il metodo, che consente a `Task_MethodAsync` di essere atteso.</span><span class="sxs-lookup"><span data-stu-id="67c78-133">Therefore, you specify a return type of `Task` for the method, which enables `Task_MethodAsync` to be awaited.</span></span> <span data-ttu-id="67c78-134">La definizione del tipo `Task` non include una proprietà `Result` per archiviare un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="67c78-134">The definition of the `Task` type doesn't include a `Result` property to store a return value.</span></span>  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 <span data-ttu-id="67c78-135">`Task_MethodAsync`viene chiamato e atteso usando un'istruzione await invece un'espressione await, simile all'istruzione chiamante per un oggetto sincrono `Sub` o un metodo che restituisce void.</span><span class="sxs-lookup"><span data-stu-id="67c78-135">`Task_MethodAsync` is called and awaited by using an await statement instead of an await expression, similar to the calling statement for a synchronous `Sub` or void-returning method.</span></span> <span data-ttu-id="67c78-136">L'applicazione di un `Await` operatore in questo caso non produce un valore.</span><span class="sxs-lookup"><span data-stu-id="67c78-136">The application of an `Await` operator in this case doesn't produce a value.</span></span>  
  
 <span data-ttu-id="67c78-137">Il codice seguente chiama e attende il metodo `Task_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="67c78-137">The following code calls and awaits method `Task_MethodAsync`.</span></span>  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 <span data-ttu-id="67c78-138">Come il precedente <xref:System.Threading.Tasks.Task%601> esempio, è possibile separare la chiamata a `Task_MethodAsync` dall'applicazione di un `Await` (operatore), come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="67c78-138">As in the previous <xref:System.Threading.Tasks.Task%601> example, you can separate the call to `Task_MethodAsync` from the application of an `Await` operator, as the following code shows.</span></span> <span data-ttu-id="67c78-139">Tuttavia, si noti che un tipo `Task` non ha una proprietà `Result` e che quando viene applicato un operatore await a un tipo `Task` non viene prodotto alcun valore.</span><span class="sxs-lookup"><span data-stu-id="67c78-139">However, remember that a `Task` doesn't have a `Result` property, and that no value is produced when an await operator is applied to a `Task`.</span></span>  
  
 <span data-ttu-id="67c78-140">Il codice seguente separa la chiamata di `Task_MethodAsync` dall'attesa dell'attività restituita da `Task_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="67c78-140">The following code separates calling `Task_MethodAsync` from awaiting the task that `Task_MethodAsync` returns.</span></span>  
  
```vb  
' Call and await in separate statements.  
Dim simpleTask As Task = Task_MethodAsync()  
  
' You can do other work that does not rely on simpleTask before awaiting.  
textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
Await simpleTask  
```  
  
##  <span data-ttu-id="67c78-141"><a name="BKMK_VoidReturnType"></a> Tipo restituito void</span><span class="sxs-lookup"><span data-stu-id="67c78-141"><a name="BKMK_VoidReturnType"></a> Void Return Type</span></span>  
 <span data-ttu-id="67c78-142">L'utilizzo principale di `Sub` è procedure nei gestori eventi, in cui è presente alcun tipo restituito (definito da un tipo restituito void in altri linguaggi).</span><span class="sxs-lookup"><span data-stu-id="67c78-142">The primary use of `Sub` procedures is in event handlers, where there is no return type (referred to as a void return type in other languages).</span></span> <span data-ttu-id="67c78-143">Un tipo restituito void può essere usato anche per eseguire l'override di metodi che restituiscono void o per metodi che eseguono attività che possono essere categorizzate come "Fire and Forget".</span><span class="sxs-lookup"><span data-stu-id="67c78-143">A void return also can be used to override void-returning methods or for methods that perform activities that can be categorized as "fire and forget."</span></span> <span data-ttu-id="67c78-144">È consigliabile tuttavia restituire un tipo `Task` ogni volta che è possibile, perché un metodo asincrono che restituisce void non può essere atteso.</span><span class="sxs-lookup"><span data-stu-id="67c78-144">However, you should return a `Task` wherever possible, because a void-returning async method can't be awaited.</span></span> <span data-ttu-id="67c78-145">Qualsiasi chiamante di questo metodo deve poter continuare fino al completamento senza attendere il completamento del metodo asincrono chiamato e il chiamante deve essere indipendente da qualsiasi eccezione o valore generato dal metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="67c78-145">Any caller of such a method must be able to continue to completion without waiting for the called async method to finish, and the caller must be independent of any values or exceptions that the async method generates.</span></span>  
  
 <span data-ttu-id="67c78-146">Il chiamante di un metodo asincrono che restituisce void non può intercettare le eccezioni generate dal metodo ed è probabile che queste eccezioni non gestite provochino un errore dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="67c78-146">The caller of a void-returning async method can't catch exceptions that are thrown from the method, and such unhandled exceptions are likely to cause your application to fail.</span></span> <span data-ttu-id="67c78-147">Se si verifica un'eccezione in un metodo asincrono che restituisce un <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, l'eccezione viene archiviata nell'attività restituita e rigenerata durante l'attesa dell'attività.</span><span class="sxs-lookup"><span data-stu-id="67c78-147">If an exception occurs in an async method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>, the exception is stored in the returned task, and rethrown when the task is awaited.</span></span> <span data-ttu-id="67c78-148">Di conseguenza, verificare che qualsiasi metodo asincrono in grado di produrre un'eccezione abbia un tipo restituito <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> e che sia impostata l'attesa per le chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="67c78-148">Therefore, make sure that any async method that can produce an exception has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> and that calls to the method are awaited.</span></span>  
  
 <span data-ttu-id="67c78-149">Per altre informazioni su come intercettare eccezioni nei metodi asincroni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="67c78-149">For more information about how to catch exceptions in async methods, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="67c78-150">Il codice seguente definisce un gestore eventi asincroni.</span><span class="sxs-lookup"><span data-stu-id="67c78-150">The following code defines an async event handler.</span></span>  
  
```vb  
' SUB EXAMPLE  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
    textBox1.Clear()  
  
    ' Start the process and await its completion. DriverAsync is a   
    ' Task-returning async method.  
    Await DriverAsync()  
  
    ' Say goodbye.  
    textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
End Sub  
```  
  
##  <span data-ttu-id="67c78-151"><a name="BKMK_Example"></a> Esempio completo</span><span class="sxs-lookup"><span data-stu-id="67c78-151"><a name="BKMK_Example"></a> Complete Example</span></span>  
 <span data-ttu-id="67c78-152">Il progetto Windows Presentation Foundation (WPF) seguente contiene gli esempi di codice di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="67c78-152">The following Windows Presentation Foundation (WPF) project contains the code examples from this topic.</span></span>  
  
 <span data-ttu-id="67c78-153">Per eseguire il progetto, effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="67c78-153">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="67c78-154">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="67c78-154">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="67c78-155">Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="67c78-155">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="67c78-156">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="67c78-156">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="67c78-157">Nel **installato**, **modelli** categoria, scegliere **Visual Basic**, quindi scegliere **Windows**.</span><span class="sxs-lookup"><span data-stu-id="67c78-157">In the **Installed**, **Templates** category, choose **Visual Basic**, and then choose **Windows**.</span></span> <span data-ttu-id="67c78-158">Dall'elenco dei tipi di progetto scegliere **Applicazione WPF**.</span><span class="sxs-lookup"><span data-stu-id="67c78-158">Choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="67c78-159">Immettere `AsyncReturnTypes` come nome del progetto e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="67c78-159">Enter `AsyncReturnTypes` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="67c78-160">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="67c78-160">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="67c78-161">Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="67c78-161">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="67c78-162">Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow.xaml in **Esplora soluzioni** e quindi scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="67c78-162">If the tab is not visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **Open**.</span></span>  
  
6.  <span data-ttu-id="67c78-163">Nella finestra **XAML** di MainWindow.xaml sostituire il codice con quello seguente.</span><span class="sxs-lookup"><span data-stu-id="67c78-163">In the **XAML** window of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="67c78-164">Nella finestra di **progettazione**di MainWindow.xaml verrà visualizzata una finestra contenente una casella di testo e un pulsante.</span><span class="sxs-lookup"><span data-stu-id="67c78-164">A simple window that contains a text box and a button appears in the **Design** window of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="67c78-165">In **Esplora**, aprire il menu di scelta rapida per file e quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="67c78-165">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
8.  <span data-ttu-id="67c78-166">Sostituire il codice in MainWindow.xaml.vb con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="67c78-166">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' SUB EXAMPLE  
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
            textBox1.Clear()  
  
            ' Start the process and await its completion. DriverAsync is a   
            ' Task-returning async method.  
            Await DriverAsync()  
  
            ' Say goodbye.  
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
        End Sub  
  
        Async Function DriverAsync() As Task  
  
            ' Task(Of T)   
            ' Call and await the Task(Of T)-returning async method in the same statement.  
            Dim result1 As Integer = Await TaskOfT_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
            ' You can do other work that does not rely on resultTask before awaiting.  
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
            Await simpleTask  
        End Function  
  
        ' TASK(OF T) EXAMPLE  
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.FromResult is a placeholder for actual work that returns a string.  
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
            ' The method then can process the result in some way.  
            Dim leisureHours As Integer  
            If today.First() = "S" Then  
                leisureHours = 16  
            Else  
                leisureHours = 5  
            End If  
  
            ' Because the return statement specifies an operand of type Integer, the   
            ' method must have a return type of Task(Of Integer).   
            Return leisureHours  
        End Function  
  
        ' TASK EXAMPLE  
        Async Function Task_MethodAsync() As Task  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.Delay is a placeholder for actual work.  
            Await Task.Delay(2000)  
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
    ```  
  
9. <span data-ttu-id="67c78-167">Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .</span><span class="sxs-lookup"><span data-stu-id="67c78-167">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="67c78-168">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="67c78-168">The following output should appear.</span></span>  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="67c78-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67c78-169">See Also</span></span>  
 <xref:System.Threading.Tasks.Task.FromResult%2A>  
 [<span data-ttu-id="67c78-170">Procedura dettagliata: Accesso al Web con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67c78-170">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="67c78-171">Flusso di controllo in programmi asincroni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67c78-171">Control Flow in Async Programs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)  
 [<span data-ttu-id="67c78-172">Async</span><span class="sxs-lookup"><span data-stu-id="67c78-172">Async</span></span>](../../../../visual-basic/language-reference/modifiers/async.md)  
 [<span data-ttu-id="67c78-173">Operatore Await</span><span class="sxs-lookup"><span data-stu-id="67c78-173">Await Operator</span></span>](../../../../visual-basic/language-reference/operators/await-operator.md)
