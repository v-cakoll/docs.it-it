---
title: "Annullare un'attività asincrona o un elenco di attività (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 916577107bd65559aed71dc9bb2921969a117e90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a><span data-ttu-id="c7c35-102">Annullare un'attività asincrona o un elenco di attività (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7c35-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>
<span data-ttu-id="c7c35-103">È possibile impostare un pulsante che consenta di annullare un'applicazione asincrona se non si vuole attendere il suo completamento.</span><span class="sxs-lookup"><span data-stu-id="c7c35-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="c7c35-104">Seguendo gli esempi in questo argomento, è possibile aggiungere un pulsante di annullamento di un'applicazione che scarica il contenuto di un sito Web o di un elenco di siti Web.</span><span class="sxs-lookup"><span data-stu-id="c7c35-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>  
  
 <span data-ttu-id="c7c35-105">Negli esempi viene utilizzato l'interfaccia utente che [ottimizzazione Async applicazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) descrive.</span><span class="sxs-lookup"><span data-stu-id="c7c35-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7c35-106">Per eseguire gli esempi, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.</span><span class="sxs-lookup"><span data-stu-id="c7c35-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <a name="BKMK_CancelaTask"></a> <span data-ttu-id="c7c35-107">Annullare un'attività</span><span class="sxs-lookup"><span data-stu-id="c7c35-107">Cancel a Task</span></span>  
 <span data-ttu-id="c7c35-108">Il primo esempio associa il pulsante **Annulla** con un'attività di download singola.</span><span class="sxs-lookup"><span data-stu-id="c7c35-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="c7c35-109">Se si sceglie il pulsante mentre l'applicazione sta scaricando il contenuto, il download viene annullato.</span><span class="sxs-lookup"><span data-stu-id="c7c35-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="c7c35-110">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="c7c35-110">Downloading the Example</span></span>  
 <span data-ttu-id="c7c35-111">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="c7c35-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="c7c35-112">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c7c35-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="c7c35-113">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="c7c35-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="c7c35-114">Nel **Apri progetto** la finestra di dialogo, aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="c7c35-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="c7c35-115">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelATask** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="c7c35-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="c7c35-116">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="c7c35-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="c7c35-117">Premere CTRL + F5 per eseguire il progetto senza il debug.</span><span class="sxs-lookup"><span data-stu-id="c7c35-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="c7c35-118">Se non si desidera scaricare il progetto, è possibile esaminare i file. Xaml. vb alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c7c35-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="c7c35-119">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="c7c35-119">Building the Example</span></span>  
 <span data-ttu-id="c7c35-120">Le modifiche seguenti aggiungono un pulsante **Annulla** a un'applicazione che scarica un sito Web.</span><span class="sxs-lookup"><span data-stu-id="c7c35-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="c7c35-121">Se non si vuole scaricare o compilare l'esempio, è possibile rivedere il prodotto finale nella sezione "Esempi completi" alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c7c35-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="c7c35-122">Gli asterischi contrassegnano le modifiche nel codice.</span><span class="sxs-lookup"><span data-stu-id="c7c35-122">Asterisks mark the changes in the code.</span></span>  
  
 <span data-ttu-id="c7c35-123">Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **StarterCode** come **progetto di avvio** anziché **CancelATask**.</span><span class="sxs-lookup"><span data-stu-id="c7c35-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>  
  
 <span data-ttu-id="c7c35-124">Aggiungere quindi le modifiche seguenti al file. Xaml. vb del progetto.</span><span class="sxs-lookup"><span data-stu-id="c7c35-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span></span>  
  
1.  <span data-ttu-id="c7c35-125">Dichiarare una variabile `CancellationTokenSource`, `cts`, che sia nell'ambito di accesso di tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="c7c35-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' ***Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  <span data-ttu-id="c7c35-126">Aggiungere il gestore eventi seguente per il pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="c7c35-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="c7c35-127">Il gestore dell'evento usa il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> per inviare notifica a `cts` quando l'utente richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="c7c35-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method to notify `cts` when the user requests cancellation.</span></span>  
  
    ```vb  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
    ```  
  
