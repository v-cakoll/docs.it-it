---
title: "Annullare un&quot;attività asincrona o un elenco di attività (Visual Basic) | Documenti di Microsoft"
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
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe2df73aaf49f1b61dafcad9a6c6e0f3d014f8ec
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a><span data-ttu-id="4bff9-102">Annullare un'attività asincrona o un elenco di attività (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bff9-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>
<span data-ttu-id="4bff9-103">È possibile impostare un pulsante che consente di annullare un'applicazione async se non si desidera attendere il completamento.</span><span class="sxs-lookup"><span data-stu-id="4bff9-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="4bff9-104">Seguendo gli esempi in questo argomento, è possibile aggiungere un pulsante di annullamento di un'applicazione che consente di scaricare il contenuto di un sito Web o un elenco di siti Web.</span><span class="sxs-lookup"><span data-stu-id="4bff9-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>  
  
 <span data-ttu-id="4bff9-105">Negli esempi viene utilizzato l'interfaccia utente che [ottimizzazione Async applicazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) descrive.</span><span class="sxs-lookup"><span data-stu-id="4bff9-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bff9-106">Per eseguire gli esempi, è necessario disporre di Visual Studio 2012 o versione successiva e .NET Framework 4.5 o versioni successive installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="4bff9-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="4bff9-107"><a name="BKMK_CancelaTask"></a>Annullare un'attività</span><span class="sxs-lookup"><span data-stu-id="4bff9-107"><a name="BKMK_CancelaTask"></a> Cancel a Task</span></span>  
 <span data-ttu-id="4bff9-108">Nel primo esempio associa il **Annulla** pulsante con un'attività di solo download.</span><span class="sxs-lookup"><span data-stu-id="4bff9-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="4bff9-109">Se si sceglie il pulsante mentre l'applicazione sta scaricando il contenuto, il download viene annullato.</span><span class="sxs-lookup"><span data-stu-id="4bff9-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="4bff9-110">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="4bff9-110">Downloading the Example</span></span>  
 <span data-ttu-id="4bff9-111">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [esempio asincrono: Fine ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046) e attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="4bff9-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="4bff9-112">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4bff9-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="4bff9-113">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="4bff9-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="4bff9-114">Nel **Apri progetto** la finestra di dialogo, aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="4bff9-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="4bff9-115">In **Esplora**, aprire il menu di scelta rapida per il **CancelATask** del progetto, quindi fare clic **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="4bff9-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="4bff9-116">Premere il tasto F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="4bff9-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="4bff9-117">Premere i tasti Ctrl + F5 per eseguire il progetto senza eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="4bff9-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="4bff9-118">Se non si desidera scaricare il progetto, è possibile esaminare i file MainWindow.xaml.vb alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4bff9-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="4bff9-119">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="4bff9-119">Building the Example</span></span>  
 <span data-ttu-id="4bff9-120">Aggiungono le seguenti modifiche un **Annulla** pulsante a un'applicazione che esegue il download di un sito Web.</span><span class="sxs-lookup"><span data-stu-id="4bff9-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="4bff9-121">Se non si desidera scaricare o compilare l'esempio, è possibile esaminare il prodotto finale nella sezione "Esempi completi" alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4bff9-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="4bff9-122">Gli asterischi contrassegnare le modifiche nel codice.</span><span class="sxs-lookup"><span data-stu-id="4bff9-122">Asterisks mark the changes in the code.</span></span>  
  
 <span data-ttu-id="4bff9-123">Per compilare l'esempio è l'utente passo passo, seguire le istruzioni nella sezione "Download di esempio", ma scegliere **StarterCode** come il **progetto di avvio** invece di **CancelATask**.</span><span class="sxs-lookup"><span data-stu-id="4bff9-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>  
  
 <span data-ttu-id="4bff9-124">Aggiungere quindi le modifiche seguenti al file MainWindow.xaml.vb del progetto.</span><span class="sxs-lookup"><span data-stu-id="4bff9-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span></span>  
  
1.  <span data-ttu-id="4bff9-125">Dichiarare un `CancellationTokenSource` variabile, `cts`, nell'ambito per tutti i metodi che vi accedono.</span><span class="sxs-lookup"><span data-stu-id="4bff9-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' ***Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  <span data-ttu-id="4bff9-126">Aggiungere il seguente gestore eventi per il **Annulla** pulsante.</span><span class="sxs-lookup"><span data-stu-id="4bff9-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="4bff9-127">Il gestore eventi utilizza il <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>metodo per notificare `cts` quando l'utente richiede l'annullamento.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4bff9-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> method to notify `cts` when the user requests cancellation.</span></span>  
  
    ```vb  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
    ```  
  
