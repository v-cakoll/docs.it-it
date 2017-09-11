---
title: "Avviare più attività asincrone ed elaborarle quando vengono completate (Visual Basic) | Documenti di Microsoft"
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
ms.assetid: 57ffb748-af40-4794-bedd-bdb7fea062de
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
ms.openlocfilehash: 6fbf4611ecd64abfd016963dff887d82aad333b7
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a><span data-ttu-id="e78d7-102">Avviare più attività asincrone ed elaborarle quando vengono completate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e78d7-102">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>
<span data-ttu-id="e78d7-103">Utilizzando <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, è possibile avviare più attività contemporaneamente ed elaborare uno alla volta, si è completati invece di elaborarle nell'ordine in cui è avviati.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e78d7-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>  
  
 <span data-ttu-id="e78d7-104">Nell'esempio seguente viene utilizzata una query per creare una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="e78d7-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="e78d7-105">Ogni attività Scarica il contenuto di un sito Web specificato.</span><span class="sxs-lookup"><span data-stu-id="e78d7-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="e78d7-106">In ogni iterazione di un periodo di tempo del ciclo, una chiamata a atteso `WhenAny` restituisce l'attività nella raccolta di attività che termina il download per prima.</span><span class="sxs-lookup"><span data-stu-id="e78d7-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="e78d7-107">Tale attività viene rimossa dalla raccolta ed elaborato.</span><span class="sxs-lookup"><span data-stu-id="e78d7-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="e78d7-108">Il ciclo viene ripetuto fino a quando la raccolta non contiene altre attività.</span><span class="sxs-lookup"><span data-stu-id="e78d7-108">The loop repeats until the collection contains no more tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e78d7-109">Per eseguire gli esempi, è necessario disporre di Visual Studio 2012 o versione successiva e .NET Framework 4.5 o versioni successive installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="e78d7-109">To run the examples, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="e78d7-110">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="e78d7-110">Downloading the Example</span></span>  
 <span data-ttu-id="e78d7-111">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [esempio asincrono: Fine ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046) e attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e78d7-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="e78d7-112">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e78d7-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="e78d7-113">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="e78d7-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="e78d7-114">Nel **Apri progetto** la finestra di dialogo, aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="e78d7-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="e78d7-115">In **Esplora**, aprire il menu di scelta rapida per il **ProcessTasksAsTheyFinish** del progetto, quindi fare clic **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="e78d7-115">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="e78d7-116">Premere il tasto F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="e78d7-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="e78d7-117">Premere i tasti Ctrl + F5 per eseguire il progetto senza eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="e78d7-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="e78d7-118">Eseguire il progetto più volte per verificare che le lunghezze scaricate non siano sempre visualizzati nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="e78d7-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
 <span data-ttu-id="e78d7-119">Se non si desidera scaricare il progetto, è possibile esaminare il file MainWindow.xaml.vb alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e78d7-119">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="e78d7-120">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="e78d7-120">Building the Example</span></span>  
 <span data-ttu-id="e78d7-121">Questo esempio viene aggiunto al codice che è stato sviluppato in [annullare attività asincrone rimanenti dopo una completa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) e utilizza la stessa interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e78d7-121">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) and uses the same UI.</span></span>  
  
 <span data-ttu-id="e78d7-122">Per compilare l'esempio è l'utente passo passo, seguire le istruzioni nella sezione "Download di esempio", ma scegliere **CancelAfterOneTask** come il **progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="e78d7-122">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAfterOneTask** as the **StartUp Project**.</span></span> <span data-ttu-id="e78d7-123">Aggiungere le modifiche in questo argomento per il `AccessTheWebAsync` metodo nel progetto.</span><span class="sxs-lookup"><span data-stu-id="e78d7-123">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="e78d7-124">Le modifiche sono contrassegnate con asterischi.</span><span class="sxs-lookup"><span data-stu-id="e78d7-124">The changes are marked with asterisks.</span></span>  
  
 <span data-ttu-id="e78d7-125">Il **CancelAfterOneTask** progetto include già una query che, quando eseguita, crea una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="e78d7-125">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="e78d7-126">Ogni chiamata a `ProcessURLAsync` nel codice seguente restituisce un <xref:System.Threading.Tasks.Task%601>dove `TResult` è un numero intero.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="e78d7-126">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
<span data-ttu-id="e78d7-127"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e78d7-127"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="e78d7-128">Nel file MainWindow.xaml.vb del progetto, apportare le modifiche seguenti per il `AccessTheWebAsync` metodo.</span><span class="sxs-lookup"><span data-stu-id="e78d7-128">In the MainWindow.xaml.vb file of the  project, make the following changes to the `AccessTheWebAsync` method.</span></span>  
  
