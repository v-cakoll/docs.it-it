---
title: "Annullare attività asincrone dopo un periodo di tempo (Visual Basic) | Documenti di Microsoft"
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
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c2c7c09f9af7c9b7bdcb6411b6db6e2ca4984cb
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a><span data-ttu-id="baa5a-102">Annullare attività asincrone dopo un periodo di tempo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baa5a-102">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>
<span data-ttu-id="baa5a-103">È possibile annullare un'operazione asincrona dopo un periodo di tempo utilizzando il <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName>metodo se non si desidera attendere il completamento dell'operazione.</xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="baa5a-103">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="baa5a-104">Questo metodo pianifica l'annullamento di eventuali attività associate che non completata entro il periodo di tempo definito dal `CancelAfter` espressione.</span><span class="sxs-lookup"><span data-stu-id="baa5a-104">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>  
  
 <span data-ttu-id="baa5a-105">Questo esempio viene aggiunto al codice che è stato sviluppato in [annullare un'attività asincrona o un elenco di attività (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) per scaricare un elenco di siti Web e per visualizzare la lunghezza del contenuto di ciascuna di esse.</span><span class="sxs-lookup"><span data-stu-id="baa5a-105">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baa5a-106">Per eseguire gli esempi, è necessario disporre di Visual Studio 2012 o versione successiva e .NET Framework 4.5 o versioni successive installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="baa5a-106">To run the examples, you must have Visual Studio 2012 or later and the .NET Framework 4.5 or later installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="baa5a-107">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="baa5a-107">Downloading the Example</span></span>  
 <span data-ttu-id="baa5a-108">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [esempio asincrono: Fine ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046) e attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="baa5a-108">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="baa5a-109">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="baa5a-109">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="baa5a-110">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="baa5a-110">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="baa5a-111">Nel **Apri progetto** la finestra di dialogo, aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="baa5a-111">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="baa5a-112">In **Esplora**, aprire il menu di scelta rapida per il **CancelAfterTime** del progetto, quindi fare clic **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="baa5a-112">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="baa5a-113">Premere il tasto F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="baa5a-113">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="baa5a-114">Premere i tasti Ctrl + F5 per eseguire il progetto senza eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="baa5a-114">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="baa5a-115">Eseguire il programma più volte per verificare che l'output potrebbe essere visualizzato l'output per tutti i siti Web, nessun sito Web o alcuni siti web.</span><span class="sxs-lookup"><span data-stu-id="baa5a-115">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>  
  
 <span data-ttu-id="baa5a-116">Se non si desidera scaricare il progetto, è possibile esaminare il file MainWindow.xaml.vb alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="baa5a-116">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="baa5a-117">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="baa5a-117">Building the Example</span></span>  
 <span data-ttu-id="baa5a-118">Nell'esempio riportato in questo argomento viene aggiunto al progetto che è stato sviluppato in [annullare un'attività asincrona o un elenco di attività (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) per annullare un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="baa5a-118">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="baa5a-119">Nell'esempio viene utilizzata la stessa interfaccia utente, anche se il **Annulla** pulsante non viene utilizzato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="baa5a-119">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="baa5a-120">Per compilare l'esempio è l'utente passo passo, seguire le istruzioni nella sezione "Download di esempio", ma scegliere **CancelAListOfTasks** come il **progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="baa5a-120">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="baa5a-121">A tale progetto, aggiungere le modifiche in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="baa5a-121">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="baa5a-122">Per specificare un tempo massimo prima che l'attività viene contrassegnata come annullata, aggiungere una chiamata a `CancelAfter` a `startButton_Click`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="baa5a-122">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="baa5a-123">L'aggiunta è contrassegnato con un asterisco.</span><span class="sxs-lookup"><span data-stu-id="baa5a-123">The addition is marked with asterisks.</span></span>  
  
```vb  
Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
    ' Instantiate the CancellationTokenSource.  
    cts = New CancellationTokenSource()  
  
    resultsTextBox.Clear()  
  
    Try  
        ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
        ' can adjust the time.)  
        cts.CancelAfter(2500)  
  
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
```  
  
 <span data-ttu-id="baa5a-124">Eseguire il programma più volte per verificare che l'output potrebbe essere visualizzato l'output per tutti i siti Web, nessun sito Web o alcuni siti web.</span><span class="sxs-lookup"><span data-stu-id="baa5a-124">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="baa5a-125">L'output seguente è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="baa5a-125">The following output is a sample.</span></span>  
  
```  
Length of the downloaded string: 35990.  
  
Length of the downloaded string: 407399.  
  
Length of the downloaded string: 226091.  
  
Downloads canceled.  
```  
  
## <a name="complete-example"></a><span data-ttu-id="baa5a-126">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="baa5a-126">Complete Example</span></span>  
 <span data-ttu-id="baa5a-127">Il codice seguente è il testo completo del file MainWindow.xaml.vb per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="baa5a-127">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="baa5a-128">Gli asterischi contrassegnare gli elementi che sono stati aggiunti per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="baa5a-128">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="baa5a-129">Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="baa5a-129">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="baa5a-130">È possibile scaricare il progetto da [esempio asincrono: Fine ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="baa5a-130">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
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
            ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You   
            ' can adjust the time.)  
            cts.CancelAfter(2500)  
  
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
  
        ' Process each element in the list of web addresses.  
        For Each url In urlList  
            ' GetAsync returns a Task(Of HttpResponseMessage).   
            ' Argument ct carries the message if the Cancel button is chosen.   
            ' Note that the Cancel button can cancel all remaining downloads.  
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
            ' Retrieve the website contents from the HttpResponseMessage.  
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
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
  
' Length of the downloaded string: 35990.  
  
' Length of the downloaded string: 407399.  
  
' Length of the downloaded string: 226091.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a><span data-ttu-id="baa5a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baa5a-131">See Also</span></span>  
 <span data-ttu-id="baa5a-132">[Programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="baa5a-132">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="baa5a-133"> [Procedura dettagliata: Accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="baa5a-133"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="baa5a-134"> [Annullare un'attività asincrona o un elenco di attività (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="baa5a-134"> [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) </span></span>  
<span data-ttu-id="baa5a-135"> [Ottimizzazione dell'applicazione Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="baa5a-135"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="baa5a-136"> [Esempio asincrono: Ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="baa5a-136"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