3.  <span data-ttu-id="4bff9-128">Apportare le modifiche seguenti nel gestore per il **avviare** pulsante `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="4bff9-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>  
  
    -   <span data-ttu-id="4bff9-129">Creare un'istanza di `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="4bff9-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>  
  
        ```vb  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
        ```  
  
    -   <span data-ttu-id="4bff9-130">Nella chiamata a `AccessTheWebAsync`, che consente di scaricare il contenuto di un sito Web specificato, invia la <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName>proprietà di `cts` come argomento.</xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4bff9-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName> property of `cts` as an argument.</span></span> <span data-ttu-id="4bff9-131">Il `Token` proprietà propaga il messaggio se viene richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="4bff9-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="4bff9-132">Aggiungere un blocco catch che visualizza un messaggio se l'utente sceglie di annullare l'operazione di download.</span><span class="sxs-lookup"><span data-stu-id="4bff9-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="4bff9-133">Il codice seguente mostra le modifiche.</span><span class="sxs-lookup"><span data-stu-id="4bff9-133">The following code shows the changes.</span></span>  
  
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
  
4.  <span data-ttu-id="4bff9-134">In `AccessTheWebAsync`, utilizzare il <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName>Overload dei metodi di `GetAsync` metodo il <xref:System.Net.Http.HttpClient>tipo per scaricare il contenuto di un sito Web.</xref:System.Net.Http.HttpClient> </xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4bff9-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="4bff9-135">Passare `ct`, <xref:System.Threading.CancellationToken>parametro di `AccessTheWebAsync`, come secondo argomento.</xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="4bff9-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="4bff9-136">Il token contiene il messaggio se l'utente sceglie il **Annulla** pulsante.</span><span class="sxs-lookup"><span data-stu-id="4bff9-136">The token carries the message if the user chooses the **Cancel** button.</span></span>  
  
     <span data-ttu-id="4bff9-137">Il codice seguente mostra le modifiche in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="4bff9-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>  
  
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
  
5.  <span data-ttu-id="4bff9-138">Se non si annulla il programma, produce l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="4bff9-138">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     <span data-ttu-id="4bff9-139">Se si sceglie il **Annulla** pulsante prima il programma termina il download del contenuto, il programma produce l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="4bff9-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <span data-ttu-id="4bff9-140"><a name="BKMK_CancelaListofTasks"></a>Annullare un elenco di attività</span><span class="sxs-lookup"><span data-stu-id="4bff9-140"><a name="BKMK_CancelaListofTasks"></a> Cancel a List of Tasks</span></span>  
 <span data-ttu-id="4bff9-141">È possibile estendere l'esempio precedente per annullare molte attività associando lo stesso `CancellationTokenSource` istanza con ogni attività.</span><span class="sxs-lookup"><span data-stu-id="4bff9-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="4bff9-142">Se si sceglie il **Annulla** pulsante, si annulla tutte le attività che non sono ancora completate.</span><span class="sxs-lookup"><span data-stu-id="4bff9-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="4bff9-143">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="4bff9-143">Downloading the Example</span></span>  
 <span data-ttu-id="4bff9-144">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [esempio asincrono: Fine ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046) e attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="4bff9-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="4bff9-145">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4bff9-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="4bff9-146">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="4bff9-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="4bff9-147">Nel **Apri progetto** la finestra di dialogo, aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="4bff9-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="4bff9-148">In **Esplora**, aprire il menu di scelta rapida per il **CancelAListOfTasks** del progetto, quindi fare clic **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="4bff9-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="4bff9-149">Premere il tasto F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="4bff9-149">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="4bff9-150">Premere i tasti Ctrl + F5 per eseguire il progetto senza eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="4bff9-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="4bff9-151">Se non si desidera scaricare il progetto, è possibile esaminare i file MainWindow.xaml.vb alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4bff9-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="4bff9-152">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="4bff9-152">Building the Example</span></span>  
 <span data-ttu-id="4bff9-153">Per estendere l'esempio è l'utente passo passo, seguire le istruzioni nella sezione "Download di esempio", ma scegliere **CancelATask** come il **progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="4bff9-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="4bff9-154">Aggiungere le seguenti modifiche al progetto.</span><span class="sxs-lookup"><span data-stu-id="4bff9-154">Add the following changes to that project.</span></span> <span data-ttu-id="4bff9-155">Gli asterischi contrassegnare le modifiche nel programma.</span><span class="sxs-lookup"><span data-stu-id="4bff9-155">Asterisks mark the changes in the program.</span></span>  
  
