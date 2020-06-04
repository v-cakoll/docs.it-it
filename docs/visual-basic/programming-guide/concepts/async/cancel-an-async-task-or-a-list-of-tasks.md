---
title: Annullare un'attività asincrona o un elenco di attività
ms.date: 07/20/2015
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
ms.openlocfilehash: 932bf46f1e3aee220d0412f1688e961faaef3459
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396701"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a><span data-ttu-id="fe91d-102">Annullare un'attività asincrona o un elenco di attività (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe91d-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>

<span data-ttu-id="fe91d-103">È possibile impostare un pulsante che consenta di annullare un'applicazione asincrona se non si vuole attendere il suo completamento.</span><span class="sxs-lookup"><span data-stu-id="fe91d-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="fe91d-104">Seguendo gli esempi in questo argomento, è possibile aggiungere un pulsante di annullamento di un'applicazione che scarica il contenuto di un sito Web o di un elenco di siti Web.</span><span class="sxs-lookup"><span data-stu-id="fe91d-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>

<span data-ttu-id="fe91d-105">Negli esempi viene usata l'interfaccia utente che consente di [ottimizzare l'applicazione asincrona (Visual Basic)](fine-tuning-your-async-application.md) .</span><span class="sxs-lookup"><span data-stu-id="fe91d-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) describes.</span></span>

> [!NOTE]
> <span data-ttu-id="fe91d-106">Per eseguire gli esempi, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.</span><span class="sxs-lookup"><span data-stu-id="fe91d-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="cancel-a-task"></a><a name="BKMK_CancelaTask"></a> <span data-ttu-id="fe91d-107">Annullare un'attività</span><span class="sxs-lookup"><span data-stu-id="fe91d-107">Cancel a Task</span></span>

<span data-ttu-id="fe91d-108">Il primo esempio associa il pulsante **Annulla** con un'attività di download singola.</span><span class="sxs-lookup"><span data-stu-id="fe91d-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="fe91d-109">Se si sceglie il pulsante mentre l'applicazione sta scaricando il contenuto, il download viene annullato.</span><span class="sxs-lookup"><span data-stu-id="fe91d-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>

### <a name="downloading-the-example"></a><span data-ttu-id="fe91d-110">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="fe91d-110">Downloading the Example</span></span>

