---
title: 'Procedura: estendere la procedura dettagliata asincrona tramite Task.WhenAll'
ms.date: 07/20/2015
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
ms.openlocfilehash: fb323852c83b1edf51396a0b800c2d54a833d0c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396623"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a>Procedura: Estendere la procedura dettagliata asincrona tramite Task.WhenAll (Visual Basic)

È possibile migliorare le prestazioni della soluzione asincrona in [procedura dettagliata: accesso al Web tramite Async e await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md) tramite il <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> metodo. Questo metodo mette in attesa più operazioni asincrone, rappresentate come una raccolta di attività.

Si noti che nella procedura dettagliata i siti Web vengono scaricati a velocità diverse. A volte un sito Web è molto lento e causa il ritardo di tutti i download rimanenti. Quando si eseguono le soluzioni asincrone compilate nella procedura dettagliata, è possibile terminare il programma con facilità se non si vuole attendere. Un'opzione migliore consiste nell'avviare tutti i download contemporaneamente e consentire a quelli più veloci di continuare senza attendere il termine di quello più lento.

Si applica il metodo `Task.WhenAll` a una raccolta di attività. L'applicazione di `WhenAll` restituisce una singola attività che non viene completata fino quando non vengono completate tutte le attività nella raccolta. Le attività vengono eseguite in parallelo, ma non vengono creati thread aggiuntivi. Il completamento delle attività può avvenire in qualsiasi ordine.

> [!IMPORTANT]
> Nelle procedure riportate di seguito vengono descritte le estensioni per le applicazioni asincrone sviluppate in [procedura dettagliata: accesso al Web tramite Async e await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md). È possibile sviluppare le applicazioni completando la procedura dettagliata o scaricando il codice da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempi di codice per gli sviluppatori).
>
> Per eseguire l'esempio, è necessario avere Visual Studio 2012 o versioni successive installate nel computer.

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a>Per aggiungere Task.WhenAll alla soluzione GetURLContentsAsync

