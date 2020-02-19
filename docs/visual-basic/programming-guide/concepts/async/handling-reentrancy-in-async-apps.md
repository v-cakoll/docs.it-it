---
title: Gestione della reentrancy nelle applicazioni asincrone
ms.date: 07/20/2015
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
ms.openlocfilehash: 44c2cdbadd02aef6b2bbb32bde8bcb9b19f8360d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452578"
---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a>Gestione della rientranza nelle app asincrone (Visual Basic)

Quando si include codice asincrono nell'applicazione, è consigliabile prevedere ed evitare la reentrancy, ovvero il reinserimento di un'operazione asincrona prima del suo completamento. Se non vengono identificate e gestite le possibilità di reentrancy, esse possono causare risultati imprevisti.

> [!NOTE]
> Per eseguire l'esempio, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.

> [!NOTE]
> Transport Layer Security (TLS) versione 1,2 è ora la versione minima da usare nello sviluppo di app. Se l'app è destinata a una versione di .NET Framework precedente alla 4,7, vedere l'articolo seguente per [le procedure consigliate per Transport Layer Security (TLS) con il .NET Framework](../../../../framework/network-programming/tls.md).

## <a name="BKMK_RecognizingReentrancy"></a> Riconoscimento della reentrancy

Nell'esempio riportato in questo argomento viene scelto un pulsante **Start** per avviare un'app asincrona che scarica una serie di siti Web e calcola il numero totale di byte scaricati. Una versione sincrona dell'esempio avrebbe risposto allo stesso modo indipendentemente dal numero di volte che un utente sceglie il pulsante perché, dopo la prima volta, il thread dell'interfaccia utente ignora tali eventi fino al termine dell'esecuzione dell'applicazione. In un'applicazione asincrona, tuttavia, il thread dell'interfaccia utente continua a rispondere e potrebbe essere possibile riattivare l'operazione asincrona prima del suo completamento.

Nell'esempio seguente viene illustrato l'output previsto se l'utente sceglie il pulsante **Start** una sola volta. Viene visualizzato un elenco dei siti Web scaricati con la dimensione, espressa in byte, di ogni sito. Il numero totale di byte viene visualizzato alla fine.

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

Tuttavia, se l'utente sceglie il pulsante più volte, il gestore eventi viene chiamato più volte e il processo di download viene riattivato ogni volta. Di conseguenza, diverse operazioni asincrone sono in esecuzione contemporaneamente, l'output si sovrappone ai risultati e il numero totale di byte è poco chiaro.

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
7. msdn.microsoft.com                                            42972
4. msdn.microsoft.com/library/hh290140.aspx               117152
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

5. msdn.microsoft.com/library/hh524395.aspx                68959
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
6. msdn.microsoft.com/library/ms404677.aspx               197325
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
7. msdn.microsoft.com                                            42972
5. msdn.microsoft.com/library/hh524395.aspx                68959
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591

6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

È possibile esaminare il codice che genera l'output andando alla fine di questo argomento. È possibile provare il codice scaricando la soluzione nel computer locale ed eseguendo il progetto WebsiteDownload oppure usando il codice alla fine di questo argomento per creare un progetto personalizzato. Per altre informazioni e istruzioni, vedere [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample).

## <a name="BKMK_HandlingReentrancy"></a> Gestione della reentrancy

È possibile gestire la reentrancy in diversi modi, a seconda delle operazioni che si desidera che l'applicazione esegua. In questo argomento vengono illustrati gli esempi seguenti:

