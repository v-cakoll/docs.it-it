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
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a>Annullare un'attività asincrona o un elenco di attività (Visual Basic)

È possibile impostare un pulsante che consenta di annullare un'applicazione asincrona se non si vuole attendere il suo completamento. Seguendo gli esempi in questo argomento, è possibile aggiungere un pulsante di annullamento di un'applicazione che scarica il contenuto di un sito Web o di un elenco di siti Web.

Negli esempi viene usata l'interfaccia utente che consente di [ottimizzare l'applicazione asincrona (Visual Basic)](fine-tuning-your-async-application.md) .

> [!NOTE]
> Per eseguire gli esempi, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.

## <a name="cancel-a-task"></a><a name="BKMK_CancelaTask"></a> Annullare un'attività

Il primo esempio associa il pulsante **Annulla** con un'attività di download singola. Se si sceglie il pulsante mentre l'applicazione sta scaricando il contenuto, il download viene annullato.

### <a name="downloading-the-example"></a>Download dell'esempio

È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.

1. Decomprimere il file scaricato e quindi avviare Visual Studio.

2. Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.

3. Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (con estensione sln) per AsyncFineTuningVB.

4. In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelATask** e scegliere **Imposta come progetto di avvio**.

5. Premere F5 per eseguire il progetto.

     Premere CTRL + F5 per eseguire il progetto senza il debug.

 Se non si vuole scaricare il progetto, è possibile esaminare i file MainWindow. XAML. VB alla fine di questo argomento.

### <a name="building-the-example"></a>Compilazione dell'esempio

Le modifiche seguenti aggiungono un pulsante **Annulla** a un'applicazione che scarica un sito Web. Se non si vuole scaricare o compilare l'esempio, è possibile rivedere il prodotto finale nella sezione "Esempi completi" alla fine di questo argomento. Gli asterischi contrassegnano le modifiche nel codice.

Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **StarterCode** come **progetto di avvio** anziché **CancelATask**.

Aggiungere quindi le seguenti modifiche al file MainWindow. XAML. vb del progetto.

1. Dichiarare una variabile `CancellationTokenSource`, `cts`, che sia nell'ambito di accesso di tutti i metodi.

    ```vb
    Class MainWindow

        ' ***Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. Aggiungere il gestore eventi seguente per il pulsante **Annulla**. Il gestore dell'evento usa il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> per inviare notifica a `cts` quando l'utente richiede l'annullamento.

    ```vb
    ' ***Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub
    ```

3. Apportare le modifiche seguenti nel gestore eventi per il pulsante **Avvio**, `startButton_Click`.

    - Creare un'istanza di `CancellationTokenSource`, `cts`.

      ```vb
      ' ***Instantiate the CancellationTokenSource.
      cts = New CancellationTokenSource()
      ```

    - Nella chiamata a `AccessTheWebAsync`, che scarica il contenuto di un sito Web specifico, inviare la proprietà <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> di `cts` come argomento. La proprietà `Token` propaga il messaggio se viene richiesto l'annullamento. Aggiungere un blocco catch che visualizzi un messaggio se l'utente sceglie di annullare l'operazione di download. Il codice seguente illustra le modifiche.

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

4. In `AccessTheWebAsync` usare l'overload <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> del metodo `GetAsync` nel tipo <xref:System.Net.Http.HttpClient> per scaricare il contenuto di un sito Web. Passare `ct`, il parametro <xref:System.Threading.CancellationToken> di `AccessTheWebAsync`, come secondo argomento. Il token trasporta il messaggio se l'utente sceglie il pulsante **Annulla**.

    Il codice seguente illustra tutte le modifiche in `AccessTheWebAsync`.

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

5. Se non si annulla il programma, viene prodotto l'output seguente:

    ```console
    Ready to download.
    Length of the downloaded string: 158125.
    ```

    Se si sceglie il pulsante **Annulla** prima che il programma completi il download del contenuto, il programma produce l'output seguente:

    ```console
    Ready to download.
    Download canceled.
    ```

## <a name="cancel-a-list-of-tasks"></a><a name="BKMK_CancelaListofTasks"></a> Annullare un elenco di attività

È possibile estendere l'esempio precedente per annullare più attività associando la stessa istanza `CancellationTokenSource` con ogni attività. Se si sceglie il pulsante **Annulla**, vengono annullate tutte le attività che non sono ancora complete.

### <a name="downloading-the-example"></a>Download dell'esempio

È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.

1. Decomprimere il file scaricato e quindi avviare Visual Studio.

2. Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.

3. Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (con estensione sln) per AsyncFineTuningVB.

4. In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelAListOfTasks** e scegliere **Imposta come progetto di avvio**.

5. Premere F5 per eseguire il progetto.

     Premere CTRL + F5 per eseguire il progetto senza il debug.

 Se non si vuole scaricare il progetto, è possibile esaminare i file MainWindow. XAML. VB alla fine di questo argomento.

### <a name="building-the-example"></a>Compilazione dell'esempio

Per estendere l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **CancelATask** come **progetto di avvio**. Aggiungere le modifiche seguenti a tale progetto. Gli asterischi contrassegnano le modifiche nel programma.

1. Aggiungere un metodo per creare un elenco di indirizzi Web.

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

2. Chiamare il metodo in `AccessTheWebAsync`.

    ```vb
    ' ***Call SetUpURLList to make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()
    ```

3. Aggiungere il ciclo seguente in `AccessTheWebAsync` per elaborare gli indirizzi Web nell'elenco.

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

4. Poiché `AccessTheWebAsync` visualizza le lunghezze, il metodo non deve restituire nessun valore. Rimuovere l'istruzione return e modificare il tipo restituito del metodo in <xref:System.Threading.Tasks.Task> anziché <xref:System.Threading.Tasks.Task%601>.

    ```vb
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task
    ```

    Chiamare il metodo da `startButton_Click` usando un'istruzione anziché un'espressione.

    ```vb
    Await AccessTheWebAsync(cts.Token)
    ```

5. Se non si annulla il programma, viene prodotto l'output seguente:

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

    Se si sceglie il pulsante **Annulla** prima di aver completato i download, l'output contiene le lunghezze dei download completati prima dell'annullamento.

    ```console
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="complete-examples"></a><a name="BKMK_CompleteExamples"></a> Esempi completi

Le sezioni seguenti contengono il codice per ognuno degli esempi precedenti. Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.

È possibile scaricare i progetti da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).

### <a name="cancel-a-task-example"></a>Esempio di annullamento di un'attività

Il codice seguente è il file MainWindow. XAML. vb completo per l'esempio che annulla una singola attività.

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

### <a name="cancel-a-list-of-tasks-example"></a>Esempio di annullamento di un elenco di attività

Il codice seguente è il file MainWindow. XAML. vb completo per l'esempio che annulla un elenco di attività.

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

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [Programmazione asincrona con Async e Await (Visual Basic)](index.md)
- [Ottimizzazione dell'applicazione Async (Visual Basic)](fine-tuning-your-async-application.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)
