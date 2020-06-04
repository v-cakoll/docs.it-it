---
title: 'Procedura: effettuare più richieste Web in parallelo tramite Async e Await'
ms.date: 07/20/2015
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
ms.openlocfilehash: 40bab392af94ba941c2562e885a8d2e08aeea5b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396584"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a>Procedura: Eseguire più richieste Web in parallelo tramite async e await (Visual Basic)

In un metodo asincrono le attività vengono avviate al momento della creazione. L'operatore [await](../../../language-reference/operators/await-operator.md) viene applicato all'attività nel punto del metodo in cui l'elaborazione non può continuare finché l'attività non viene completata. Spesso un'attività viene messa in attesa al momento della creazione, come illustrato nell'esempio seguente.

```vb
Dim result = Await someWebAccessMethodAsync(url)
```

Tuttavia, è possibile separare la creazione dalla messa in attesa dell'attività se il programma ha altro lavoro da eseguire che non dipende dal completamento dell'attività.

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

Tra l'avvio di un'attività e la messa in attesa, è possibile avviare altre attività. Le attività aggiuntive vengono eseguite in modo implicito in parallelo, ma non vengono creati thread aggiuntivi.

Il programma seguente avvia tre download Web asincroni e quindi li mette in attesa nell'ordine in cui vengono chiamati. Si noti che, quando si esegue il programma, non sempre le attività finiscono nell'ordine in cui sono state create e messe in attesa. Vengono avviate al momento della creazione ed è possibile che una o più di una finiscano prima che il metodo raggiunga le espressioni await.

> [!NOTE]
> Per completare il progetto, è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.

Per un altro esempio in cui vengono avviate più attività contemporaneamente, vedere [procedura: estendere la procedura dettagliata asincrona tramite Task. WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).

È possibile scaricare il codice per l'esempio da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e) (Esempi di codice per sviluppatori).

### <a name="to-set-up-the-project"></a>Per impostare il progetto

1. Per configurare un'applicazione WPF, completare i passaggi seguenti. Per istruzioni dettagliate su questa procedura, vedere [procedura dettagliata: accesso al Web tramite Async e await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Creare un'applicazione WPF che contenga una casella di testo e un pulsante. Denominare il pulsante `startButton` e la casella di testo `resultsTextBox`.

    - Aggiunge un riferimento a <xref:System.Net.Http>.

    - Nel file MainWindow. XAML. vb aggiungere un' `Imports` istruzione per `System.Net.Http` .

### <a name="to-add-the-code"></a>Per aggiungere il codice

1. Nella finestra di progettazione MainWindow. XAML fare doppio clic sul pulsante per creare il `startButton_Click` gestore eventi in MainWindow. XAML. vb.

2. Copiare il codice seguente e incollarlo nel corpo di `startButton_Click` in MainWindow. XAML. vb.

    ```vb
    resultsTextBox.Clear()
    Await CreateMultipleTasksAsync()
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    ```

     Il codice chiama un metodo asincrono, `CreateMultipleTasksAsync`, che avvia l'applicazione.

3. Aggiungere i metodi di supporto seguenti al progetto:

    - `ProcessURLAsync` usa un metodo <xref:System.Net.Http.HttpClient> per scaricare il contenuto di un sito Web come matrice di byte. Il metodo di supporto `ProcessURLAsync` visualizza e restituisce la lunghezza della matrice.

    - `DisplayResults` visualizza il numero di byte della matrice di byte per ogni URL. Questa visualizzazione indica quando ogni attività ha terminato il download.

     Copiare i metodi seguenti e incollarli dopo il `startButton_Click` gestore eventi in MainWindow. XAML. vb.

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

4. Infine, definire il metodo `CreateMultipleTasksAsync`, che esegue i passaggi seguenti.

    - Il metodo dichiara un oggetto `HttpClient`, che è necessario per accedere al metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.

    - Il metodo crea e avvia tre attività di tipo <xref:System.Threading.Tasks.Task%601>, dove `TResult` è un numero intero. Al termine di ogni attività, `DisplayResults` vengono visualizzati l'URL dell'attività e la lunghezza del contenuto scaricato. Poiché le attività sono in esecuzione in modo asincrono, l'ordine in cui vengono visualizzati i risultati potrebbe essere diverso da quello in cui le attività sono stati dichiarate.

    - Il metodo attende il completamento di ogni attività. Ogni operatore `Await` sospende l'esecuzione di `CreateMultipleTasksAsync` finché non viene completata l'attività in attesa. L'operatore recupera anche il valore restituito dalla chiamata a `ProcessURLAsync` da ogni attività completata.

    - Quando sono state completate le attività e sono stati recuperati i valori interi, il metodo somma le lunghezze dei siti Web e visualizza il risultato.

     Copiare il metodo seguente e incollarlo nella soluzione.

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

5. Premere F5 per eseguire il programma e quindi scegliere il pulsante **Avvia**.

     Eseguire il programma più volte per verificare che le tre attività non vengano completate sempre nello stesso ordine e che l'ordine in cui vengono completate non è necessariamente l'ordine in cui sono state create e messe in attesa.

## <a name="example"></a>Esempio

Il codice seguente contiene l'esempio completo.

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

## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: accesso al Web con Async e Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Programmazione asincrona con Async e Await (Visual Basic)](index.md)
- [Procedura: Estendere la procedura dettagliata asincrona tramite Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