3.  <span data-ttu-id="c7c35-128">Apportare le modifiche seguenti nel gestore eventi per il pulsante **Avvio**, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="c7c35-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>  
  
    -   <span data-ttu-id="c7c35-129">Creare un'istanza di `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="c7c35-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>  
  
        ```vb  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
        ```  
  
    -   <span data-ttu-id="c7c35-130">Nella chiamata a `AccessTheWebAsync`, che scarica il contenuto di un sito Web specifico, inviare la proprietà <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> di `cts` come argomento.</span><span class="sxs-lookup"><span data-stu-id="c7c35-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> property of `cts` as an argument.</span></span> <span data-ttu-id="c7c35-131">La proprietà `Token` propaga il messaggio se viene richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="c7c35-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="c7c35-132">Aggiungere un blocco catch che visualizzi un messaggio se l'utente sceglie di annullare l'operazione di download.</span><span class="sxs-lookup"><span data-stu-id="c7c35-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="c7c35-133">Il codice seguente illustra le modifiche.</span><span class="sxs-lookup"><span data-stu-id="c7c35-133">The following code shows the changes.</span></span>  
  
        ```vb  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
        ```  
  
4.  <span data-ttu-id="c7c35-134">In `AccessTheWebAsync` usare l'overload <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> del metodo `GetAsync` nel tipo <xref:System.Net.Http.HttpClient> per scaricare il contenuto di un sito Web.</span><span class="sxs-lookup"><span data-stu-id="c7c35-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="c7c35-135">Passare `ct`, il parametro <xref:System.Threading.CancellationToken> di `AccessTheWebAsync`, come secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="c7c35-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="c7c35-136">Il token trasporta il messaggio se l'utente sceglie il pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="c7c35-136">The token carries the message if the user chooses the **Cancel** button.</span></span>  
  
     <span data-ttu-id="c7c35-137">Il codice seguente illustra tutte le modifiche in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="c7c35-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
    ```  
  
5.  <span data-ttu-id="c7c35-138">Se non si annulla il programma, viene prodotto l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="c7c35-138">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     <span data-ttu-id="c7c35-139">Se si sceglie il pulsante **Annulla** prima che il programma termini il download del contenuto, viene prodotto l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="c7c35-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <a name="BKMK_CancelaListofTasks"></a> <span data-ttu-id="c7c35-140">Annullare un elenco di attività</span><span class="sxs-lookup"><span data-stu-id="c7c35-140">Cancel a List of Tasks</span></span>  
 <span data-ttu-id="c7c35-141">È possibile estendere l'esempio precedente per annullare più attività associando la stessa istanza `CancellationTokenSource` con ogni attività.</span><span class="sxs-lookup"><span data-stu-id="c7c35-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="c7c35-142">Se si sceglie il pulsante **Annulla**, vengono annullate tutte le attività che non sono ancora complete.</span><span class="sxs-lookup"><span data-stu-id="c7c35-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="c7c35-143">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="c7c35-143">Downloading the Example</span></span>  
 <span data-ttu-id="c7c35-144">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="c7c35-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="c7c35-145">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c7c35-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="c7c35-146">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="c7c35-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="c7c35-147">Nel **Apri progetto** la finestra di dialogo, aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="c7c35-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="c7c35-148">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelAListOfTasks** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="c7c35-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="c7c35-149">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="c7c35-149">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="c7c35-150">Premere CTRL + F5 per eseguire il progetto senza il debug.</span><span class="sxs-lookup"><span data-stu-id="c7c35-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="c7c35-151">Se non si desidera scaricare il progetto, è possibile esaminare i file. Xaml. vb alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c7c35-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="c7c35-152">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="c7c35-152">Building the Example</span></span>  
 <span data-ttu-id="c7c35-153">Per estendere l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **CancelATask** come **progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="c7c35-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="c7c35-154">Aggiungere le modifiche seguenti a tale progetto.</span><span class="sxs-lookup"><span data-stu-id="c7c35-154">Add the following changes to that project.</span></span> <span data-ttu-id="c7c35-155">Gli asterischi contrassegnano le modifiche nel programma.</span><span class="sxs-lookup"><span data-stu-id="c7c35-155">Asterisks mark the changes in the program.</span></span>  
  
1.  <span data-ttu-id="c7c35-156">Aggiungere un metodo per creare un elenco di indirizzi Web.</span><span class="sxs-lookup"><span data-stu-id="c7c35-156">Add a method to create a list of web addresses.</span></span>  
  
    ```vb  
    ' ***Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
    ```  
  
2.  <span data-ttu-id="c7c35-157">Chiamare il metodo in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="c7c35-157">Call the method in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Call SetUpURLList to make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
    ```  
  