<span data-ttu-id="fe91d-111">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="fe91d-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="fe91d-112">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fe91d-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="fe91d-113">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="fe91d-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="fe91d-114">Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (con estensione sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="fe91d-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="fe91d-115">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelATask** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="fe91d-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="fe91d-116">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="fe91d-116">Choose the F5 key to run the project.</span></span>

     <span data-ttu-id="fe91d-117">Premere CTRL + F5 per eseguire il progetto senza il debug.</span><span class="sxs-lookup"><span data-stu-id="fe91d-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

 <span data-ttu-id="fe91d-118">Se non si vuole scaricare il progetto, è possibile esaminare i file MainWindow. XAML. VB alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fe91d-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>

### <a name="building-the-example"></a><span data-ttu-id="fe91d-119">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="fe91d-119">Building the Example</span></span>

<span data-ttu-id="fe91d-120">Le modifiche seguenti aggiungono un pulsante **Annulla** a un'applicazione che scarica un sito Web.</span><span class="sxs-lookup"><span data-stu-id="fe91d-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="fe91d-121">Se non si vuole scaricare o compilare l'esempio, è possibile rivedere il prodotto finale nella sezione "Esempi completi" alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fe91d-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="fe91d-122">Gli asterischi contrassegnano le modifiche nel codice.</span><span class="sxs-lookup"><span data-stu-id="fe91d-122">Asterisks mark the changes in the code.</span></span>

<span data-ttu-id="fe91d-123">Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **StarterCode** come **progetto di avvio** anziché **CancelATask**.</span><span class="sxs-lookup"><span data-stu-id="fe91d-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>

<span data-ttu-id="fe91d-124">Aggiungere quindi le seguenti modifiche al file MainWindow. XAML. vb del progetto.</span><span class="sxs-lookup"><span data-stu-id="fe91d-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span></span>

1. <span data-ttu-id="fe91d-125">Dichiarare una variabile `CancellationTokenSource`, `cts`, che sia nell'ambito di accesso di tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="fe91d-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>

    ```vb
    Class MainWindow

        ' ***Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. <span data-ttu-id="fe91d-126">Aggiungere il gestore eventi seguente per il pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="fe91d-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="fe91d-127">Il gestore dell'evento usa il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> per inviare notifica a `cts` quando l'utente richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="fe91d-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method to notify `cts` when the user requests cancellation.</span></span>

    ```vb
    ' ***Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub
    ```

3. <span data-ttu-id="fe91d-128">Apportare le modifiche seguenti nel gestore eventi per il pulsante **Avvio**, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="fe91d-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>

    - <span data-ttu-id="fe91d-129">Creare un'istanza di `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="fe91d-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>

      ```vb
      ' ***Instantiate the CancellationTokenSource.
      cts = New CancellationTokenSource()
      ```

    - <span data-ttu-id="fe91d-130">Nella chiamata a `AccessTheWebAsync`, che scarica il contenuto di un sito Web specifico, inviare la proprietà <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> di `cts` come argomento.</span><span class="sxs-lookup"><span data-stu-id="fe91d-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> property of `cts` as an argument.</span></span> <span data-ttu-id="fe91d-131">La proprietà `Token` propaga il messaggio se viene richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="fe91d-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="fe91d-132">Aggiungere un blocco catch che visualizzi un messaggio se l'utente sceglie di annullare l'operazione di download.</span><span class="sxs-lookup"><span data-stu-id="fe91d-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="fe91d-133">Il codice seguente illustra le modifiche.</span><span class="sxs-lookup"><span data-stu-id="fe91d-133">The following code shows the changes.</span></span>

      ```vb
      Try
          ' ***Send a token to carry the message if cancellation is requested.
          Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)

          resultsTextBox.Text &=
              vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

          ' *** If cancellation is requested, an OperationCanceledException results.
      Catch ex As OperationCanceledException
          resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

      Catch ex As Exception
          resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
      End Try
      ```

4. <span data-ttu-id="fe91d-134">In `AccessTheWebAsync` usare l'overload <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> del metodo `GetAsync` nel tipo <xref:System.Net.Http.HttpClient> per scaricare il contenuto di un sito Web.</span><span class="sxs-lookup"><span data-stu-id="fe91d-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="fe91d-135">Passare `ct`, il parametro <xref:System.Threading.CancellationToken> di `AccessTheWebAsync`, come secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="fe91d-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="fe91d-136">Il token trasporta il messaggio se l'utente sceglie il pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="fe91d-136">The token carries the message if the user chooses the **Cancel** button.</span></span>

    <span data-ttu-id="fe91d-137">Il codice seguente illustra tutte le modifiche in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="fe91d-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>

    ```vb
    ' ***Provide a parameter for the CancellationToken.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)

        Dim client As HttpClient = New HttpClient()

        resultsTextBox.Text &= vbCrLf & "Ready to download." & vbCrLf

        ' You might need to slow things down to have a chance to cancel.
        Await Task.Delay(250)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' ***The ct argument carries the message if the Cancel button is chosen.
        Dim response As HttpResponseMessage = Await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' The result of the method is the length of the downloaded website.
        Return urlContents.Length
    End Function
    ```

5. <span data-ttu-id="fe91d-138">Se non si annulla il programma, viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="fe91d-138">If you don’t cancel the program, it produces the following output:</span></span>

    ```console
    Ready to download.
    Length of the downloaded string: 158125.
    ```

    <span data-ttu-id="fe91d-139">Se si sceglie il pulsante **Annulla** prima che il programma completi il download del contenuto, il programma produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="fe91d-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output:</span></span>

    ```console
    Ready to download.
    Download canceled.
    ```

## <a name="cancel-a-list-of-tasks"></a><a name="BKMK_CancelaListofTasks"></a> <span data-ttu-id="fe91d-140">Annullare un elenco di attività</span><span class="sxs-lookup"><span data-stu-id="fe91d-140">Cancel a List of Tasks</span></span>

<span data-ttu-id="fe91d-141">È possibile estendere l'esempio precedente per annullare più attività associando la stessa istanza `CancellationTokenSource` con ogni attività.</span><span class="sxs-lookup"><span data-stu-id="fe91d-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="fe91d-142">Se si sceglie il pulsante **Annulla**, vengono annullate tutte le attività che non sono ancora complete.</span><span class="sxs-lookup"><span data-stu-id="fe91d-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>

### <a name="downloading-the-example"></a><span data-ttu-id="fe91d-143">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="fe91d-143">Downloading the Example</span></span>

<span data-ttu-id="fe91d-144">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="fe91d-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="fe91d-145">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fe91d-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="fe91d-146">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="fe91d-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="fe91d-147">Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (con estensione sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="fe91d-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="fe91d-148">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelAListOfTasks** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="fe91d-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="fe91d-149">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="fe91d-149">Choose the F5 key to run the project.</span></span>

     <span data-ttu-id="fe91d-150">Premere CTRL + F5 per eseguire il progetto senza il debug.</span><span class="sxs-lookup"><span data-stu-id="fe91d-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

 <span data-ttu-id="fe91d-151">Se non si vuole scaricare il progetto, è possibile esaminare i file MainWindow. XAML. VB alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fe91d-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>

### <a name="building-the-example"></a><span data-ttu-id="fe91d-152">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="fe91d-152">Building the Example</span></span>

<span data-ttu-id="fe91d-153">Per estendere l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **CancelATask** come **progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="fe91d-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="fe91d-154">Aggiungere le modifiche seguenti a tale progetto.</span><span class="sxs-lookup"><span data-stu-id="fe91d-154">Add the following changes to that project.</span></span> <span data-ttu-id="fe91d-155">Gli asterischi contrassegnano le modifiche nel programma.</span><span class="sxs-lookup"><span data-stu-id="fe91d-155">Asterisks mark the changes in the program.</span></span>

1. <span data-ttu-id="fe91d-156">Aggiungere un metodo per creare un elenco di indirizzi Web.</span><span class="sxs-lookup"><span data-stu-id="fe91d-156">Add a method to create a list of web addresses.</span></span>

    ```vb
    ' ***Add a method that creates a list of web addresses.
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
    ```

2. <span data-ttu-id="fe91d-157">Chiamare il metodo in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="fe91d-157">Call the method in `AccessTheWebAsync`.</span></span>

    ```vb
    ' ***Call SetUpURLList to make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()
    ```

3. <span data-ttu-id="fe91d-158">Aggiungere il ciclo seguente in `AccessTheWebAsync` per elaborare gli indirizzi Web nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fe91d-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>

    ```vb
    ' ***Add a loop to process the list of web addresses.
    For Each url In urlList
        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' Argument ct carries the message if the Cancel button is chosen.
        ' ***Note that the Cancel button can cancel all remaining downloads.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        resultsTextBox.Text &=
            vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
    Next
    ```

4. <span data-ttu-id="fe91d-159">Poiché `AccessTheWebAsync` visualizza le lunghezze, il metodo non deve restituire nessun valore.</span><span class="sxs-lookup"><span data-stu-id="fe91d-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="fe91d-160">Rimuovere l'istruzione return e modificare il tipo restituito del metodo in <xref:System.Threading.Tasks.Task> anziché <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="fe91d-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>

    ```vb
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task
    ```

    <span data-ttu-id="fe91d-161">Chiamare il metodo da `startButton_Click` usando un'istruzione anziché un'espressione.</span><span class="sxs-lookup"><span data-stu-id="fe91d-161">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>

    ```vb
    Await AccessTheWebAsync(cts.Token)
    ```

5. <span data-ttu-id="fe91d-162">Se non si annulla il programma, viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="fe91d-162">If you don’t cancel the program, it produces the following output:</span></span>

    ```console
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

    <span data-ttu-id="fe91d-163">Se si sceglie il pulsante **Annulla** prima di aver completato i download, l'output contiene le lunghezze dei download completati prima dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="fe91d-163">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>

    ```console
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="complete-examples"></a><a name="BKMK_CompleteExamples"></a> <span data-ttu-id="fe91d-164">Esempi completi</span><span class="sxs-lookup"><span data-stu-id="fe91d-164">Complete Examples</span></span>

<span data-ttu-id="fe91d-165">Le sezioni seguenti contengono il codice per ognuno degli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="fe91d-165">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="fe91d-166">Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="fe91d-166">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="fe91d-167">È possibile scaricare i progetti da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="fe91d-167">You can download the projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

### <a name="cancel-a-task-example"></a><span data-ttu-id="fe91d-168">Esempio di annullamento di un'attività</span><span class="sxs-lookup"><span data-stu-id="fe91d-168">Cancel a Task Example</span></span>

<span data-ttu-id="fe91d-169">Il codice seguente è il file MainWindow. XAML. vb completo per l'esempio che annulla una singola attività.</span><span class="sxs-lookup"><span data-stu-id="fe91d-169">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span></span>

```vb
' Add an Imports directive and a reference for System.Net.Http.
Imports System.Net.Http

' Add the following Imports directive for System.Threading.
Imports System.Threading

Class MainWindow

    ' ***Declare a System.Threading.CancellationTokenSource.
    Dim cts As CancellationTokenSource

    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)
        ' ***Instantiate the CancellationTokenSource.
        cts = New CancellationTokenSource()

        resultsTextBox.Clear()

        Try
            ' ***Send a token to carry the message if cancellation is requested.
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

            ' *** If cancellation is requested, an OperationCanceledException results.
        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
        End Try

        ' ***Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' ***Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' ***Provide a parameter for the CancellationToken.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)

        Dim client As HttpClient = New HttpClient()

        resultsTextBox.Text &=
            vbCrLf & "Ready to download." & vbCrLf

        ' You might need to slow things down to have a chance to cancel.
        Await Task.Delay(250)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' ***The ct argument carries the message if the Cancel button is chosen.
        Dim response As HttpResponseMessage = Await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' The result of the method is the length of the downloaded website.
        Return urlContents.Length
    End Function
End Class

' Output for a successful download:

' Ready to download.

' Length of the downloaded string: 158125.

' Or, if you cancel:

' Ready to download.

' Download canceled.
```

### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="fe91d-170">Esempio di annullamento di un elenco di attività</span><span class="sxs-lookup"><span data-stu-id="fe91d-170">Cancel a List of Tasks Example</span></span>

<span data-ttu-id="fe91d-171">Il codice seguente è il file MainWindow. XAML. vb completo per l'esempio che annulla un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="fe91d-171">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span></span>

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
            ' ***AccessTheWebAsync returns a Task, not a Task(Of Integer).
            Await AccessTheWebAsync(cts.Token)
            '  ***Small change in the display lines.
            resultsTextBox.Text &= vbCrLf & "Downloads complete."

        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf
        End Try

        ' Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' Provide a parameter for the CancellationToken.
    ' ***Change the return type to Task because the method has no return statement.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task

        Dim client As HttpClient = New HttpClient()

        ' ***Call SetUpURLList to make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' ***Add a loop to process the list of web addresses.
        For Each url In urlList
            ' GetAsync returns a Task(Of HttpResponseMessage).
            ' Argument ct carries the message if the Cancel button is chosen.
            ' ***Note that the Cancel button can cancel all remaining downloads.
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

            ' Retrieve the website contents from the HttpResponseMessage.
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        Next
    End Function

    ' ***Add a method that creates a list of web addresses.
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

' Output if you do not choose to cancel:

' Length of the downloaded string: 35939.

' Length of the downloaded string: 237682.

' Length of the downloaded string: 128607.

' Length of the downloaded string: 158124.

' Length of the downloaded string: 204890.

' Length of the downloaded string: 175488.

' Length of the downloaded string: 145790.

' Downloads complete.

'  Sample output if you choose to cancel:

' Length of the downloaded string: 35939.

' Length of the downloaded string: 237682.

' Length of the downloaded string: 128607.

' Downloads canceled.
```

## <a name="see-also"></a><span data-ttu-id="fe91d-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe91d-172">See also</span></span>

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [<span data-ttu-id="fe91d-173">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe91d-173">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="fe91d-174">Ottimizzazione dell'applicazione Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe91d-174">Fine-Tuning Your Async Application (Visual Basic)</span></span>](fine-tuning-your-async-application.md)
- <span data-ttu-id="fe91d-175">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="fe91d-175">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
