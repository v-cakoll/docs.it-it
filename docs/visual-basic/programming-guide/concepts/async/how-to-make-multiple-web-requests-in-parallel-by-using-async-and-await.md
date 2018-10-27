---
title: 'Procedura: effettuare più richieste Web in parallelo tramite Async e Await (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
ms.openlocfilehash: 44531ef643df6402ad318957c0a2bdc058c5bcb0
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195035"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a><span data-ttu-id="6916b-102">Procedura: effettuare più richieste Web in parallelo tramite Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6916b-102">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>
<span data-ttu-id="6916b-103">In un metodo asincrono le attività vengono avviate al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="6916b-103">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="6916b-104">Il [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operatore viene applicato all'attività nel punto nel metodo in cui non è possibile continuare l'elaborazione fino al termine dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6916b-104">The [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="6916b-105">Spesso un'attività viene messa in attesa al momento della creazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6916b-105">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>  
  
```vb  
Dim result = Await someWebAccessMethodAsync(url)  
```  
  
 <span data-ttu-id="6916b-106">Tuttavia, è possibile separare la creazione dalla messa in attesa dell'attività se il programma ha altro lavoro da eseguire che non dipende dal completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6916b-106">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>  
  
```vb  
' The following line creates and starts the task.  
Dim myTask = someWebAccessMethodAsync(url)  
  
' While the task is running, you can do other work that does not depend  
' on the results of the task.  
' . . . . .  
  
' The application of Await suspends the rest of this method until the task is   
' complete.  
Dim result = Await myTask  
```  
  
 <span data-ttu-id="6916b-107">Tra l'avvio di un'attività e la messa in attesa, è possibile avviare altre attività.</span><span class="sxs-lookup"><span data-stu-id="6916b-107">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="6916b-108">Le attività aggiuntive vengono eseguite in modo implicito in parallelo, ma non vengono creati thread aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="6916b-108">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>  
  
 <span data-ttu-id="6916b-109">Il programma seguente avvia tre download Web asincroni e quindi li mette in attesa nell'ordine in cui vengono chiamati.</span><span class="sxs-lookup"><span data-stu-id="6916b-109">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="6916b-110">Si noti che, quando si esegue il programma, non sempre le attività finiscono nell'ordine in cui sono state create e messe in attesa.</span><span class="sxs-lookup"><span data-stu-id="6916b-110">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="6916b-111">Vengono avviate al momento della creazione ed è possibile che una o più di una finiscano prima che il metodo raggiunga le espressioni await.</span><span class="sxs-lookup"><span data-stu-id="6916b-111">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6916b-112">Per completare il progetto, è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="6916b-112">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>  
  
 <span data-ttu-id="6916b-113">Per un altro esempio che avvii più operazioni contemporaneamente, vedere [procedura: estendere la Async Walkthrough usando Task. whenall (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="6916b-113">For another example that starts multiple tasks at the same time, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="6916b-114">È possibile scaricare il codice per l'esempio da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e) (Esempi di codice per sviluppatori).</span><span class="sxs-lookup"><span data-stu-id="6916b-114">You can download the code for this example from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span></span>  
  
### <a name="to-set-up-the-project"></a><span data-ttu-id="6916b-115">Per impostare il progetto</span><span class="sxs-lookup"><span data-stu-id="6916b-115">To set up the project</span></span>  
  
1.  <span data-ttu-id="6916b-116">Per configurare un'applicazione WPF, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="6916b-116">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="6916b-117">È possibile trovare istruzioni dettagliate per le procedure descritte nel [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="6916b-117">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="6916b-118">Creare un'applicazione WPF che contenga una casella di testo e un pulsante.</span><span class="sxs-lookup"><span data-stu-id="6916b-118">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="6916b-119">Denominare il pulsante `startButton` e la casella di testo `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="6916b-119">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="6916b-120">Aggiunge un riferimento a <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="6916b-120">Add a reference for <xref:System.Net.Http>.</span></span>  
  
    -   <span data-ttu-id="6916b-121">Nel file XAML. vb, aggiungere un' `Imports` istruzione per `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="6916b-121">In the MainWindow.xaml.vb file, add an `Imports` statement for `System.Net.Http`.</span></span>  
  
### <a name="to-add-the-code"></a><span data-ttu-id="6916b-122">Per aggiungere il codice</span><span class="sxs-lookup"><span data-stu-id="6916b-122">To add the code</span></span>  
  
1.  <span data-ttu-id="6916b-123">Nella finestra di progettazione MainWindow. XAML fare doppio clic sul pulsante per creare il `startButton_Click` gestore dell'evento in XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="6916b-123">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="6916b-124">Copiare il codice seguente e incollarlo nel corpo di `startButton_Click` in XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="6916b-124">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.vb.</span></span>  
  
    ```vb  
    resultsTextBox.Clear()  
    Await CreateMultipleTasksAsync()  
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    ```  
  
     <span data-ttu-id="6916b-125">Il codice chiama un metodo asincrono, `CreateMultipleTasksAsync`, che avvia l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6916b-125">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>  
  
3.  <span data-ttu-id="6916b-126">Aggiungere i metodi di supporto seguenti al progetto:</span><span class="sxs-lookup"><span data-stu-id="6916b-126">Add the following support methods to the project:</span></span>  
  
    -   <span data-ttu-id="6916b-127">`ProcessURLAsync` usa un metodo <xref:System.Net.Http.HttpClient> per scaricare il contenuto di un sito Web come matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="6916b-127">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="6916b-128">Il metodo di supporto `ProcessURLAsync` visualizza e restituisce la lunghezza della matrice.</span><span class="sxs-lookup"><span data-stu-id="6916b-128">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>  
  
    -   <span data-ttu-id="6916b-129">`DisplayResults` visualizza il numero di byte della matrice di byte per ogni URL.</span><span class="sxs-lookup"><span data-stu-id="6916b-129">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="6916b-130">Questa visualizzazione indica quando ogni attività ha terminato il download.</span><span class="sxs-lookup"><span data-stu-id="6916b-130">This display shows when each task has finished downloading.</span></span>  
  
     <span data-ttu-id="6916b-131">Copiare i metodi seguenti e incollarli dopo il `startButton_Click` gestore dell'evento in XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="6916b-131">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "https://".  
        Dim displayURL = url.Replace("https://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
4.  <span data-ttu-id="6916b-132">Infine, definire il metodo `CreateMultipleTasksAsync`, che esegue i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="6916b-132">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>  
  
    -   <span data-ttu-id="6916b-133">Il metodo dichiara un oggetto `HttpClient`, che è necessario per accedere al metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="6916b-133">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>  
  
    -   <span data-ttu-id="6916b-134">Il metodo crea e avvia tre attività di tipo <xref:System.Threading.Tasks.Task%601>, dove `TResult` è un numero intero.</span><span class="sxs-lookup"><span data-stu-id="6916b-134">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="6916b-135">Al termine di ogni attività, `DisplayResults` vengono visualizzati l'URL dell'attività e la lunghezza del contenuto scaricato.</span><span class="sxs-lookup"><span data-stu-id="6916b-135">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="6916b-136">Poiché le attività sono in esecuzione in modo asincrono, l'ordine in cui vengono visualizzati i risultati potrebbe essere diverso da quello in cui le attività sono stati dichiarate.</span><span class="sxs-lookup"><span data-stu-id="6916b-136">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>  
  
    -   <span data-ttu-id="6916b-137">Il metodo attende il completamento di ogni attività.</span><span class="sxs-lookup"><span data-stu-id="6916b-137">The method awaits the completion of each task.</span></span> <span data-ttu-id="6916b-138">Ogni operatore `Await` sospende l'esecuzione di `CreateMultipleTasksAsync` finché non viene completata l'attività in attesa.</span><span class="sxs-lookup"><span data-stu-id="6916b-138">Each `Await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="6916b-139">L'operatore recupera anche il valore restituito dalla chiamata a `ProcessURLAsync` da ogni attività completata.</span><span class="sxs-lookup"><span data-stu-id="6916b-139">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>  
  
    -   <span data-ttu-id="6916b-140">Quando sono state completate le attività e sono stati recuperati i valori interi, il metodo somma le lunghezze dei siti Web e visualizza il risultato.</span><span class="sxs-lookup"><span data-stu-id="6916b-140">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>  
  
     <span data-ttu-id="6916b-141">Copiare il metodo seguente e incollarlo nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="6916b-141">Copy the following method, and paste it into your solution.</span></span>  
  
    ```vb  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("https://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
    ```  
  
5.  <span data-ttu-id="6916b-142">Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .</span><span class="sxs-lookup"><span data-stu-id="6916b-142">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="6916b-143">Eseguire il programma più volte per verificare che le tre attività non vengano completate sempre nello stesso ordine e che l'ordine in cui vengono completate non è necessariamente l'ordine in cui sono state create e messe in attesa.</span><span class="sxs-lookup"><span data-stu-id="6916b-143">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6916b-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="6916b-144">Example</span></span>  
 <span data-ttu-id="6916b-145">Il codice seguente contiene l'esempio completo.</span><span class="sxs-lookup"><span data-stu-id="6916b-145">The following code contains the full example.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
        resultsTextBox.Clear()  
        Await CreateMultipleTasksAsync()  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("https://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "https://".  
        Dim displayURL = url.Replace("https://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="6916b-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6916b-146">See Also</span></span>  
 [<span data-ttu-id="6916b-147">Procedura dettagliata: Accesso al Web con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6916b-147">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="6916b-148">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6916b-148">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="6916b-149">Procedura: Estendere la procedura dettagliata asincrona tramite Task.WhenAll (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6916b-149">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
