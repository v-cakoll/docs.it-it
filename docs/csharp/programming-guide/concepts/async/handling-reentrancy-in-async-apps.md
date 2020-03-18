---
title: Gestione della reentrancy nelle app asincrone (C#)
ms.date: 07/20/2015
ms.assetid: 47c5075e-c448-45ce-9155-ed4e7e98c677
ms.openlocfilehash: 67fbbd294ffe6219b58065f974543b2dd483a92c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451863"
---
# <a name="handling-reentrancy-in-async-apps-c"></a>Gestione della reentrancy nelle app asincrone (C#)

Quando si include codice asincrono nell'applicazione, è consigliabile prevedere ed evitare la reentrancy, ovvero il reinserimento di un'operazione asincrona prima del suo completamento. Se non vengono identificate e gestite le possibilità di reentrancy, esse possono causare risultati imprevisti.

**In questo argomento**

- [Riconoscimento della reentrancy](#BKMK_RecognizingReentrancy)

- [Gestione della rientranza](#BKMK_HandlingReentrancy)

  - [Disabilitare il pulsante Start](#BKMK_DisableTheStartButton)

  - [Annullare e riavviare l'operazione](#BKMK_CancelAndRestart)

  - [Eseguire più operazioni e mettere in coda l'output](#BKMK_RunMultipleOperations)

- [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample)

> [!NOTE]
> Per eseguire l'esempio, è necessario disporre di Visual Studio 2012 o versione successiva e .NET Framework 4.5 o versione successiva nel computer.

> [!NOTE]
> Transport Layer Security (TLS) versione 1.2 è ora la versione minima da usare nello sviluppo dell'app. Se l'app è destinata a una versione di .NET Framework precedente alla 4.7, vedere il seguente articolo per [le procedure consigliate TLS (Transport Layer Security) con .NET Framework.](../../../../framework/network-programming/tls.md)

## <a name="BKMK_RecognizingReentrancy"></a>Riconoscere la rientranza

Nell'esempio riportato in questo argomento viene scelto un pulsante **Start** per avviare un'app asincrona che scarica una serie di siti Web e calcola il numero totale di byte scaricati. Una versione sincrona dell'esempio avrebbe risposto allo stesso modo indipendentemente dal numero di volte che un utente sceglie il pulsante perché, dopo la prima volta, il thread dell'interfaccia utente ignora tali eventi fino al termine dell'esecuzione dell'applicazione. In un'applicazione asincrona, tuttavia, il thread dell'interfaccia utente continua a rispondere e potrebbe essere possibile riattivare l'operazione asincrona prima del suo completamento.

Nell'esempio seguente viene illustrato l'output previsto se l'utente sceglie il pulsante **Start** una sola volta. Viene visualizzato un elenco dei siti Web scaricati con la dimensione, espressa in byte, di ogni sito. Il numero totale di byte viene visualizzato alla fine.

```output
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

```output
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

### <a name="BKMK_DisableTheStartButton"></a>Disattivare il pulsante Start

È possibile bloccare il pulsante **Start** durante l'esecuzione di un'operazione disabilitando il pulsante nella parte superiore del gestore eventi `StartButton_Click`. È possibile riabilitare il pulsante dall'interno un blocco `finally` al termine dell'operazione in modo che gli utenti possano eseguire nuovamente l'applicazione.

Per configurare questo scenario, apportare le modifiche seguenti al codice di base fornito in [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample). È anche possibile scaricare l'app finita da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET). Il nome del progetto è DisableStartButton.

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // This line is commented out to make the results clearer in the output.
    //ResultsTextBox.Text = "";

    // ***Disable the Start button until the downloads are complete.
    StartButton.IsEnabled = false;

    try
    {
        await AccessTheWebAsync();
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.";
    }
    // ***Enable the Start button in case you want to run the program again.
    finally
    {
        StartButton.IsEnabled = true;
    }
}
```

In seguito alle modifiche, il pulsante non risponde mentre `AccessTheWebAsync` sta scaricando i siti Web. Pertanto, il processo non potrà essere riattivato.

### <a name="BKMK_CancelAndRestart"></a> Annullare e riavviare l'operazione

Anziché disabilitare il pulsante **Start**, è possibile tenere attivo il pulsante ma, se l'utente sceglie di nuovo il pulsante, è necessario annullare l'operazione in esecuzione e consentire la continuazione dell'operazione richiesta più di recente.

Per altre informazioni sull'annullamento, vedere [Ottimizzazione dell'app asincrona (C#)](./fine-tuning-your-async-application.md).

Per configurare questo scenario, apportare le modifiche seguenti al codice di base fornito in [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample). È anche possibile scaricare l'app finita da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET). Il nome del progetto è CancelAndRestart.

1. Dichiarare una variabile <xref:System.Threading.CancellationTokenSource>, `cts`, che sia compresa nell'ambito per tutti i metodi.

    ```csharp
    public partial class MainWindow : Window   // Or class MainPage
    {
        // *** Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. In `StartButton_Click` determinare se un'operazione è già in corso. Se il valore di `cts` è Null, nessuna operazione è già attiva. Se il valore non è null, viene annullata l'operazione in esecuzione.

    ```csharp
    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }
    ```

3. Impostare `cts` su un valore diverso che rappresenti il processo corrente.

    ```csharp
    // *** Now set cts to a new value that you can use to cancel the current process
    // if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;
    ```

4. Alla fine di `StartButton_Click`, il processo corrente è completo, quindi impostare il valore di `cts` nuovamente su null.

    ```csharp
    // *** When the process is complete, signal that another process can begin.
    if (cts == newCTS)
        cts = null;
    ```

Il codice seguente illustra tutte le modifiche in `StartButton_Click`. Le aggiunte sono contrassegnate con asterischi.

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // This line is commented out to make the results clearer in the output.
    //ResultsTextBox.Clear();

    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }

    // *** Now set cts to cancel the current process if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;

    try
    {
        // ***Send cts.Token to carry the message if there is a cancellation request.
        await AccessTheWebAsync(cts.Token);

    }
    // *** Catch cancellations separately.
    catch (OperationCanceledException)
    {
        ResultsTextBox.Text += "\r\nDownloads canceled.\r\n";
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.\r\n";
    }
    // *** When the process is complete, signal that another process can proceed.
    if (cts == newCTS)
        cts = null;
}
```

In `AccessTheWebAsync`, apportare le seguenti modifiche.

- Aggiungere un parametro per accettare il token di annullamento da `StartButton_Click`.

- Usare il metodo <xref:System.Net.Http.HttpClient.GetAsync%2A> per scaricare i siti Web, in quanto `GetAsync` accetta un argomento <xref:System.Threading.CancellationToken>.

- Prima di chiamare `DisplayResults` per visualizzare i risultati per ogni sito Web scaricato, controllare `ct` per verificare che l'operazione corrente non sia stata annullata.

Il codice seguente illustra queste modifiche, contrassegnate da asterischi.

```csharp
// *** Provide a parameter for the CancellationToken from StartButton_Click.
async Task AccessTheWebAsync(CancellationToken ct)
{
    // Declare an HttpClient object.
    HttpClient client = new HttpClient();

    // Make a list of web addresses.
    List<string> urlList = SetUpURLList();

    var total = 0;
    var position = 0;

    foreach (var url in urlList)
    {
        // *** Use the HttpClient.GetAsync method because it accepts a
        // cancellation token.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // *** Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // *** Check for cancellations before displaying information about the
        // latest site.
        ct.ThrowIfCancellationRequested();

        DisplayResults(url, urlContents, ++position);

        // Update the total.
        total += urlContents.Length;
    }

    // Display the total count for all of the websites.
    ResultsTextBox.Text +=
        $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
}
```

Se si sceglie il pulsante **Start** più volte durante l'esecuzione di questa app, i risultati generati devono essere simili all'output seguente.

```output
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

### <a name="BKMK_RunMultipleOperations"></a>Esecuzione di più operazioni e accodamento dell'outputRun Multiple Operations and Queue the Output

Il terzo esempio è il più complesso in quanto l'app avvia un'altra operazione asincrona ogni volta che l'utente sceglie il pulsante **Start** e tutte le operazioni vengono eseguite fino al completamento. Tutte le operazioni richieste scaricano i siti Web dall'elenco in modo asincrono, ma l'output delle operazioni viene visualizzato in sequenza. In altre parole, l'attività di download effettiva è di tipo interleaved, come illustrato nell'output in [Riconoscimento della reentrancy](#BKMK_RecognizingReentrancy), ma l'elenco dei risultati per ogni gruppo viene visualizzato separatamente.

Le operazioni condividono un codice <xref:System.Threading.Tasks.Task> globale, `pendingWork`, che funge da gatekeeper per il processo di visualizzazione.

Per configurare questo scenario, apportare le modifiche seguenti al codice di base fornito in [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample). È anche possibile scaricare l'app finita da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET). Il nome del progetto è QueueResults.

Nell'output seguente viene illustrato il risultato restituito quando l'utente sceglie il pulsante **Start** una sola volta. L'etichetta A indica che il risultato fa riferimento alla prima volta che il pulsante **Start** viene scelto. I numeri indicano l'ordine degli URL nell'elenco delle destinazioni di download.

```output
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

```output
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

```csharp
public partial class MainWindow : Window  // Class MainPage in Windows Store app.
{
    // ***Declare the following variables where all methods can access them.
    private Task pendingWork = null;
    private char group = (char)('A' - 1);
```

La variabile `Task`, `pendingWork`, controlla il processo di visualizzazione e impedisce a qualsiasi gruppo di interrompere l'operazione di visualizzazione di un altro gruppo. La variabile di tipo carattere, `group`, etichetta l'output dei vari gruppi per far sì che i risultati vengano visualizzati nell'ordine previsto.

#### <a name="the-click-event-handler"></a>Il gestore eventi Click

Il gestore eventi `StartButton_Click` incrementa la lettera del gruppo ogni volta che l'utente sceglie il pulsante **Start**. Il gestore chiama quindi `AccessTheWebAsync` per eseguire l'operazione di download.

```csharp
private async void StartButton_Click(object sender, RoutedEventArgs e)
{
    // ***Verify that each group's results are displayed together, and that
    // the groups display in order, by marking each group with a letter.
    group = (char)(group + 1);
    ResultsTextBox.Text += $"\r\n\r\n#Starting group {group}.";

    try
    {
        // *** Pass the group value to AccessTheWebAsync.
        char finishedGroup = await AccessTheWebAsync(group);

        // The following line verifies a successful return from the download and
        // display procedures.
        ResultsTextBox.Text += $"\r\n\r\n#Group {finishedGroup} is complete.\r\n";
    }
    catch (Exception)
    {
        ResultsTextBox.Text += "\r\nDownloads failed.";
    }
}
```

#### <a name="the-accessthewebasync-method"></a>Il metodo AccessTheWebAsync

Questo esempio suddivide `AccessTheWebAsync` in due metodi. Il primo metodo, `AccessTheWebAsync`, avvia tutte le attività di download per un gruppo e configura `pendingWork` per il controllo del processo di visualizzazione. Il metodo usa una query LINQ (Language Integrated Query) e <xref:System.Linq.Enumerable.ToArray%2A> per avviare tutte le attività di download contemporaneamente.

`AccessTheWebAsync` quindi chiama `FinishOneGroupAsync` per attendere il completamento di ogni download e visualizzare la relativa lunghezza.

`FinishOneGroupAsync` restituisce un'attività assegnata a `pendingWork` in `AccessTheWebAsync`. Tale valore impedisce l'interruzione da parte di un'altra operazione prima del completamento dell'attività.

```csharp
private async Task<char> AccessTheWebAsync(char grp)
{
    HttpClient client = new HttpClient();

    // Make a list of the web addresses to download.
    List<string> urlList = SetUpURLList();

    // ***Kick off the downloads. The application of ToArray activates all the download tasks.
    Task<byte[]>[] getContentTasks = urlList.Select(url => client.GetByteArrayAsync(url)).ToArray();

    // ***Call the method that awaits the downloads and displays the results.
    // Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp);

    ResultsTextBox.Text += $"\r\n#Task assigned for group {grp}. Download tasks are active.\r\n";

    // ***This task is complete when a group has finished downloading and displaying.
    await pendingWork;

    // You can do other work here or just return.
    return grp;
}
```

#### <a name="the-finishonegroupasync-method"></a>Il metodo FinishOneGroupAsync

Questo metodo consente di scorrere le attività di download in reciproca attesa in un gruppo, nonché visualizza la lunghezza del sito Web scaricato e aggiunge la lunghezza al totale.

La prima istruzione in `FinishOneGroupAsync` usa `pendingWork` per assicurarsi che l'uso del metodo non interferisca con un'operazione già presente nel processo di visualizzazione o in attesa. Se tale operazione è in corso, l'operazione di attivazione deve attendere il suo turno.

```csharp
private async Task FinishOneGroupAsync(List<string> urls, Task<byte[]>[] contentTasks, char grp)
{
    // ***Wait for the previous group to finish displaying results.
    if (pendingWork != null) await pendingWork;

    int total = 0;

    // contentTasks is the array of Tasks that was created in AccessTheWebAsync.
    for (int i = 0; i < contentTasks.Length; i++)
    {
        // Await the download of a particular URL, and then display the URL and
        // its length.
        byte[] content = await contentTasks[i];
        DisplayResults(urls[i], content, i, grp);
        total += content.Length;
    }

    // Display the total count for all of the websites.
    ResultsTextBox.Text +=
        $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
}
```

#### <a name="points-of-interest"></a>Punti di interesse

Le righe di informazioni che iniziano con un segno di cancelletto (#) nell'output descrivono il funzionamento dell'esempio.

L'output mostra i modelli seguenti.

- Un gruppo può essere avviato anche se un gruppo precedente è visualizzato nel relativo output, ma la visualizzazione dell'output del gruppo precedente non viene interrotta.

    ```output
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

- L'attività `pendingWork` è Null all'inizio di `FinishOneGroupAsync` solo per il gruppo A, che viene avviato per primo. Il gruppo A non ha ancora completato un'espressione await quando raggiunge `FinishOneGroupAsync`. Pertanto, il controllo non è stato restituito a `AccessTheWebAsync` e non è stata eseguita la prima assegnazione a `pendingWork`.

- Le due righe seguenti sono sempre visualizzate insieme nell'output. Il codice non viene mai interrotto tra l'avvio dell'operazione di un gruppo in `StartButton_Click` e l'assegnazione di un'attività per il gruppo a `pendingWork`.

    ```output
    #Starting group B.
    #Task assigned for group B. Download tasks are active.
    ```

    Dopo che un gruppo entra in `StartButton_Click`, l'operazione non completa un'espressione await fino a quando l'operazione non entra in `FinishOneGroupAsync`. Pertanto, nessuna operazione può assumere il controllo durante l'esecuzione di tale segmento di codice.

## <a name="BKMD_SettingUpTheExample"></a>Revisione ed esecuzione dell'app di esempio

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

3. Nel riquadro **Modelli installati** espandere **Visual C#** e selezionare **Windows**.

4. Dall'elenco dei tipi di progetto scegliere **Applicazione WPF**.

5. Denominare `WebsiteDownloadWPF`il progetto , scegliere .NET Framework versione 4.6 o successiva e quindi fare clic sul pulsante **OK** .

     Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.

6. Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .

     Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow.xaml in **Esplora soluzioni** e scegliere **Visualizza codice**.

7. Nella visualizzazione **XAML** di MainWindow.xaml sostituire il codice con quello riportato di seguito.

    ```csharp
    <Window x:Class="WebsiteDownloadWPF.MainWindow"
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

8. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Riferimenti** e scegliere **Aggiungi riferimento**.

     Aggiungere un <xref:System.Net.Http>riferimento per , se non è già selezionato.

9. In **Esplora soluzioni** aprire il menu di scelta rapida per MainWindow.xaml.cs e scegliere **Visualizza codice**.

10. Sostituire il codice in MainWindow.xaml.cs con quello riportato di seguito.

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows;
    using System.Windows.Controls;
    using System.Windows.Data;
    using System.Windows.Documents;
    using System.Windows.Input;
    using System.Windows.Media;
    using System.Windows.Media.Imaging;
    using System.Windows.Navigation;
    using System.Windows.Shapes;

    // Add the following using directives, and add a reference for System.Net.Http.
    using System.Net.Http;
    using System.Threading;

    namespace WebsiteDownloadWPF
    {
        public partial class MainWindow : Window
        {
            public MainWindow()
            {
                System.Net.ServicePointManager.SecurityProtocol |= System.Net.SecurityProtocolType.Tls12;
                InitializeComponent();
            }

            private async void StartButton_Click(object sender, RoutedEventArgs e)
            {
                // This line is commented out to make the results clearer in the output.
                //ResultsTextBox.Text = "";

                try
                {
                    await AccessTheWebAsync();
                }
                catch (Exception)
                {
                    ResultsTextBox.Text += "\r\nDownloads failed.";
                }
            }

            private async Task AccessTheWebAsync()
            {
                // Declare an HttpClient object.
                HttpClient client = new HttpClient();

                // Make a list of web addresses.
                List<string> urlList = SetUpURLList();

                var total = 0;
                var position = 0;

                foreach (var url in urlList)
                {
                    // GetByteArrayAsync returns a task. At completion, the task
                    // produces a byte array.
                    byte[] urlContents = await client.GetByteArrayAsync(url);

                    DisplayResults(url, urlContents, ++position);

                    // Update the total.
                    total += urlContents.Length;
                }

                // Display the total count for all of the websites.
                ResultsTextBox.Text +=
                    $"\r\n\r\nTOTAL bytes returned:  {total}\r\n";
            }

            private List<string> SetUpURLList()
            {
                List<string> urls = new List<string>
                {
                    "https://msdn.microsoft.com/library/hh191443.aspx",
                    "https://msdn.microsoft.com/library/aa578028.aspx",
                    "https://msdn.microsoft.com/library/jj155761.aspx",
                    "https://msdn.microsoft.com/library/hh290140.aspx",
                    "https://msdn.microsoft.com/library/hh524395.aspx",
                    "https://msdn.microsoft.com/library/ms404677.aspx",
                    "https://msdn.microsoft.com",
                    "https://msdn.microsoft.com/library/ff730837.aspx"
                };
                return urls;
            }

            private void DisplayResults(string url, byte[] content, int pos)
            {
                // Display the length of each website. The string format is designed
                // to be used with a monospaced font, such as Lucida Console or
                // Global Monospace.

                // Strip off the "https://".
                var displayURL = url.Replace("https://", "");
                // Display position in the URL list, the URL, and the number of bytes.
                ResultsTextBox.Text += $"\n{pos}. {displayURL,-58} {content.Length,8}";
            }
        }
    }
    ```

11. Premere CTRL+F5 per eseguire il programma e scegliere il pulsante **Start** più volte.

12. Apportare le modifiche descritte in [Disabilitare il pulsante Start](#BKMK_DisableTheStartButton), [Annullare e riavviare l'operazione](#BKMK_CancelAndRestart) o [Eseguire più operazioni e mettere in coda l'output](#BKMK_RunMultipleOperations) per gestire la reentrancy.

## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: accesso al Web tramite async e await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Programmazione asincrona con async e await (C#)](./index.md)
