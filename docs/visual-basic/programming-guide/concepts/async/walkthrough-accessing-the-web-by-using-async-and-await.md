---
title: 'Procedura dettagliata: accesso al Web tramite Async e Await'
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: 41ededd4d4335b78b8d7a33e8fe387c7d632cbee
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400745"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a>Procedura dettagliata: accesso al Web con Async e Await (Visual Basic)

È possibile scrivere programmi asincroni in modo più semplice e intuitivo usando le funzionalità async/await. È possibile scrivere codice asincrono simile al codice sincrono e consentire al compilatore di gestire le complesse funzioni di callback e continuazione tipiche del codice asincrono.

Per ulteriori informazioni sulla funzionalità async, vedere [programmazione asincrona con Async e await (Visual Basic)](index.md).

Questa procedura dettagliata inizia con l'esecuzione di un'applicazione Windows Presentation Foundation (WPF) sincrona che somma il numero di byte in un elenco di siti Web. La procedura dettagliata converte quindi l'applicazione in una soluzione asincrona usando le nuove funzionalità.

Se non si desidera compilare manualmente le applicazioni, è possibile scaricare "Esempio asincrono: accesso alla procedura dettagliata Web (C# e Visual Basic)" da [esempi di codice per sviluppatori](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).

Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:

> [!div class="checklist"]
>
> - [Creare un'applicazione WPF](#create-a-wpf-application)
> - [Progettare una finestra WPF MainWindow semplice](#design-a-simple-wpf-mainwindow)
> - [Aggiungere un riferimento](#add-a-reference)
> - [Aggiungere le istruzioni Import necessarie](#add-necessary-imports-statements)
> - [Creare un'applicazione sincrona](#create-a-synchronous-application)
> - [Eseguire il test della soluzione sincrona](#test-the-synchronous-solution)
> - [Convertire GetURLContents in un metodo asincrono](#convert-geturlcontents-to-an-asynchronous-method)
> - [Convertire SumPageSizes in un metodo asincrono](#convert-sumpagesizes-to-an-asynchronous-method)
> - [Convertire startButton_Click in un metodo asincrono](#convert-startbutton_click-to-an-asynchronous-method)
> - [Eseguire il test della soluzione asincrona](#test-the-asynchronous-solution)
> - [Sostituire il metodo GetURLContentsAsync con un metodo .NET Framework](#replace-the-geturlcontentsasync-method-with-a-net-framework-method)

Vedere la sezione [esempio](#example) per l'esempio completo asincrono.

## <a name="prerequisites"></a>Prerequisiti

È necessario che sia installato nel computer Visual Studio 2012 o versione successiva. Per ulteriori informazioni, vedere la pagina [download](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) di Visual Studio.

## <a name="create-a-wpf-application"></a>Creare un'applicazione WPF

1. Avviare Visual Studio.

2. Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.

    Verrà visualizzata la finestra di dialogo **Nuovo progetto** .

3. Nel riquadro **modelli installati** scegliere Visual Basic, quindi scegliere **applicazione WPF** dall'elenco dei tipi di progetto.

4. Nella casella di testo **Nome** immettere `AsyncExampleWPF` e quindi scegliere il pulsante **OK**.

    Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.

## <a name="design-a-simple-wpf-mainwindow"></a>Progettare una finestra WPF MainWindow semplice

1. Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .

2. Se la finestra **Casella degli strumenti** non è visibile, aprire il menu **Visualizza** e quindi scegliere **Casella degli strumenti**.

3. Aggiungere un controllo **Button** e un controllo **TextBox** alla finestra **MainWindow**.

4. Evidenziare il controllo **TextBox** e nella finestra **Proprietà** impostare i valori seguenti:

    - Impostare la proprietà **Nome** su `resultsTextBox`.

    - Impostare la proprietà **Height** su 250.

    - Impostare la proprietà **Width** su 500.

    - Nel scheda **Testo** specificare un tipo di carattere a spaziatura fissa, ad esempio Lucida Console o Global Monospace.

5. Evidenziare il controllo **Button** e nella finestra **Proprietà** impostare i valori seguenti:

    - Impostare la proprietà **Nome** su `startButton`.

    - Modificare il valore della proprietà **Content** da **Button** in **Start**.

6. Posizionare la casella di testo e il pulsante in modo che entrambi siano visualizzati nella finestra **MainWindow**.

    Per altre informazioni su WPF XAML Designer, vedere [Creazione di un'interfaccia utente tramite XAML Designer](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).

## <a name="add-a-reference"></a>Aggiungere un riferimento

1. In **Esplora soluzioni** evidenziare il nome del progetto.

2. Nella barra dei menu scegliere **Progetto**, **Aggiungi riferimento**.

    Verrà visualizzata la finestra di dialogo **Gestione riferimenti**.

3. Nella parte superiore della finestra di dialogo verificare che il progetto sia destinato a .NET Framework 4.5 o versione successiva.

4. Nell'area **Assembly** scegliere **Framework** se non è già selezionato.

5. Nell'elenco dei nomi selezionare la casella di controllo **System.Net.Http**.

6. Scegliere il pulsante **OK** per chiudere la finestra di dialogo.

## <a name="add-necessary-imports-statements"></a>Aggiungere le istruzioni Import necessarie

1. In **Esplora soluzioni**aprire il menu di scelta rapida per MainWindow. XAML. vb, quindi scegliere **Visualizza codice**.

2. Aggiungere le seguenti `Imports` istruzioni all'inizio del file di codice, se non sono già presenti.

    ```vb
    Imports System.Net.Http
    Imports System.Net
    Imports System.IO
    ```

## <a name="create-a-synchronous-application"></a>Creare un'applicazione sincrona

1. Nella finestra di progettazione MainWindow. XAML fare doppio clic sul pulsante **Start** per creare il `startButton_Click` gestore eventi in MainWindow. XAML. vb.

2. In MainWindow. XAML. vb copiare il codice seguente nel corpo di `startButton_Click` :

    ```vb
    resultsTextBox.Clear()
    SumPageSizes()
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."
    ```

    Il codice chiama il metodo che controlla l'applicazione `SumPageSizes` e visualizza un messaggio quando il controllo torna a `startButton_Click`.

3. Il codice per la soluzione sincrona contiene i quattro metodi seguenti:

    - `SumPageSizes`, che ottiene un elenco di URL delle pagine Web da `SetUpURLList` e quindi chiama `GetURLContents` e `DisplayResults` per elaborare ogni URL.

    - `SetUpURLList`, che crea e restituisce un elenco di indirizzi web.

    - `GetURLContents`, che scarica il contenuto di ogni sito Web e restituisce il contenuto come matrice di byte.

    - `DisplayResults`, che visualizza il numero di byte nella matrice di byte per ogni URL.

    Copiare i quattro metodi seguenti e incollarli nel `startButton_Click` gestore eventi in MainWindow. XAML. vb:

    ```vb
    Private Sub SumPageSizes()

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetURLContents returns the contents of url as a byte array.
            Dim urlContents As Byte() = GetURLContents(url)

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)
    End Sub

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
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

    Private Function GetURLContents(url As String) As Byte()

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        Using response As WebResponse = webReq.GetResponse()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content)
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
    ```

## <a name="test-the-synchronous-solution"></a>Eseguire il test della soluzione sincrona

1. Premere F5 per eseguire il programma e quindi scegliere il pulsante **Avvia**.

    Verrà visualizzato un output simile all'elenco seguente:

    ```console
    msdn.microsoft.com/library/windows/apps/br211380.aspx        383832
    msdn.microsoft.com                                            33964
    msdn.microsoft.com/library/hh290136.aspx               225793
    msdn.microsoft.com/library/ee256749.aspx               143577
    msdn.microsoft.com/library/hh290138.aspx               237372
    msdn.microsoft.com/library/hh290140.aspx               128279
    msdn.microsoft.com/library/dd470362.aspx               157649
    msdn.microsoft.com/library/aa578028.aspx               204457
    msdn.microsoft.com/library/ms404677.aspx               176405
    msdn.microsoft.com/library/ff730837.aspx               143474

    Total bytes returned:  1834802

    Control returned to startButton_Click.
    ```

    Si noti che sono necessari alcuni secondi per visualizzare i conteggi. Durante tale periodo, il thread dell'interfaccia utente viene bloccato mentre attende il download delle risorse richieste. Di conseguenza, è possibile spostare, ingrandire, ridurre o chiudere la finestra di visualizzazione dopo aver scelto il  pulsante **Start**. Queste operazioni hanno esito negativo finché non vengono visualizzati i conteggi dei byte. Se un sito Web non risponde, non si ha alcuna indicazione relativa al sito con esito negativo. È inoltre difficile interrompere l'attesa e chiudere il programma.

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a>Convertire GetURLContents in un metodo asincrono

1. Per convertire la soluzione sincrona in una soluzione asincrona, il punto di partenza migliore è in `GetURLContents` perché le chiamate al <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> metodo e al metodo sono i punti in <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> cui l'applicazione accede al Web. .NET Framework semplifica la conversione fornendo versioni asincrone di entrambi i metodi.

    Per altre informazioni sui modelli usati in `GetURLContents`, vedere <xref:System.Net.WebRequest>.

    > [!NOTE]
    > Mentre si esegue la procedura descritta in questa procedura dettagliata, vengono visualizzati diversi errori del compilatore. È possibile ignorarli e continuare con la procedura dettagliata.

    Modificare il metodo chiamato nella terza riga di `GetURLContents` da `GetResponse` nel metodo asincrono basato su attività <xref:System.Net.WebRequest.GetResponseAsync%2A>.

    ```vb
    Using response As WebResponse = webReq.GetResponseAsync()
    ```

2. `GetResponseAsync` restituisce <xref:System.Threading.Tasks.Task%601>. In questo caso, la *variabile di restituzione dell'attività*, `TResult` , è di tipo <xref:System.Net.WebResponse> . L'attività rappresenta una promessa di creazione di un oggetto `WebResponse` effettivo dopo il download dei dati richiesti e il completamento dell'esecuzione dell'attività.

    Per recuperare il `WebResponse` valore dall'attività, applicare un operatore [await](../../../language-reference/operators/await-operator.md) alla chiamata a `GetResponseAsync` , come illustrato nel codice seguente.

    ```vb
    Using response As WebResponse = Await webReq.GetResponseAsync()
    ```

    L'operatore `GetURLContents` sospende l'esecuzione del metodo corrente `Await` fino al completamento dell'attività attesa. Nel frattempo il controllo viene restituito al chiamante del metodo asincrono. In questo esempio, il metodo corrente è `GetURLContents` e il chiamante è `SumPageSizes`. Quando l'attività è terminata, l'oggetto promesso `WebResponse` viene generato come valore dell'attività attesa e assegnato alla variabile `response`.

    L'istruzione precedente può essere suddivisa nelle due istruzioni seguenti per chiarire cosa accade.

    ```vb
    Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
    Using response As WebResponse = Await responseTask
    ```

    La chiamata a `webReq.GetResponseAsync` restituisce `Task(Of WebResponse)` o `Task<WebResponse>`. Viene quindi `Await` applicato un operatore all'attività per recuperare il `WebResponse` valore.

    Se il metodo asincrono ha operazioni da eseguire che non dipendono dal completamento dell'attività, il metodo può continuare l'esecuzione tra queste due istruzioni dopo la chiamata al metodo asincrono e prima che venga applicato l'operatore await. Per esempi, vedere [procedura: eseguire più richieste Web in parallelo tramite Async e await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) e [procedura: estendere la procedura dettagliata asincrona tramite Task. WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).

3. Poiché è stato aggiunto l'operatore `Await` nel passaggio precedente, verrà generato un errore del compilatore. L'operatore può essere usato solo nei metodi contrassegnati con il modificatore [Async](../../../language-reference/modifiers/async.md) . Ignorare l'errore mentre vengono ripetuti i passaggi di conversione per sostituire la chiamata a `CopyTo` con una chiamata a `CopyToAsync`.

    - Modificare il nome del metodo chiamato in <xref:System.IO.Stream.CopyToAsync%2A>.

    - Il metodo `CopyTo` o `CopyToAsync` copia i byte nel relativo argomento `content` e non restituisce un valore significativo. Nella versione sincrona, la chiamata a `CopyTo` è un'istruzione semplice che non restituisce un valore. La versione asincrona `CopyToAsync` restituisce <xref:System.Threading.Tasks.Task>. L'attività è analoga a "Task(void)" e consente l'attesa del metodo. Applicare `Await` o `await` alla chiamata a `CopyToAsync`, come mostrato nel codice riportato di seguito.

        ```vb
        Await responseStream.CopyToAsync(content)
        ```

         L'istruzione precedente abbrevia le due righe di codice riportate di seguito.

        ```vb
        ' CopyToAsync returns a Task, not a Task<T>.
        Dim copyTask As Task = responseStream.CopyToAsync(content)

        ' When copyTask is completed, content contains a copy of
        ' responseStream.
        Await copyTask
        ```

4. A questo punto, non rimane che modificare la firma del metodo in `GetURLContents`. È possibile usare l' `Await` operatore solo nei metodi contrassegnati con il modificatore [Async](../../../language-reference/modifiers/async.md) . Aggiungere il modificatore per contrassegnare il metodo come *metodo async*, come mostrato nel codice riportato di seguito.

    ```vb
    Private Async Function GetURLContents(url As String) As Byte()
    ```

5. Il tipo restituito di un metodo asincrono può essere solo <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601> . In Visual Basic, il metodo deve essere `Function` che restituisce `Task` o `Task(Of T)` oppure il metodo deve essere `Sub`. In genere, un `Sub` metodo viene usato solo in un gestore eventi asincrono, dove `Sub` è obbligatorio. In altri casi, si utilizza `Task(T)` se il metodo completed dispone di un'istruzione [Return](../../../language-reference/statements/return-statement.md) che restituisce un valore di tipo T e si utilizza `Task` se il metodo completato non restituisce un valore significativo.

    Per ulteriori informazioni, vedere [tipi restituiti asincroni (Visual Basic)](async-return-types.md).

    Il metodo `GetURLContents` dispone di un'istruzione return che restituisce una matrice di byte. Pertanto, il tipo restituito della versione asincrona è Task(T), dove T è una matrice di byte. Apportare le modifiche seguenti nella firma del metodo:

    - Cambiare il tipo restituito in `Task(Of Byte())`.

    - Per convenzione, i metodi asincroni presentano nomi che terminano in "Async". Rinominare pertanto il metodo `GetURLContentsAsync`.

    Nel codice seguente sono illustrate queste modifiche.

    ```vb
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())
    ```

    Dopo aver apportato queste modifiche, la conversione di `GetURLContents` in un metodo asincrono è completa.

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a>Convertire SumPageSizes in un metodo asincrono

1. Ripetere i passaggi della procedura precedente per `SumPageSizes`. In primo luogo, modificare la chiamata a `GetURLContents` in una chiamata asincrona.

    - Modificare il nome del metodo chiamato da `GetURLContents` in `GetURLContentsAsync`, se non è ancora stato fatto.

    - Applicare `Await` all'attività restituita da `GetURLContentsAsync` per ottenere il valore della matrice di byte.

    Nel codice seguente sono illustrate queste modifiche.

    ```vb
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)
    ```

    L'assegnazione precedente abbrevia le due righe di codice riportate di seguito.

    ```vb
    ' GetURLContentsAsync returns a task. At completion, the task
    ' produces a byte array.
    Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    Dim urlContents As Byte() = Await getContentsTask
    ```

2. Apportare le modifiche seguenti nella firma del metodo:

    - Contrassegnare il metodo con il modificatore `Async`.

    - Aggiungere "Async" al nome del metodo.

    - Non esiste alcuna variabile di restituzione dell'attività, T, questa volta perché `SumPageSizesAsync` non restituisce un valore per T. (il metodo non ha alcuna `Return` istruzione). Tuttavia, il metodo deve restituire un oggetto `Task` per essere awaitable. Modificare quindi il tipo di metodo da `Sub` a `Function` . Il tipo restituito della funzione è `Task`.

    Nel codice seguente sono illustrate queste modifiche.

    ```vb
    Private Async Function SumPageSizesAsync() As Task
    ```

    La conversione di `SumPageSizes` in `SumPageSizesAsync` è completa.

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a>Convertire startButton_Click in un metodo asincrono

1. Nel gestore eventi modificare il nome del metodo chiamato da `SumPageSizes` in `SumPageSizesAsync`, se non è ancora stato fatto.

2. Poiché `SumPageSizesAsync` è un metodo asincrono, modificare il codice nel gestore eventi in modo che attenda il risultato.

    La chiamata a `SumPageSizesAsync` rispecchia la chiamata a `CopyToAsync` in `GetURLContentsAsync`. La chiamata restituisce `Task` e non `Task(T)`.

    Come nelle procedure precedenti, è possibile convertire la chiamata tramite una o due istruzioni. Nel codice seguente sono illustrate queste modifiche.

    ```vb
    ' One-step async call.
    Await SumPageSizesAsync()

    ' Two-step async call.
    Dim sumTask As Task = SumPageSizesAsync()
    Await sumTask
    ```

3. Per impedire la reentrancy accidentale dell'operazione, aggiungere l'istruzione seguente all'inizio di `startButton_Click` per disabilitare il pulsante **Start**.

    ```vb
    ' Disable the button until the operation is complete.
    startButton.IsEnabled = False
    ```

    È possibile riabilitare il pulsante alla fine del gestore eventi.

    ```vb
    ' Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = True
    ```

    Per ulteriori informazioni sulla rientranza, vedere [gestione della rientranza in app asincrone (Visual Basic)](handling-reentrancy-in-async-apps.md).

4. Aggiungere infine il modificatore `Async` alla dichiarazione, in modo che il gestore eventi possa attendere `SumPagSizesAsync`.

    ```vb
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
    ```

    In genere, i nomi dei gestori eventi non vengono modificati. Il tipo restituito non viene modificato in `Task` perché i gestori eventi devono essere `Sub` procedure in Visual Basic.

    La conversione del progetto dall'elaborazione sincrona a quella asincrona è completa.

## <a name="test-the-asynchronous-solution"></a>Eseguire il test della soluzione asincrona

1. Premere F5 per eseguire il programma e quindi scegliere il pulsante **Avvia**.

2. Viene visualizzato un output simile all'output della soluzione sincrona. Esistono tuttavia le differenze seguenti:

    - I risultati non vengono restituiti contemporaneamente, al termine dell'elaborazione. Ad esempio, entrambi i programmi contengono una riga in `startButton_Click` che consente di cancellare la casella di testo. Lo scopo è quello di cancellare il contenuto della casella di testo tra le esecuzioni se si sceglie il pulsante **Start** per la seconda volta, dopo la visualizzazione di un set di risultati. Nella versione sincrona la casella di testo viene cancellata prima della seconda visualizzazione dei conteggi, ovvero quando vengono completati i download e il thread dell'interfaccia utente è libero di eseguire altre operazioni. Nella versione asincrona, la casella di testo viene cancellata subito dopo aver scelto il pulsante **Start**.

    - È importante notare che il thread dell'interfaccia utente non è bloccato durante il download. È possibile spostare o ridimensionare la finestra durante il download, il conteggio e la visualizzazione delle risorse Web. Se uno dei siti Web è lento o non risponde, è possibile annullare l'operazione scegliendo il pulsante **Chiudi** (il simbolo x su sfondo rosso nell'angolo superiore destro).

## <a name="replace-the-geturlcontentsasync-method-with-a-net-framework-method"></a>Sostituire il metodo GetURLContentsAsync con un metodo .NET Framework

1. Il .NET Framework fornisce molti metodi asincroni che è possibile usare. Uno di essi, il <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType> metodo, esegue solo le operazioni necessarie per questa procedura dettagliata. È possibile usarlo al posto del metodo `GetURLContentsAsync` creato in una procedura precedente.

    Il primo passaggio consiste nel creare un <xref:System.Net.Http.HttpClient> oggetto nel `SumPageSizesAsync` metodo. Aggiungere la dichiarazione seguente all'inizio del metodo.

    ```vb
    ' Declare an HttpClient object and increase the buffer size. The
    ' default buffer size is 65,536.
    Dim client As HttpClient =
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}
    ```

2. In `SumPageSizesAsync,` sostituire la chiamata al metodo `GetURLContentsAsync` con una chiamata al metodo `HttpClient`.

    ```vb
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ```

3. Rimuovere o impostare come commento il metodo `GetURLContentsAsync` precedentemente scritto.

4. Premere F5 per eseguire il programma e quindi scegliere il pulsante **Avvia**.

    Il comportamento di questa versione del progetto deve corrispondere al comportamento descritto nella procedura "Per eseguire il test della soluzione asincrona" ma con un intervento ridotto da parte dell'utente.

## <a name="example"></a>Esempio

Di seguito è riportato l'esempio completo della soluzione asincrona convertita che usa il `GetURLContentsAsync` metodo asincrono. Si noti che è molto simile alla soluzione sincrona originale.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)

            ' The previous line abbreviates the following two assignment statements.

            '//<snippet21>
            ' GetURLContentsAsync returns a task. At completion, the task
            ' produces a byte array.
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
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

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()

            ' The previous statement abbreviates the following two statements.

            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
            'Using response As WebResponse = Await responseTask

            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                Await responseStream.CopyToAsync(content)

                ' The previous statement abbreviates the following two statements.

                ' CopyToAsync returns a Task, not a Task<T>.
                'Dim copyTask As Task = responseStream.CopyToAsync(content)

                ' When copyTask is completed, content contains a copy of
                ' responseStream.
                'Await copyTask
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

Il codice seguente contiene l'esempio completo della soluzione che usa il metodo `HttpClient`, `GetByteArrayAsync`.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        ' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetByteArrayAsync returns a task. At completion, the task
            ' produces a byte array.
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

            ' The following two lines can replace the previous assignment statement.
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
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

- [Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempio asincrono: accesso alla procedura dettagliata Web (C# e Visual Basic)
- [Operatore await](../../../language-reference/operators/await-operator.md)
- [Async](../../../language-reference/modifiers/async.md)
- [Programmazione asincrona con Async e Await (Visual Basic)](index.md)
- [Tipi restituiti asincroni (Visual Basic)](async-return-types.md)
- [Programmazione asincrona basata su attività](https://www.microsoft.com/download/details.aspx?id=19957)
- [Procedura: Estendere la procedura dettagliata asincrona tramite Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [Procedura: Eseguire più richieste Web in parallelo tramite async e await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