1.  <span data-ttu-id="4bff9-156">Aggiungere un metodo per creare un elenco di indirizzi web.</span><span class="sxs-lookup"><span data-stu-id="4bff9-156">Add a method to create a list of web addresses.</span></span>  
  
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
  
2.  <span data-ttu-id="4bff9-157">Chiamare il metodo `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="4bff9-157">Call the method in `AccessTheWebAsync`.</span></span>  
  
    ```vb  
    ' ***Call SetUpURLList to make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
    ```  
  
3.  <span data-ttu-id="4bff9-158">Aggiungere il seguente ciclo in `AccessTheWebAsync` per elaborare gli indirizzi web nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4bff9-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>  
  
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
  
4.  <span data-ttu-id="4bff9-159">Poiché `AccessTheWebAsync` Visualizza le lunghezze, il metodo non è necessario restituire un valore.</span><span class="sxs-lookup"><span data-stu-id="4bff9-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="4bff9-160">Rimuovere l'istruzione return e modificare il tipo restituito del metodo per <xref:System.Threading.Tasks.Task>anziché <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="4bff9-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
<span data-ttu-id="4bff9-161"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4bff9-161"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="4bff9-162">Chiamare il metodo dal `startButton_Click` utilizzando un'istruzione anziché un'espressione.</span><span class="sxs-lookup"><span data-stu-id="4bff9-162">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>  
  
    ```vb  
    Await AccessTheWebAsync(cts.Token)  
    ```  
  
5.  <span data-ttu-id="4bff9-163">Se non si annulla il programma, produce l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="4bff9-163">If you don’t cancel the program, it produces the following output.</span></span>  
  
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
  
     <span data-ttu-id="4bff9-164">Se si sceglie il **Annulla** pulsante prima di aver completato il download, l'output contiene le lunghezze dei download completato prima dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="4bff9-164">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
  
    ```  
  
##  <span data-ttu-id="4bff9-165"><a name="BKMK_CompleteExamples"></a>Esempi completi</span><span class="sxs-lookup"><span data-stu-id="4bff9-165"><a name="BKMK_CompleteExamples"></a> Complete Examples</span></span>  
 <span data-ttu-id="4bff9-166">Nelle sezioni seguenti contengono il codice per ognuno degli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="4bff9-166">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="4bff9-167">Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="4bff9-167">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="4bff9-168">È possibile scaricare i progetti da [esempio asincrono: Fine ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="4bff9-168">You can download the projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
### <a name="cancel-a-task-example"></a><span data-ttu-id="4bff9-169">Annullare un'attività di esempio</span><span class="sxs-lookup"><span data-stu-id="4bff9-169">Cancel a Task Example</span></span>  
 <span data-ttu-id="4bff9-170">Il codice seguente è il file MainWindow.xaml.vb completo per l'esempio che consente di annullare una singola attività.</span><span class="sxs-lookup"><span data-stu-id="4bff9-170">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span></span>  
  
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
  
### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="4bff9-171">Annullare un elenco di esempio di attività</span><span class="sxs-lookup"><span data-stu-id="4bff9-171">Cancel a List of Tasks Example</span></span>  
 <span data-ttu-id="4bff9-172">Il codice seguente è il file MainWindow.xaml.vb completo per l'esempio che consente di annullare un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="4bff9-172">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4bff9-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bff9-173">See Also</span></span>  
 <span data-ttu-id="4bff9-174"><xref:System.Threading.CancellationTokenSource></xref:System.Threading.CancellationTokenSource></span><span class="sxs-lookup"><span data-stu-id="4bff9-174"><xref:System.Threading.CancellationTokenSource></span></span>   
 <span data-ttu-id="4bff9-175"><xref:System.Threading.CancellationToken></xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="4bff9-175"><xref:System.Threading.CancellationToken></span></span>   
<span data-ttu-id="4bff9-176"> [Programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="4bff9-176"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="4bff9-177"> [Ottimizzazione dell'applicazione Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="4bff9-177"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="4bff9-178"> [Esempio asincrono: Ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="4bff9-178"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
