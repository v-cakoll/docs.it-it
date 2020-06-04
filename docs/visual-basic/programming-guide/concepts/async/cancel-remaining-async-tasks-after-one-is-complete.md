---
title: Annullare le attività asincrone rimanenti dopo che ne è stata completata una
ms.date: 07/20/2015
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
ms.openlocfilehash: be716e98263c865adad3c197236467b2f48d7740
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396675"
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a><span data-ttu-id="ff6f1-102">Annullare le attività asincrone rimanenti dopo che ne è stata completata una(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff6f1-102">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>

<span data-ttu-id="ff6f1-103">È possibile usare il metodo <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> insieme a <xref:System.Threading.CancellationToken> per annullare tutte le attività rimanenti dopo il completamento di un'attività.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-103">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="ff6f1-104">Il metodo `WhenAny` accetta un argomento che rappresenta una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-104">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="ff6f1-105">Il metodo avvia tutte le attività e restituisce una singola attività.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-105">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="ff6f1-106">La singola attività è completa quando una qualsiasi attività nella raccolta è completata.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-106">The single task is complete when any task in the collection is complete.</span></span>

<span data-ttu-id="ff6f1-107">Questo esempio illustra come usare un token di annullamento in combinazione con `WhenAny` per terminare il completamento della prima attività della raccolta di attività e annullare le rimanenti attività.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-107">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="ff6f1-108">Ogni attività scarica il contenuto di un sito Web.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-108">Each task downloads the contents of a website.</span></span> <span data-ttu-id="ff6f1-109">L'esempio visualizza la lunghezza del contenuto del primo download da completare e annulla gli altri download.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-109">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>

> [!NOTE]
> <span data-ttu-id="ff6f1-110">Per eseguire gli esempi, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-110">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="downloading-the-example"></a><span data-ttu-id="ff6f1-111">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="ff6f1-111">Downloading the Example</span></span>

<span data-ttu-id="ff6f1-112">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-112">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="ff6f1-113">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-113">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="ff6f1-114">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-114">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="ff6f1-115">Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (con estensione sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-115">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="ff6f1-116">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelAfterOneTask** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-116">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="ff6f1-117">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-117">Choose the F5 key to run the project.</span></span>

    <span data-ttu-id="ff6f1-118">Premere CTRL + F5 per eseguire il progetto senza il debug.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-118">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

6. <span data-ttu-id="ff6f1-119">Eseguire il programma più volte per verificare che diversi download terminino prima.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-119">Run the program several times to verify that different downloads finish first.</span></span>

<span data-ttu-id="ff6f1-120">Se non si vuole scaricare il progetto, è possibile esaminare il file MainWindow.xaml.vb alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-120">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>

## <a name="building-the-example"></a><span data-ttu-id="ff6f1-121">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="ff6f1-121">Building the Example</span></span>

<span data-ttu-id="ff6f1-122">Nell'esempio riportato in questo argomento viene aggiunto al progetto sviluppato in [annullare un'attività asincrona o un elenco di attività](cancel-an-async-task-or-a-list-of-tasks.md) per annullare un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-122">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks](cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="ff6f1-123">L'esempio usa la stessa interfaccia utente, sebbene il pulsante **Annulla** non viene usato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-123">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>

<span data-ttu-id="ff6f1-124">Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **CancelAListOfTasks** come **progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="ff6f1-125">Aggiungere al progetto le modifiche illustrate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-125">Add the changes in this topic to that project.</span></span>

<span data-ttu-id="ff6f1-126">Nel file MainWindow. XAML. vb del progetto **CancelAListOfTasks** avviare la transizione spostando i passaggi di elaborazione per ogni sito Web dal ciclo in `AccessTheWebAsync` al seguente metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-126">In the MainWindow.xaml.vb file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>

```vb
' ***Bundle the processing steps for a website into one async method.
Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)

    ' GetAsync returns a Task(Of HttpResponseMessage).
    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

    ' Retrieve the website contents from the HttpResponseMessage.
    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

    Return urlContents.Length
End Function
```

<span data-ttu-id="ff6f1-127">In `AccessTheWebAsync`, questo esempio usa una query, il metodo <xref:System.Linq.Enumerable.ToArray%2A> e il metodo `WhenAny` per creare e avviare una matrice di attività.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-127">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="ff6f1-128">L'applicazione di `WhenAny` alla matrice restituisce una singola attività che, quando attesa, restituisce la prima attività per raggiungere il completamento della matrice di attività.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-128">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>

<span data-ttu-id="ff6f1-129">Modificare `AccessTheWebAsync` nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-129">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="ff6f1-130">Gli asterischi contrassegnano le modifiche nel file del codice.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-130">Asterisks mark the changes in the code file.</span></span>

1. <span data-ttu-id="ff6f1-131">Aggiungere un commento o eliminare il ciclo.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-131">Comment out or delete the loop.</span></span>

2. <span data-ttu-id="ff6f1-132">Creare una query che, quando eseguita, produce una raccolta di attività generiche.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-132">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="ff6f1-133">Ogni chiamata a `ProcessURLAsync` restituisce un oggetto <xref:System.Threading.Tasks.Task%601> dove `TResult` è un numero intero.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-133">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>

    ```vb
    ' ***Create a query that, when executed, returns a collection of tasks.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client, ct)
    ```