3.  <span data-ttu-id="c7c35-158">Aggiungere il ciclo seguente in `AccessTheWebAsync` per elaborare gli indirizzi Web nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c7c35-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>  
  
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
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
    Next  
    ```  
  
4.  <span data-ttu-id="c7c35-159">Poiché `AccessTheWebAsync` visualizza le lunghezze, il metodo non deve restituire nessun valore.</span><span class="sxs-lookup"><span data-stu-id="c7c35-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="c7c35-160">Rimuovere l'istruzione return e modificare il tipo restituito del metodo in <xref:System.Threading.Tasks.Task> anziché <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="c7c35-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
    ```vb  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
    ```  
  
     <span data-ttu-id="c7c35-161">Chiamare il metodo da `startButton_Click` usando un'istruzione anziché un'espressione.</span><span class="sxs-lookup"><span data-stu-id="c7c35-161">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>  
  
    ```vb  
    Await AccessTheWebAsync(cts.Token)  
    ```  
  
5.  <span data-ttu-id="c7c35-162">Se non si annulla il programma, viene prodotto l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="c7c35-162">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Length of the downloaded string: 158124.  
  
    Length of the downloaded string: 204890.  
  
    Length of the downloaded string: 175488.  
  
    Length of the downloaded string: 145790.  
  
    Downloads complete.  
    ```  
  
     <span data-ttu-id="c7c35-163">Se si sceglie il pulsante **Annulla** prima di aver completato i download, l'output contiene le lunghezze dei download completati prima dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="c7c35-163">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
    ```  
  
##  <a name="BKMK_CompleteExamples"></a> <span data-ttu-id="c7c35-164">Esempi completi</span><span class="sxs-lookup"><span data-stu-id="c7c35-164">Complete Examples</span></span>  
 <span data-ttu-id="c7c35-165">Le sezioni seguenti contengono il codice per ognuno degli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="c7c35-165">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="c7c35-166">Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="c7c35-166">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="c7c35-167">È possibile scaricare i progetti da [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="c7c35-167">You can download the projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
### <a name="cancel-a-task-example"></a><span data-ttu-id="c7c35-168">Esempio di annullamento di un'attività</span><span class="sxs-lookup"><span data-stu-id="c7c35-168">Cancel a Task Example</span></span>  
 <span data-ttu-id="c7c35-169">Il codice seguente è il file di file completo per l'esempio che consente di annullare una singola attività.</span><span class="sxs-lookup"><span data-stu-id="c7c35-169">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span></span>  
  
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
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
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
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
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
  
### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="c7c35-170">Esempio di annullamento di un elenco di attività</span><span class="sxs-lookup"><span data-stu-id="c7c35-170">Cancel a List of Tasks Example</span></span>  
 <span data-ttu-id="c7c35-171">Il codice seguente è il file di file completo per l'esempio che consente di annullare un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="c7c35-171">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span></span>  
  
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
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
    End Function  
  
    ' ***Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
  
## <a name="see-also"></a><span data-ttu-id="c7c35-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7c35-172">See Also</span></span>  
 <xref:System.Threading.CancellationTokenSource>  
 <xref:System.Threading.CancellationToken>  
 [<span data-ttu-id="c7c35-173">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7c35-173">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="c7c35-174">Ottimizzazione dell'applicazione Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7c35-174">Fine-Tuning Your Async Application (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)  
 <span data-ttu-id="c7c35-175">[Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="c7c35-175">[Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
