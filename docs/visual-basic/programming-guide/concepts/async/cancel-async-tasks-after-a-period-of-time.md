---
title: Annullare attività asincrone dopo un periodo di tempo
ms.date: 07/20/2015
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
ms.openlocfilehash: 048d4c19d459905ea579ede96c69230e718d55aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396688"
---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a><span data-ttu-id="dd669-102">Annullare attività asincrone dopo un periodo di tempo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd669-102">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>

<span data-ttu-id="dd669-103">È possibile annullare un'operazione asincrona dopo un periodo di tempo tramite il metodo <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> se non si vuole attendere fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="dd669-103">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="dd669-104">Questo metodo pianifica l'annullamento di qualsiasi attività associata che non è stata completata nel periodo di tempo designato dall'espressione `CancelAfter`.</span><span class="sxs-lookup"><span data-stu-id="dd669-104">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="dd669-105">Questo esempio viene aggiunto al codice sviluppato in [Annullare un'attività asincrona o un elenco di attività (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) per scaricare un elenco di siti Web e per visualizzare la lunghezza del contenuto di ogni sito.</span><span class="sxs-lookup"><span data-stu-id="dd669-105">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

> [!NOTE]
> <span data-ttu-id="dd669-106">Per eseguire gli esempi, è necessario avere installato nel computer Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="dd669-106">To run the examples, you must have Visual Studio 2012 or later and the .NET Framework 4.5 or later installed on your computer.</span></span>

## <a name="downloading-the-example"></a><span data-ttu-id="dd669-107">Download dell'esempio</span><span class="sxs-lookup"><span data-stu-id="dd669-107">Downloading the Example</span></span>

<span data-ttu-id="dd669-108">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="dd669-108">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="dd669-109">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dd669-109">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="dd669-110">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="dd669-110">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="dd669-111">Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (con estensione sln) per AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="dd669-111">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="dd669-112">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelAfterTime** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="dd669-112">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="dd669-113">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="dd669-113">Choose the F5 key to run the project.</span></span>

     <span data-ttu-id="dd669-114">Premere CTRL + F5 per eseguire il progetto senza il debug.</span><span class="sxs-lookup"><span data-stu-id="dd669-114">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

6. <span data-ttu-id="dd669-115">Eseguire il programma più volte per verificare che l'output visualizzi il contenuto per tutti i siti Web, per nessun sito Web o per alcuni siti Web.</span><span class="sxs-lookup"><span data-stu-id="dd669-115">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>

 <span data-ttu-id="dd669-116">Se non si vuole scaricare il progetto, è possibile esaminare il file MainWindow.xaml.vb alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dd669-116">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>

## <a name="building-the-example"></a><span data-ttu-id="dd669-117">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="dd669-117">Building the Example</span></span>

<span data-ttu-id="dd669-118">L'esempio riportato in questo argomento aggiunge codice al progetto sviluppato in [Annullare un'attività asincrona o un elenco di attività (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) per annullare un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="dd669-118">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="dd669-119">L'esempio usa la stessa interfaccia utente, sebbene il pulsante **Annulla** non viene usato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="dd669-119">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>

<span data-ttu-id="dd669-120">Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **CancelAListOfTasks** come **progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="dd669-120">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="dd669-121">Aggiungere al progetto le modifiche illustrate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dd669-121">Add the changes in this topic to that project.</span></span>

<span data-ttu-id="dd669-122">Per specificare un tempo massimo prima che le attività vengano contrassegnate come annullate, aggiungere una chiamata a `CancelAfter` al pulsante `startButton_Click`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="dd669-122">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="dd669-123">L'aggiunta viene contrassegnata con asterischi.</span><span class="sxs-lookup"><span data-stu-id="dd669-123">The addition is marked with asterisks.</span></span>

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

<span data-ttu-id="dd669-124">Eseguire il programma più volte per verificare che l'output visualizzi il contenuto per tutti i siti Web, per nessun sito Web o per alcuni siti Web.</span><span class="sxs-lookup"><span data-stu-id="dd669-124">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="dd669-125">L'output seguente è un esempio:</span><span class="sxs-lookup"><span data-stu-id="dd669-125">The following output is a sample:</span></span>

```console
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a><span data-ttu-id="dd669-126">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="dd669-126">Complete Example</span></span>

<span data-ttu-id="dd669-127">Il codice seguente è il testo completo del file MainWindow.xaml.vb per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="dd669-127">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="dd669-128">Gli asterischi contrassegnano gli elementi che sono stati aggiunti per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="dd669-128">Asterisks mark the elements that were added for this example.</span></span>

<span data-ttu-id="dd669-129">Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="dd669-129">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="dd669-130">È possibile scaricare il progetto da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="dd669-130">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

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
                vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        Next
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

' Length of the downloaded string: 35990.

' Length of the downloaded string: 407399.

' Length of the downloaded string: 226091.

' Downloads canceled.
```

## <a name="see-also"></a><span data-ttu-id="dd669-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd669-131">See also</span></span>

- [<span data-ttu-id="dd669-132">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd669-132">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="dd669-133">Procedura dettagliata: accesso al Web con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd669-133">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="dd669-134">Annullare un'attività asincrona o un elenco di attività (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd669-134">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>](cancel-an-async-task-or-a-list-of-tasks.md)
- [<span data-ttu-id="dd669-135">Ottimizzazione dell'applicazione Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd669-135">Fine-Tuning Your Async Application (Visual Basic)</span></span>](fine-tuning-your-async-application.md)
- <span data-ttu-id="dd669-136">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="dd669-136">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