3. <span data-ttu-id="ff6f1-134">Chiamare `ToArray` per eseguire la query e avviare le attività.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-134">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="ff6f1-135">L'applicazione del metodo `WhenAny` nel passaggio successivo esegue la query e avvia le attività senza usare `ToArray`, ma altri metodi non farebbero lo stesso.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-135">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="ff6f1-136">La procedura più sicura consiste nel forzare l'esecuzione della query in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-136">The safest practice is to force execution of the query explicitly.</span></span>

    ```vb
    ' ***Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. <span data-ttu-id="ff6f1-137">Chiamare `WhenAny` sulla raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-137">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="ff6f1-138">`WhenAny` restituisce `Task(Of Task(Of Integer))` o `Task<Task<int>>`.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-138">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="ff6f1-139">Ovvero `WhenAny` restituisce un'attività che include un singolo `Task(Of Integer)` o `Task<int>` quando è attesa.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-139">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="ff6f1-140">L'attività singola è la prima attività della raccolta da completare.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-140">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="ff6f1-141">L'attività completata per prima viene assegnata a `firstFinishedTask`.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-141">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="ff6f1-142">Il tipo di `firstFinishedTask` è <xref:System.Threading.Tasks.Task%601> dove `TResult` è un numero intero perché è il tipo restituito di `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-142">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>

    ```vb
    ' ***Call WhenAny and then await the result. The task that finishes
    ' first is assigned to firstFinishedTask.
    Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)
    ```

5. <span data-ttu-id="ff6f1-143">In questo esempio, si è interessati solo all'attività che termina per prima.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-143">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="ff6f1-144">Usare quindi <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> per annullare le attività rimanenti.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-144">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> to cancel the remaining tasks.</span></span>

    ```vb
    ' ***Cancel the rest of the downloads. You just want the first one.
    cts.Cancel()
    ```

6. <span data-ttu-id="ff6f1-145">Infine, attendere `firstFinishedTask` per recuperare la lunghezza del contenuto scaricato.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-145">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>

    ```vb
    Dim length = Await firstFinishedTask
    resultsTextBox.Text &= vbCrLf & $"Length of the downloaded website:  {length}" & vbCrLf
    ```

<span data-ttu-id="ff6f1-146">Eseguire il programma più volte per verificare che diversi download terminino prima.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-146">Run the program several times to verify that different downloads finish first.</span></span>

## <a name="complete-example"></a><span data-ttu-id="ff6f1-147">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="ff6f1-147">Complete Example</span></span>

<span data-ttu-id="ff6f1-148">Il codice seguente è il file MainWindow. XAML. vb o MainWindow.xaml.cs completo per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-148">The following code is the complete MainWindow.xaml.vb or MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="ff6f1-149">Gli asterischi contrassegnano gli elementi che sono stati aggiunti per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-149">Asterisks mark the elements that were added for this example.</span></span>

<span data-ttu-id="ff6f1-150">Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="ff6f1-150">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="ff6f1-151">È possibile scaricare il progetto da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="ff6f1-151">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

```vb
' Add an Imports directive and a reference for System.Net.Http.
Imports System.Net.Http

' Add the following Imports directive for System.Threading.
Imports System.Threading

Class MainWindow

    ' Declare a System.Threading.CancellationTokenSource.
    Dim cts As CancellationTokenSource

    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)

        ' Instantiate the CancellationTokenSource.
        cts = New CancellationTokenSource()

        resultsTextBox.Clear()

        Try
            Await AccessTheWebAsync(cts.Token)
            resultsTextBox.Text &= vbCrLf & "Download complete."

        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
        End Try

        ' Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' You can still include a Cancel button if you want to.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' Provide a parameter for the CancellationToken.
    ' Change the return type to Task because the method has no return statement.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task

        Dim client As HttpClient = New HttpClient()

        ' Call SetUpURLList to make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        '' Comment out or delete the loop.
        ''For Each url In urlList
        ''    ' GetAsync returns a Task(Of HttpResponseMessage).
        ''    ' Argument ct carries the message if the Cancel button is chosen.
        ''    ' Note that the Cancel button can cancel all remaining downloads.
        ''    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ''    ' Retrieve the website contents from the HttpResponseMessage.
        ''    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ''    resultsTextBox.Text &=
        ''        vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        ''Next

        ' ***Create a query that, when executed, returns a collection of tasks.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url, client, ct)

        ' ***Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' ***Call WhenAny and then await the result. The task that finishes
        ' first is assigned to firstFinishedTask.
        Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)

        ' ***Cancel the rest of the downloads. You just want the first one.
        cts.Cancel()

        ' ***Await the first completed task and display the results
        ' Run the program several times to demonstrate that different
        ' websites can finish first.
        Dim length = Await firstFinishedTask
        resultsTextBox.Text &= vbCrLf & $"Length of the downloaded website:  {length}" & vbCrLf
    End Function

    ' ***Bundle the processing steps for a website into one async method.
    Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        Return urlContents.Length
    End Function

    ' Add a method that creates a list of web addresses.
    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

End Class

' Sample output:

' Length of the downloaded website:  158856

' Download complete.
```

## <a name="see-also"></a><span data-ttu-id="ff6f1-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff6f1-152">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="ff6f1-153">Ottimizzazione dell'applicazione Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff6f1-153">Fine-Tuning Your Async Application (Visual Basic)</span></span>](fine-tuning-your-async-application.md)
- [<span data-ttu-id="ff6f1-154">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff6f1-154">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- <span data-ttu-id="ff6f1-155">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="ff6f1-155">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