1. Aggiungere il `ProcessURLAsync` metodo alla prima applicazione sviluppata in [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Se è stato scaricato il codice dagli [esempi di codice dello sviluppatore](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), aprire il progetto AsyncWalkthrough e quindi aggiungere `ProcessURLAsync` al file MainWindow. XAML. vb.

    - Se il codice è stato sviluppato completando la procedura dettagliata, aggiungere `ProcessURLAsync` all'applicazione che include il metodo `GetURLContentsAsync`. Il file MainWindow. XAML. vb per questa applicazione è il primo esempio della sezione "esempi di codice completi della procedura dettagliata".

     Il metodo `ProcessURLAsync` consente di consolidare le azioni nel corpo del ciclo `For Each` in `SumPageSizesAsync` nella procedura dettagliata originale. Il metodo scarica in modo asincrono il contenuto di un sito Web specificato come matrice di byte e quindi visualizza e restituisce la lunghezza della matrice di byte.

    ```vb
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. Impostare come commento o eliminare il ciclo `For Each` in `SumPageSizesAsync`, come illustrato nel codice seguente.

    ```vb
    'Dim total = 0
    'For Each url In urlList

    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

    '    ' The previous line abbreviates the following two assignment statements.

    '    ' GetURLContentsAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. Creare una raccolta di attività. Il codice seguente definisce una [query](../linq/index.md) che, quando eseguita dal metodo <xref:System.Linq.Enumerable.ToArray%2A>, crea una raccolta di attività che scaricano il contenuto di ogni sito Web. Le attività vengono avviate quando viene valutata la query.

     Aggiungere il codice seguente al metodo `SumPageSizesAsync` dopo la dichiarazione di `urlList`.

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. Applicare `Task.WhenAll` alla raccolta di attività, `downloadTasks`. `Task.WhenAll` restituisce una singola attività che termina al completamento di tutte le attività della raccolta.

     Nell'esempio seguente, l'espressione `Await` mette in attesa il completamento della singola attività restituita da `WhenAll`. L'espressione restituisce una matrice di numeri interi, dove ogni numero intero rappresenta la lunghezza di un sito Web scaricato. Aggiungere il codice seguente a `SumPageSizesAsync`, dopo il codice aggiunto nel passaggio precedente.

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. Infine, usare il metodo <xref:System.Linq.Enumerable.Sum%2A> per calcolare la somma delle lunghezze di tutti i siti Web. Aggiungere la riga seguente a `SumPageSizesAsync`.

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a>Per aggiungere Task.WhenAll alla soluzione HttpClient.GetByteArrayAsync

1. Aggiungere la versione seguente di `ProcessURLAsync` alla seconda applicazione sviluppata in [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Se è stato scaricato il codice dagli [esempi di codice dello sviluppatore](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), aprire il progetto AsyncWalkthrough_HttpClient e quindi aggiungere `ProcessURLAsync` al file MainWindow. XAML. vb.

    - Se il codice è stato sviluppato completando la procedura dettagliata, aggiungere `ProcessURLAsync` all'applicazione che usa il metodo `HttpClient.GetByteArrayAsync`. Il file MainWindow. XAML. vb per questa applicazione è il secondo esempio della sezione "esempi di codice completi della procedura dettagliata".

     Il metodo `ProcessURLAsync` consente di consolidare le azioni nel corpo del ciclo `For Each` in `SumPageSizesAsync` nella procedura dettagliata originale. Il metodo scarica in modo asincrono il contenuto di un sito Web specificato come matrice di byte e quindi visualizza e restituisce la lunghezza della matrice di byte.

     L'unica differenza rispetto al metodo `ProcessURLAsync` nella procedura precedente consiste nell'uso dell'istanza di <xref:System.Net.Http.HttpClient>, `client`.

    ```vb
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. Impostare come commento o eliminare il ciclo `For Each` in `SumPageSizesAsync`, come illustrato nel codice seguente.

    ```vb
    'Dim total = 0
    'For Each url In urlList
    '    ' GetByteArrayAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

    '    ' The following two lines can replace the previous assignment statement.
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. Definire una [query](../linq/index.md) che, quando eseguita dal metodo <xref:System.Linq.Enumerable.ToArray%2A>, crea una raccolta di attività che scaricano il contenuto di ogni sito Web. Le attività vengono avviate quando viene valutata la query.

     Aggiungere il codice seguente al metodo `SumPageSizesAsync` dopo la dichiarazione di `client` e `urlList`.

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. In seguito applicare `Task.WhenAll` alla raccolta di attività, `downloadTasks`. `Task.WhenAll` restituisce una singola attività che termina al completamento di tutte le attività della raccolta.

     Nell'esempio seguente, l'espressione `Await` mette in attesa il completamento della singola attività restituita da `WhenAll`. Al termine dell'operazione, l'espressione `Await` restituisce una matrice di numeri interi, dove ogni numero intero rappresenta la lunghezza di un sito Web scaricato. Aggiungere il codice seguente a `SumPageSizesAsync`, dopo il codice aggiunto nel passaggio precedente.

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. Infine, usare il metodo <xref:System.Linq.Enumerable.Sum%2A> per ottenere la somma delle lunghezze di tutti i siti Web. Aggiungere la riga seguente a `SumPageSizesAsync`.

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-test-the-taskwhenall-solutions"></a>Per testare le soluzioni Task.WhenAll

Per tutte le soluzioni, premere F5 per eseguire il programma e scegliere il pulsante **Start**. L'output dovrebbe essere simile all'output delle soluzioni asincrone in [procedura dettagliata: accesso al Web tramite Async e await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md). Tuttavia, si noti che i siti Web vengono visualizzati ogni volta in un ordine diverso.

## <a name="example"></a>Esempio

Il codice seguente illustra le estensioni per il progetto che usa il metodo `GetURLContentsAsync` per scaricare il contenuto dal Web.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        'Dim total = 0
        'For Each url In urlList

        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

        '    ' The previous line abbreviates the following two assignment statements.

        '    ' GetURLContentsAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    ' The actions from the foreach loop are moved to this async method.
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                ' CopyToAsync returns a Task, not a Task<T>.
                Await responseStream.CopyToAsync(content)
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
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

## <a name="example"></a>Esempio

Il codice seguente illustra le estensioni per il progetto che usa il metodo `HttpClient.GetByteArrayAsync` per scaricare il contenuto dal Web.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url, client)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        ''<snippet7>
        'Dim total = 0
        'For Each url In urlList
        '    ' GetByteArrayAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    '<snippet31>
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
        '    '</snippet31>

        '    ' The following two lines can replace the previous assignment statement.
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://www.msdn.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
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

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [Procedura dettagliata: accesso al Web con Async e Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)
