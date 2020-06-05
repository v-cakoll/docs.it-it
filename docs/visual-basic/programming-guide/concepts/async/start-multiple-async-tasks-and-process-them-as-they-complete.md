---
title: Avviare più attività asincrone ed elaborarle quando vengono completate
ms.date: 07/20/2015
ms.assetid: 57ffb748-af40-4794-bedd-bdb7fea062de
ms.openlocfilehash: e227029928676e21d3ed14450140e92b386bf216
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400797"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a>Avviare più attività asincrone ed elaborarle quando vengono completate (Visual Basic)
Usando <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, è possibile avviare più attività contemporaneamente ed elaborarle una ad una quando vengono completate, invece che nell'ordine in cui vengono avviate.  
  
 Nell'esempio seguente viene usata una query per creare una Collection di attività. Ogni attività scarica il contenuto di un sito Web specificato. In ogni iterazione di un ciclo while, una chiamata attesa a `WhenAny` restituisce l'attività nella Collection di attività che completa per prima il download. Questa attività viene rimossa dalla Collection ed elaborata. Il ciclo si ripete finché la Collection non contiene più attività.  
  
> [!NOTE]
> Per eseguire gli esempi, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.  
  
## <a name="downloading-the-example"></a>Download dell'esempio  
 È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.  
  
1. Decomprimere il file scaricato e quindi avviare Visual Studio.  
  
2. Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.  
  
3. Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e quindi aprire il file di soluzione (con estensione sln) per AsyncFineTuningVB.  
  
4. In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **ProcessTasksAsTheyFinish** e quindi scegliere **Imposta come progetto di avvio**.  
  
5. Premere F5 per eseguire il progetto.  
  
     Premere CTRL + F5 per eseguire il progetto senza il debug.  
  
6. Eseguire il progetto più volte per verificare che le lunghezze scaricate non siano sempre nello stesso ordine.  
  
 Se non si vuole scaricare il progetto, è possibile esaminare il file MainWindow.xaml.vb alla fine di questo argomento.  
  
## <a name="building-the-example"></a>Compilazione dell'esempio  
 Questo esempio aggiunge al codice sviluppato in [Annulla le attività asincrone rimanenti dopo che ne è stata completata una (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md) e usa la stessa interfaccia utente.  
  
 Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **CancelAfterOneTask** come **progetto di avvio**. Aggiungere le modifiche in questo argomento al metodo `AccessTheWebAsync` in tale progetto. Le modifiche sono contrassegnate con asterischi.  
  
 Il progetto **CancelAfterOneTask** include già una query che, se eseguita, crea una Collection di attività. Ogni chiamata a `ProcessURLAsync` nel codice seguente restituisce un <xref:System.Threading.Tasks.Task%601> dove `TResult` è un valore intero.  
  
```vb  
Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
    From url In urlList Select ProcessURLAsync(url, client, ct)  
```  
  
 Nel file MainWindow. XAML. vb del progetto apportare le modifiche seguenti al `AccessTheWebAsync` metodo.  
  
- Eseguire la query applicando <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> anziché <xref:System.Linq.Enumerable.ToArray%2A>.  
  
    ```vb  
    Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
    ```  
  
- Aggiungere un ciclo while che esegue i passaggi seguenti per ogni attività nella raccolta.  
  
    1. Attende una chiamata a `WhenAny` per identificare la prima attività nella raccolta che deve completare il relativo download.  
  
        ```vb  
        Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
        ```  
  
    2. Rimuove l'attività dalla Collection.  
  
        ```vb  
        downloadTasks.Remove(firstFinishedTask)  
        ```  
  
    3. Attende `firstFinishedTask`, che viene restituito da una chiamata a `ProcessURLAsync`. La variabile `firstFinishedTask` è un <xref:System.Threading.Tasks.Task%601> dove `TReturn` è un valore intero. L'attività è già stata completata, ma è possibile metterla in attesa per recuperare la lunghezza del sito Web scaricato, come illustrato di seguito.  
  
        ```vb  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 Eseguire il progetto più volte per verificare che le lunghezze scaricate non siano sempre nello stesso ordine.  
  
> [!CAUTION]
> È possibile usare `WhenAny` in un ciclo, come descritto nell'esempio, per risolvere i problemi che includono un numero limitato di attività. Tuttavia, se ci sono molte attività da elaborare, altri approcci sono più efficienti. Per altre informazioni ed esempi, vedere il post relativo all'[elaborazione delle attività quando vengono completate](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/).  
  
## <a name="complete-example"></a>Esempio completo  
 Il codice seguente è il testo completo del file MainWindow.xaml.vb per l'esempio. Gli asterischi contrassegnano gli elementi che sono stati aggiunti per questo esempio.  
  
 Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.  
  
 È possibile scaricare il progetto da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).  
  
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
  
' Length of the download:  226093  
' Length of the download:  412588  
' Length of the download:  175490  
' Length of the download:  204890  
' Length of the download:  158855  
' Length of the download:  145790  
' Length of the download:  44908  
' Downloads complete.  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Ottimizzazione dell'applicazione Async (Visual Basic)](fine-tuning-your-async-application.md)
- [Programmazione asincrona con Async e Await (Visual Basic)](index.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)