-   <span data-ttu-id="e78d7-129">Eseguire la query applicando <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>anziché <xref:System.Linq.Enumerable.ToArray%2A>.</xref:System.Linq.Enumerable.ToArray%2A> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e78d7-129">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
<span data-ttu-id="e78d7-130"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e78d7-130"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
-   <span data-ttu-id="e78d7-131">Aggiungere un po' di tempo ciclo che esegue i passaggi seguenti per ogni attività nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e78d7-131">Add a while loop that performs the following steps for each task in the collection.</span></span>  
  
    1.  <span data-ttu-id="e78d7-132">Attende una chiamata a `WhenAny` per identificare la prima attività da completare il download nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e78d7-132">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>  
  
<span data-ttu-id="e78d7-133"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e78d7-133"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
    2.  <span data-ttu-id="e78d7-134">Rimuove l'attività dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="e78d7-134">Removes that task from the collection.</span></span>  
  
<span data-ttu-id="e78d7-135"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="e78d7-135"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
    3.  <span data-ttu-id="e78d7-136">Attende `firstFinishedTask`, che viene restituito da una chiamata a `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="e78d7-136">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="e78d7-137">Il `firstFinishedTask` variabile è un <xref:System.Threading.Tasks.Task%601>dove `TReturn` è un numero intero.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="e78d7-137">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="e78d7-138">L'attività è già completa, ma si è in attesa per recuperare la lunghezza del sito Web scaricato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e78d7-138">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span>  
  
        ```vb  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 <span data-ttu-id="e78d7-139">È necessario eseguire il progetto più volte per verificare che le lunghezze scaricate non siano sempre visualizzati nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="e78d7-139">You should run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e78d7-140">È possibile utilizzare `WhenAny` in un ciclo, come descritto nell'esempio, per risolvere i problemi che coinvolgono un numero limitato di attività.</span><span class="sxs-lookup"><span data-stu-id="e78d7-140">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="e78d7-141">Tuttavia, se ci sono molte attività da elaborare, altri approcci sono più efficienti.</span><span class="sxs-lookup"><span data-stu-id="e78d7-141">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="e78d7-142">Per ulteriori informazioni ed esempi, vedere [man mano che completa le attività di elaborazione](http://go.microsoft.com/fwlink/?LinkId=260810).</span><span class="sxs-lookup"><span data-stu-id="e78d7-142">For more information and examples, see [Processing Tasks as they complete](http://go.microsoft.com/fwlink/?LinkId=260810).</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="e78d7-143">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="e78d7-143">Complete Example</span></span>  
 <span data-ttu-id="e78d7-144">Il codice seguente è il testo completo del file MainWindow.xaml.vb per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="e78d7-144">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="e78d7-145">Gli asterischi contrassegnare gli elementi che sono stati aggiunti per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="e78d7-145">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="e78d7-146">Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="e78d7-146">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="e78d7-147">È possibile scaricare il progetto da [esempio asincrono: Fine ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="e78d7-147">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
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
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
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
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToList to execute the query and start the download tasks.   
        Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
  
        ' ***Add a loop to process the tasks one at a time until none remain.  
        While downloadTasks.Count > 0  
            ' ***Identify the first task that completes.  
            Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
            ' ***Remove the selected task from the list so that you don't  
            ' process it more than once.  
            downloadTasks.Remove(firstFinishedTask)  
  
            ' ***Await the first completed task and display the results.  
            Dim length = Await firstFinishedTask  
            resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        End While  
  
    End Function  
  
    ' Bundle the processing steps for a website into one async method.  
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
  
' Sample output:  
  
' Length of the download:  226093  
' Length of the download:  412588  
' Length of the download:  175490  
' Length of the download:  204890  
' Length of the download:  158855  
' Length of the download:  145790  
' Length of the download:  44908  
' Downloads complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="e78d7-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e78d7-148">See Also</span></span>  
 <span data-ttu-id="e78d7-149"><xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A></span><span class="sxs-lookup"><span data-stu-id="e78d7-149"><xref:System.Threading.Tasks.Task.WhenAny%2A></span></span>   
<span data-ttu-id="e78d7-150"> [Ottimizzazione dell'applicazione Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="e78d7-150"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="e78d7-151"> [Programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="e78d7-151"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="e78d7-152"> [Esempio asincrono: Ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="e78d7-152"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