- [Disabilitare il pulsante Start](#BKMK_DisableTheStartButton)

  Disabilitare il pulsante **Start** mentre l'operazione è in esecuzione in modo che l'utente non la interrompa.

- [Annullare e riavviare l'operazione](#BKMK_CancelAndRestart)

  Annullare le operazioni ancora in esecuzione quando l'utente sceglie di nuovo il pulsante **Start** e consentire la continuazione dell'operazione richiesta più di recente.

- [Eseguire più operazioni e mettere in coda l'output](#BKMK_RunMultipleOperations)

  Consentire l'esecuzione asincrona di tutte le operazioni richieste, ma coordinare la visualizzazione dell'output in modo che vengano visualizzati i risultati di ogni operazione tutti insieme e ordinati.

### <a name="BKMK_DisableTheStartButton"></a> Disabilitare il pulsante Start

È possibile bloccare il pulsante **Start** durante l'esecuzione di un'operazione disabilitando il pulsante nella parte superiore del gestore eventi `StartButton_Click`. È possibile riabilitare il pulsante dall'interno un blocco `Finally` al termine dell'operazione in modo che gli utenti possano eseguire nuovamente l'applicazione.

Il codice seguente illustra queste modifiche, contrassegnate da asterischi. È possibile aggiungere le modifiche al codice alla fine di questo argomento, oppure è possibile scaricare l'applicazione finita da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET). Il nome del progetto è DisableStartButton.

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' This line is commented out to make the results clearer in the output.
    'ResultsTextBox.Text = ""

    ' ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = False

    Try
        Await AccessTheWebAsync()

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    ' ***Enable the Start button in case you want to run the program again.
    Finally
        StartButton.IsEnabled = True

    End Try
End Sub
```

In seguito alle modifiche, il pulsante non risponde mentre `AccessTheWebAsync` sta scaricando i siti Web. Pertanto, il processo non potrà essere riattivato.

### <a name="BKMK_CancelAndRestart"></a> Annullare e riavviare l'operazione

Anziché disabilitare il pulsante **Start**, è possibile tenere attivo il pulsante ma, se l'utente sceglie di nuovo il pulsante, è necessario annullare l'operazione in esecuzione e consentire la continuazione dell'operazione richiesta più di recente.

Per ulteriori informazioni sull'annullamento, vedere [ottimizzazione dell'applicazione asincrona (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).

Per configurare questo scenario, apportare le modifiche seguenti al codice di base fornito in [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample). È anche possibile scaricare l'app finita da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET). Il nome di questo progetto è CancelAndRestart.

1. Dichiarare una variabile <xref:System.Threading.CancellationTokenSource>, `cts`, che sia compresa nell'ambito per tutti i metodi.

    ```vb
    Class MainWindow // Or Class MainPage

        ' *** Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. In `StartButton_Click` determinare se un'operazione è già in corso. Se il valore di `cts` è `Nothing`, nessuna operazione è già attiva. Se il valore non è `Nothing`, l'operazione già in esecuzione viene annullata.

    ```vb
    ' *** If a download process is already underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If
    ```

3. Impostare `cts` su un valore diverso che rappresenti il processo corrente.

    ```vb
    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS
    ```

4. Alla fine del `StartButton_Click`, il processo corrente è completo, quindi impostare il valore di `cts` di nuovo su `Nothing`.

    ```vb
    ' *** When the process completes, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
    ```

Il codice seguente illustra tutte le modifiche in `StartButton_Click`. Le aggiunte sono contrassegnate con asterischi.

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)

    ' This line is commented out to make the results clearer.
    'ResultsTextBox.Text = ""

    ' *** If a download process is underway, cancel it.
    If cts IsNot Nothing Then
        cts.Cancel()
    End If

    ' *** Now set cts to cancel the current process if the button is chosen again.
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()
    cts = newCTS

    Try
        ' *** Send a token to carry the message if the operation is canceled.
        Await AccessTheWebAsync(cts.Token)

    Catch ex As OperationCanceledException
        ResultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."
    End Try

    ' *** When the process is complete, signal that another process can proceed.
    If cts Is newCTS Then
        cts = Nothing
    End If
End Sub
```

In `AccessTheWebAsync`, apportare le seguenti modifiche.

- Aggiungere un parametro per accettare il token di annullamento da `StartButton_Click`.

- Usare il metodo <xref:System.Net.Http.HttpClient.GetAsync%2A> per scaricare i siti Web, in quanto `GetAsync` accetta un argomento <xref:System.Threading.CancellationToken>.

- Prima di chiamare `DisplayResults` per visualizzare i risultati per ogni sito Web scaricato, controllare `ct` per verificare che l'operazione corrente non sia stata annullata.

 Il codice seguente illustra queste modifiche, contrassegnate da asterischi.

```vb
' *** Provide a parameter for the CancellationToken from StartButton_Click.
Private Async Function AccessTheWebAsync(ct As CancellationToken) As Task

    ' Declare an HttpClient object.
    Dim client = New HttpClient()

    ' Make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()

    Dim total = 0
    Dim position = 0

    For Each url In urlList
        ' *** Use the HttpClient.GetAsync method because it accepts a
        ' cancellation token.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' *** Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' *** Check for cancellations before displaying information about the
        ' latest site.
        ct.ThrowIfCancellationRequested()

        position += 1
        DisplayResults(url, urlContents, position)

        ' Update the total.
        total += urlContents.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

Se si sceglie il pulsante **Start** più volte mentre l'app è in esecuzione, si otterrà un risultato simile all'output seguente:

```console
1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               122505
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
Download canceled.

1. msdn.microsoft.com/library/hh191443.aspx                83732
2. msdn.microsoft.com/library/aa578028.aspx               205273
3. msdn.microsoft.com/library/jj155761.aspx                29019
4. msdn.microsoft.com/library/hh290140.aspx               117152
5. msdn.microsoft.com/library/hh524395.aspx                68959
6. msdn.microsoft.com/library/ms404677.aspx               197325
7. msdn.microsoft.com                                            42972
8. msdn.microsoft.com/library/ff730837.aspx               146159

TOTAL bytes returned:  890591
```

Per eliminare gli elenchi parziali, rimuovere la prima riga di codice in `StartButton_Click` per cancellare la casella di testo ogni volta che l'utente riavvia l'operazione.

### <a name="BKMK_RunMultipleOperations"></a> Eseguire più operazioni e mettere in coda l'output

Il terzo esempio è il più complesso in quanto l'app avvia un'altra operazione asincrona ogni volta che l'utente sceglie il pulsante **Start** e tutte le operazioni vengono eseguite fino al completamento. Tutte le operazioni richieste scaricano i siti Web dall'elenco in modo asincrono, ma l'output delle operazioni viene visualizzato in sequenza. In altre parole, l'attività di download effettiva è di tipo interleaved, come illustrato nell'output in [Riconoscimento della reentrancy](#BKMK_RecognizingReentrancy), ma l'elenco dei risultati per ogni gruppo viene visualizzato separatamente.

Le operazioni condividono un codice <xref:System.Threading.Tasks.Task> globale, `pendingWork`, che funge da gatekeeper per il processo di visualizzazione.

È possibile eseguire questo esempio incollando le modifiche nel codice in [Compilazione dell'app](#BKMK_BuildingTheApp) oppure è possibile attenersi alle istruzioni riportate in [Download dell'app](#BKMK_DownloadingTheApp) per scaricare l'esempio ed eseguire il progetto QueueResults.

Nell'output seguente viene illustrato il risultato restituito quando l'utente sceglie il pulsante **Start** una sola volta. L'etichetta A indica che il risultato fa riferimento alla prima volta che il pulsante **Start** viene scelto. I numeri indicano l'ordine degli URL nell'elenco delle destinazioni di download.

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               209858
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71260
A-6. msdn.microsoft.com/library/ms404677.aspx               199186
A-7. msdn.microsoft.com                                            53266
A-8. msdn.microsoft.com/library/ff730837.aspx               148020

TOTAL bytes returned:  918876

#Group A is complete.
```

Se l'utente sceglie il pulsante **Start** tre volte, l'app genera un output simile alle righe seguenti. Le righe di informazioni che iniziano con un cancelletto (#) tengono traccia dello stato di avanzamento dell'applicazione.

```console
#Starting group A.
#Task assigned for group A.

A-1. msdn.microsoft.com/library/hh191443.aspx                87389
A-2. msdn.microsoft.com/library/aa578028.aspx               207089
A-3. msdn.microsoft.com/library/jj155761.aspx                30870
A-4. msdn.microsoft.com/library/hh290140.aspx               119027
A-5. msdn.microsoft.com/library/hh524395.aspx                71259
A-6. msdn.microsoft.com/library/ms404677.aspx               199185

#Starting group B.
#Task assigned for group B.

A-7. msdn.microsoft.com                                            53266

#Starting group C.
#Task assigned for group C.

A-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916095

B-1. msdn.microsoft.com/library/hh191443.aspx                87389
B-2. msdn.microsoft.com/library/aa578028.aspx               207089
B-3. msdn.microsoft.com/library/jj155761.aspx                30870
B-4. msdn.microsoft.com/library/hh290140.aspx               119027
B-5. msdn.microsoft.com/library/hh524395.aspx                71260
B-6. msdn.microsoft.com/library/ms404677.aspx               199186

#Group A is complete.

B-7. msdn.microsoft.com                                            53266
B-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  916097

C-1. msdn.microsoft.com/library/hh191443.aspx                87389
C-2. msdn.microsoft.com/library/aa578028.aspx               207089

#Group B is complete.

C-3. msdn.microsoft.com/library/jj155761.aspx                30870
C-4. msdn.microsoft.com/library/hh290140.aspx               119027
C-5. msdn.microsoft.com/library/hh524395.aspx                72765
C-6. msdn.microsoft.com/library/ms404677.aspx               199186
C-7. msdn.microsoft.com                                            56190
C-8. msdn.microsoft.com/library/ff730837.aspx               148010

TOTAL bytes returned:  920526

#Group C is complete.
```

I gruppi B e C vengono avviati prima del completamento del gruppo A, ma l'output per ogni gruppo viene visualizzato separatamente. Viene prima visualizzato l'intero output del gruppo A, seguito dall'intero output del gruppo B e dall'intero output del gruppo C. L'app visualizza sempre i gruppi nell'ordine e, per ogni gruppo, visualizza sempre le informazioni sui singoli siti Web in base all'ordine in cui i relativi URL sono visualizzati nell'elenco di URL.

Tuttavia, è possibile prevedere l'ordine in cui vengono eseguiti i download. Dopo l'avvio di più gruppi, tutte le attività di download generate sono attive. Non è possibile presupporre che A-1 venga scaricato prima di B-1 e che A-1 venga scaricato prima A 2.

#### <a name="global-definitions"></a>Definizioni globali

Il codice di esempio contiene le seguenti dichiarazioni globali visibili da tutti i metodi.

```vb
Class MainWindow    ' Class MainPage in Windows Store app.

    ' ***Declare the following variables where all methods can access them.
    Private pendingWork As Task = Nothing
    Private group As Char = ChrW(AscW("A") - 1)
```

La variabile `Task`, `pendingWork`, controlla il processo di visualizzazione e impedisce a qualsiasi gruppo di interrompere l'operazione di visualizzazione di un altro gruppo. La variabile di tipo carattere, `group`, etichetta l'output dei vari gruppi per far sì che i risultati vengano visualizzati nell'ordine previsto.

#### <a name="the-click-event-handler"></a>Il gestore eventi Click

Il gestore eventi `StartButton_Click` incrementa la lettera del gruppo ogni volta che l'utente sceglie il pulsante **Start**. Il gestore chiama quindi `AccessTheWebAsync` per eseguire l'operazione di download.

```vb
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
    ' ***Verify that each group's results are displayed together, and that
    ' the groups display in order, by marking each group with a letter.
    group = ChrW(AscW(group) + 1)
    ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Starting group {0}.", group)

    Try
        ' *** Pass the group value to AccessTheWebAsync.
        Dim finishedGroup As Char = Await AccessTheWebAsync(group)

        ' The following line verifies a successful return from the download and
        ' display procedures.
        ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Group {0} is complete." & vbCrLf, finishedGroup)

    Catch ex As Exception
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."

    End Try
End Sub
```

#### <a name="the-accessthewebasync-method"></a>Il metodo AccessTheWebAsync

Questo esempio suddivide `AccessTheWebAsync` in due metodi. Il primo metodo, `AccessTheWebAsync`, avvia tutte le attività di download per un gruppo e configura `pendingWork` per il controllo del processo di visualizzazione. Il metodo usa una query LINQ (Language Integrated Query) e <xref:System.Linq.Enumerable.ToArray%2A> per avviare tutte le attività di download contemporaneamente.

`AccessTheWebAsync` quindi chiama `FinishOneGroupAsync` per attendere il completamento di ogni download e visualizzare la relativa lunghezza.

`FinishOneGroupAsync` restituisce un'attività assegnata a `pendingWork` in `AccessTheWebAsync`. Tale valore impedisce l'interruzione da parte di un'altra operazione prima del completamento dell'attività.

```vb
Private Async Function AccessTheWebAsync(grp As Char) As Task(Of Char)

    Dim client = New HttpClient()

    ' Make a list of the web addresses to download.
    Dim urlList As List(Of String) = SetUpURLList()

    ' ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Dim getContentTasks As Task(Of Byte())() =
        urlList.Select(Function(addr) client.GetByteArrayAsync(addr)).ToArray()

    ' ***Call the method that awaits the downloads and displays the results.
    ' Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp)

    ResultsTextBox.Text &=
        String.Format(vbCrLf & "#Task assigned for group {0}. Download tasks are active." & vbCrLf, grp)

    ' ***This task is complete when a group has finished downloading and displaying.
    Await pendingWork

    ' You can do other work here or just return.
    Return grp
End Function
```

#### <a name="the-finishonegroupasync-method"></a>Il metodo FinishOneGroupAsync

Questo metodo consente di scorrere le attività di download in reciproca attesa in un gruppo, nonché visualizza la lunghezza del sito Web scaricato e aggiunge la lunghezza al totale.

La prima istruzione in `FinishOneGroupAsync` usa `pendingWork` per assicurarsi che l'uso del metodo non interferisca con un'operazione già presente nel processo di visualizzazione o in attesa. Se tale operazione è in corso, l'operazione di attivazione deve attendere il suo turno.

```vb
Private Async Function FinishOneGroupAsync(urls As List(Of String), contentTasks As Task(Of Byte())(), grp As Char) As Task

    ' Wait for the previous group to finish displaying results.
    If pendingWork IsNot Nothing Then
        Await pendingWork
    End If

    Dim total = 0

    ' contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    For i As Integer = 0 To contentTasks.Length - 1
        ' Await the download of a particular URL, and then display the URL and
        ' its length.
        Dim content As Byte() = Await contentTasks(i)
        DisplayResults(urls(i), content, i, grp)
        total += content.Length
    Next

    ' Display the total count for all of the websites.
    ResultsTextBox.Text &=
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
End Function
```

È possibile eseguire questo esempio incollando le modifiche nel codice in [Compilazione dell'app](#BKMK_BuildingTheApp) oppure è possibile attenersi alle istruzioni riportate in [Download dell'app](#BKMK_DownloadingTheApp) per scaricare l'esempio ed eseguire il progetto QueueResults.

#### <a name="points-of-interest"></a>Punti di interesse

Le righe di informazioni che iniziano con un segno di cancelletto (#) nell'output descrivono il funzionamento dell'esempio.

L'output mostra i modelli seguenti.

- Un gruppo può essere avviato anche se un gruppo precedente è visualizzato nel relativo output, ma la visualizzazione dell'output del gruppo precedente non viene interrotta.

  ```console
  #Starting group A.
  #Task assigned for group A. Download tasks are active.

  A-1. msdn.microsoft.com/library/hh191443.aspx                87389
  A-2. msdn.microsoft.com/library/aa578028.aspx               207089
  A-3. msdn.microsoft.com/library/jj155761.aspx                30870
  A-4. msdn.microsoft.com/library/hh290140.aspx               119037
  A-5. msdn.microsoft.com/library/hh524395.aspx                71260

  #Starting group B.
  #Task assigned for group B. Download tasks are active.

  A-6. msdn.microsoft.com/library/ms404677.aspx               199186
  A-7. msdn.microsoft.com                                            53078
  A-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915919

  B-1. msdn.microsoft.com/library/hh191443.aspx                87388
  B-2. msdn.microsoft.com/library/aa578028.aspx               207089
  B-3. msdn.microsoft.com/library/jj155761.aspx                30870

  #Group A is complete.

  B-4. msdn.microsoft.com/library/hh290140.aspx               119027
  B-5. msdn.microsoft.com/library/hh524395.aspx                71260
  B-6. msdn.microsoft.com/library/ms404677.aspx               199186
  B-7. msdn.microsoft.com                                            53078
  B-8. msdn.microsoft.com/library/ff730837.aspx               148010

  TOTAL bytes returned:  915908
  ```

- L'attività `pendingWork` viene `Nothing` all'inizio di `FinishOneGroupAsync` solo per il gruppo A, che viene avviato per primo. Il gruppo A non ha ancora completato un'espressione await quando raggiunge `FinishOneGroupAsync`. Pertanto, il controllo non è stato restituito a `AccessTheWebAsync` e non è stata eseguita la prima assegnazione a `pendingWork`.

- Le due righe seguenti sono sempre visualizzate insieme nell'output. Il codice non viene mai interrotto tra l'avvio dell'operazione di un gruppo in `StartButton_Click` e l'assegnazione di un'attività per il gruppo a `pendingWork`.

  ```console
  #Starting group B.
  #Task assigned for group B. Download tasks are active.
  ```

  Dopo che un gruppo entra in `StartButton_Click`, l'operazione non completa un'espressione await fino a quando l'operazione non entra in `FinishOneGroupAsync`. Pertanto, nessuna operazione può assumere il controllo durante l'esecuzione di tale segmento di codice.

## <a name="BKMD_SettingUpTheExample"></a> Revisione ed esecuzione dell'app di esempio

Per comprendere meglio l'applicazione di esempio, è possibile scaricarla, compilarla manualmente o esaminare il codice alla fine di questo argomento senza implementare l'applicazione.

> [!NOTE]
> Per eseguire l'esempio come applicazione dektop WPF (Windows Presentation Foundation), è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.

### <a name="BKMK_DownloadingTheApp"></a> Download dell'app

1. Scaricare il file compresso da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET).

2. Decomprimere il file scaricato e quindi avviare Visual Studio.

3. Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.

4. Passare alla cartella che contiene il codice di esempio decompresso e quindi aprire il file di soluzione (sln).

5. In **Esplora soluzioni** aprire il menu di scelta rapida del progetto che si vuole eseguire e scegliere **Set as StartUpProject** (Imposta come progetto di avvio).

6. Premere CTRL+F5 per compilare ed eseguire il progetto.

### <a name="BKMK_BuildingTheApp"></a> Compilazione dell'app

Nella sezione seguente viene illustrato il codice per compilare l'esempio come app WPF.

##### <a name="to-build-a-wpf-app"></a>Per compilare un'applicazione WPF

1. Avviare Visual Studio.

2. Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.

     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .

3. Nel riquadro **modelli installati** espandere **Visual Basic**, quindi espandere **Windows**.

4. Dall'elenco dei tipi di progetto scegliere **Applicazione WPF**.

5. Assegnare al progetto il nome `WebsiteDownloadWPF`, scegliere .NET Framework versione 4,6 o successiva, quindi fare clic sul pulsante **OK** .

     Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.

6. Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .

     Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow.xaml in **Esplora soluzioni** e scegliere **Visualizza codice**.

7. Nella visualizzazione **XAML** di MainWindow.xaml sostituire il codice con quello riportato di seguito.

    ```xaml
    <Window x:Class="MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WebsiteDownloadWPF"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Width="517" Height="360">
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />
        </Grid>
    </Window>
    ```

     Nella visualizzazione **Progettazione** di MainWindow.xaml viene visualizzata una finestra semplice contenente una casella di testo e un pulsante.

8. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **riferimenti** e scegliere **Aggiungi riferimento**.

     Aggiungere un riferimento per <xref:System.Net.Http>, se non è già selezionato.

9. In **Esplora soluzioni**aprire il menu di scelta rapida per MainWindow. XAML. vb, quindi scegliere **Visualizza codice**.

10. In MainWindow. XAML. vb sostituire il codice con il codice seguente.

    ```vb
    ' Add the following Imports statements, and add a reference for System.Net.Http.
    Imports System.Net.Http
    Imports System.Threading

    Class MainWindow

        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)
            System.Net.ServicePointManager.SecurityProtocol = System.Net.ServicePointManager.SecurityProtocol Or System.Net.SecurityProtocolType.Tls12

            ' This line is commented out to make the results clearer in the output.
            'ResultsTextBox.Text = ""

            Try
                Await AccessTheWebAsync()

            Catch ex As Exception
                ResultsTextBox.Text &= vbCrLf & "Downloads failed."

            End Try
        End Sub

        Private Async Function AccessTheWebAsync() As Task

            ' Declare an HttpClient object.
            Dim client = New HttpClient()

            ' Make a list of web addresses.
            Dim urlList As List(Of String) = SetUpURLList()

            Dim total = 0
            Dim position = 0

            For Each url In urlList
                ' GetByteArrayAsync returns a task. At completion, the task
                ' produces a byte array.
                Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

                position += 1
                DisplayResults(url, urlContents, position)

                ' Update the total.
                total += urlContents.Length
            Next

            ' Display the total count for all of the websites.
            ResultsTextBox.Text &=
                String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)
        End Function

        Private Function SetUpURLList() As List(Of String)
            Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com/library/hh191443.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/jj155761.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/hh524395.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
            Return urls
        End Function

        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)
            ' Display the length of each website. The string format is designed
            ' to be used with a monospaced font, such as Lucida Console or
            ' Global Monospace.

            ' Strip off the "http:'".
            Dim displayURL = url.Replace("https://", "")
            ' Display position in the URL list, the URL, and the number of bytes.
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)
        End Sub
    End Class
    ```

11. Premere CTRL+F5 per eseguire il programma e scegliere il pulsante **Start** più volte.

12. Apportare le modifiche descritte in [Disabilitare il pulsante Start](#BKMK_DisableTheStartButton), [Annullare e riavviare l'operazione](#BKMK_CancelAndRestart) o [Eseguire più operazioni e mettere in coda l'output](#BKMK_RunMultipleOperations) per gestire la reentrancy.

## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Accesso al Web con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
