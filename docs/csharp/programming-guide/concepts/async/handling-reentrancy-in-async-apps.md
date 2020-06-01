---
title: Gestione della reentrancy nelle app asincrone (C#)
ms.date: 07/20/2015
ms.assetid: 47c5075e-c448-45ce-9155-ed4e7e98c677
ms.openlocfilehash: e03e0f6ecd8e74dd8518f84ec03c76c1ef5b9ee6
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241812"
---
# <a name="handling-reentrancy-in-async-apps-c"></a><span data-ttu-id="2c1a2-102">Gestione della reentrancy nelle app asincrone (C#)</span><span class="sxs-lookup"><span data-stu-id="2c1a2-102">Handling Reentrancy in Async Apps (C#)</span></span>

<span data-ttu-id="2c1a2-103">Quando si include codice asincrono nell'applicazione, è consigliabile prevedere ed evitare la reentrancy, ovvero il reinserimento di un'operazione asincrona prima del suo completamento.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-103">When you include asynchronous code in your app, you should consider and possibly prevent reentrancy, which refers to reentering an asynchronous operation before it has completed.</span></span> <span data-ttu-id="2c1a2-104">Se non vengono identificate e gestite le possibilità di reentrancy, esse possono causare risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-104">If you don't identify and handle possibilities for reentrancy, it can cause unexpected results.</span></span>

<span data-ttu-id="2c1a2-105">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="2c1a2-105">**In this topic**</span></span>

- [<span data-ttu-id="2c1a2-106">Riconoscimento della reentrancy</span><span class="sxs-lookup"><span data-stu-id="2c1a2-106">Recognizing Reentrancy</span></span>](#BKMK_RecognizingReentrancy)

- [<span data-ttu-id="2c1a2-107">Gestione della rientranza</span><span class="sxs-lookup"><span data-stu-id="2c1a2-107">Handling Reentrancy</span></span>](#BKMK_HandlingReentrancy)

  - [<span data-ttu-id="2c1a2-108">Disabilitare il pulsante Start</span><span class="sxs-lookup"><span data-stu-id="2c1a2-108">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  - [<span data-ttu-id="2c1a2-109">Annulla e riavvia l'operazione</span><span class="sxs-lookup"><span data-stu-id="2c1a2-109">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  - [<span data-ttu-id="2c1a2-110">Eseguire più operazioni e mettere in coda l'output</span><span class="sxs-lookup"><span data-stu-id="2c1a2-110">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

- [<span data-ttu-id="2c1a2-111">Revisione ed esecuzione dell'app di esempio</span><span class="sxs-lookup"><span data-stu-id="2c1a2-111">Reviewing and Running the Example App</span></span>](#BKMD_SettingUpTheExample)

> [!NOTE]
> <span data-ttu-id="2c1a2-112">Per eseguire l'esempio, è necessario che nel computer sia installato Visual Studio 2012 o versione successiva e .NET Framework 4,5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-112">To run the example, you must have Visual Studio 2012 or newer and .NET Framework 4.5 or newer installed on your computer.</span></span>

> [!NOTE]
> <span data-ttu-id="2c1a2-113">Transport Layer Security (TLS) versione 1,2 è ora la versione minima da usare nello sviluppo di app.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-113">Transport Layer Security (TLS) version 1.2 is now the minimum version to use in your app development.</span></span> <span data-ttu-id="2c1a2-114">Se l'app è destinata a una versione .NET Framework precedente alla 4,7, vedere l'articolo seguente per le [procedure consigliate per Transport Layer Security (TLS) con .NET Framework](../../../../framework/network-programming/tls.md).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-114">If your app targets a .NET Framework version earlier than 4.7, refer to the following article for [Transport Layer Security (TLS) best practices with .NET Framework](../../../../framework/network-programming/tls.md).</span></span>

## <a name="recognizing-reentrancy"></a><a name="BKMK_RecognizingReentrancy"></a><span data-ttu-id="2c1a2-115">Riconoscimento della rientranza</span><span class="sxs-lookup"><span data-stu-id="2c1a2-115">Recognizing Reentrancy</span></span>

<span data-ttu-id="2c1a2-116">Nell'esempio riportato in questo argomento viene scelto un pulsante **Start** per avviare un'app asincrona che scarica una serie di siti Web e calcola il numero totale di byte scaricati.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-116">In the example in this topic, users choose a **Start** button to initiate an asynchronous app that downloads a series of websites and calculates the total number of bytes that are downloaded.</span></span> <span data-ttu-id="2c1a2-117">Una versione sincrona dell'esempio avrebbe risposto allo stesso modo indipendentemente dal numero di volte che un utente sceglie il pulsante perché, dopo la prima volta, il thread dell'interfaccia utente ignora tali eventi fino al termine dell'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-117">A synchronous version of the example would respond the same way regardless of how many times a user chooses the button because, after the first time, the UI thread ignores those events until the app finishes running.</span></span> <span data-ttu-id="2c1a2-118">In un'applicazione asincrona, tuttavia, il thread dell'interfaccia utente continua a rispondere e potrebbe essere possibile riattivare l'operazione asincrona prima del suo completamento.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-118">In an asynchronous app, however, the UI thread continues to respond, and you might reenter the asynchronous operation before it has completed.</span></span>

<span data-ttu-id="2c1a2-119">Nell'esempio seguente viene illustrato l'output previsto se l'utente sceglie il pulsante **Start** una sola volta.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-119">The following example shows the expected output if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="2c1a2-120">Viene visualizzato un elenco dei siti Web scaricati con la dimensione, espressa in byte, di ogni sito.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-120">A list of the downloaded websites appears with the size, in bytes, of each site.</span></span> <span data-ttu-id="2c1a2-121">Il numero totale di byte viene visualizzato alla fine.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-121">The total number of bytes appears at the end.</span></span>

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

<span data-ttu-id="2c1a2-122">Tuttavia, se l'utente sceglie il pulsante più volte, il gestore eventi viene chiamato più volte e il processo di download viene riattivato ogni volta.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-122">However, if the user chooses the button more than once, the event handler is invoked repeatedly, and the download process is reentered each time.</span></span> <span data-ttu-id="2c1a2-123">Di conseguenza, diverse operazioni asincrone sono in esecuzione contemporaneamente, l'output si sovrappone ai risultati e il numero totale di byte è poco chiaro.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-123">As a result, several asynchronous operations are running at the same time, the output interleaves the results, and the total number of bytes is confusing.</span></span>

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

<span data-ttu-id="2c1a2-124">È possibile esaminare il codice che genera l'output andando alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-124">You can review the code that produces this output by scrolling to the end of this topic.</span></span> <span data-ttu-id="2c1a2-125">È possibile provare il codice scaricando la soluzione nel computer locale ed eseguendo il progetto WebsiteDownload oppure usando il codice alla fine di questo argomento per creare un progetto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-125">You can experiment with the code by downloading the solution to your local computer and then running the WebsiteDownload project or by using the code at the end of this topic to create your own project.</span></span> <span data-ttu-id="2c1a2-126">Per altre informazioni e istruzioni, vedere [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-126">For more information and instructions, see [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span>

## <a name="handling-reentrancy"></a><a name="BKMK_HandlingReentrancy"></a> <span data-ttu-id="2c1a2-127">Gestione della reentrancy</span><span class="sxs-lookup"><span data-stu-id="2c1a2-127">Handling Reentrancy</span></span>

<span data-ttu-id="2c1a2-128">È possibile gestire la reentrancy in diversi modi, a seconda delle operazioni che si desidera che l'applicazione esegua.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-128">You can handle reentrancy in a variety of ways, depending on what you want your app to do.</span></span> <span data-ttu-id="2c1a2-129">In questo argomento vengono illustrati gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c1a2-129">This topic presents the following examples:</span></span>

- [<span data-ttu-id="2c1a2-130">Disabilitare il pulsante Start</span><span class="sxs-lookup"><span data-stu-id="2c1a2-130">Disable the Start Button</span></span>](#BKMK_DisableTheStartButton)

  <span data-ttu-id="2c1a2-131">Disabilitare il pulsante **Start** mentre l'operazione è in esecuzione in modo che l'utente non la interrompa.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-131">Disable the **Start** button while the operation is running so that the user can't interrupt it.</span></span>

- [<span data-ttu-id="2c1a2-132">Annulla e riavvia l'operazione</span><span class="sxs-lookup"><span data-stu-id="2c1a2-132">Cancel and Restart the Operation</span></span>](#BKMK_CancelAndRestart)

  <span data-ttu-id="2c1a2-133">Annullare le operazioni ancora in esecuzione quando l'utente sceglie di nuovo il pulsante **Start** e consentire la continuazione dell'operazione richiesta più di recente.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-133">Cancel any operation that is still running when the user chooses the **Start** button again, and then let the most recently requested operation continue.</span></span>

- [<span data-ttu-id="2c1a2-134">Eseguire più operazioni e mettere in coda l'output</span><span class="sxs-lookup"><span data-stu-id="2c1a2-134">Run Multiple Operations and Queue the Output</span></span>](#BKMK_RunMultipleOperations)

  <span data-ttu-id="2c1a2-135">Consentire l'esecuzione asincrona di tutte le operazioni richieste, ma coordinare la visualizzazione dell'output in modo che vengano visualizzati i risultati di ogni operazione tutti insieme e ordinati.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-135">Allow all requested operations to run asynchronously, but coordinate the display of output so that the results from each operation appear together and in order.</span></span>

### <a name="disable-the-start-button"></a><a name="BKMK_DisableTheStartButton"></a><span data-ttu-id="2c1a2-136">Disabilitare il pulsante Start</span><span class="sxs-lookup"><span data-stu-id="2c1a2-136">Disable the Start Button</span></span>

<span data-ttu-id="2c1a2-137">È possibile bloccare il pulsante **Start** durante l'esecuzione di un'operazione disabilitando il pulsante nella parte superiore del gestore eventi `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-137">You can block the **Start** button while an operation is running by disabling the button at the top of the `StartButton_Click` event handler.</span></span> <span data-ttu-id="2c1a2-138">È possibile riabilitare il pulsante dall'interno un blocco `finally` al termine dell'operazione in modo che gli utenti possano eseguire nuovamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-138">You can then reenable the button from within a  `finally` block when the operation finishes so that users can run the app again.</span></span>

<span data-ttu-id="2c1a2-139">Per configurare questo scenario, apportare le modifiche seguenti al codice di base fornito in [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-139">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="2c1a2-140">È anche possibile scaricare l'app finita da [esempi asincroni: rientranza nelle app desktop .NET](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-140">You can also download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="2c1a2-141">Il nome del progetto è DisableStartButton.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-141">The name of the project is DisableStartButton.</span></span>

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

<span data-ttu-id="2c1a2-142">In seguito alle modifiche, il pulsante non risponde mentre `AccessTheWebAsync` sta scaricando i siti Web, pertanto il processo non può essere nuovamente immesso.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-142">As a result of the changes, the button doesn't respond while `AccessTheWebAsync` is downloading the websites, so the process can't be reentered.</span></span>

### <a name="cancel-and-restart-the-operation"></a><a name="BKMK_CancelAndRestart"></a> <span data-ttu-id="2c1a2-143">Annullare e riavviare l'operazione</span><span class="sxs-lookup"><span data-stu-id="2c1a2-143">Cancel and Restart the Operation</span></span>

<span data-ttu-id="2c1a2-144">Anziché disabilitare il pulsante **Start**, è possibile tenere attivo il pulsante ma, se l'utente sceglie di nuovo il pulsante, è necessario annullare l'operazione in esecuzione e consentire la continuazione dell'operazione richiesta più di recente.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-144">Instead of disabling the **Start** button, you can keep the button active but, if the user chooses that button again, cancel the operation that's already running and let the most recently started operation continue.</span></span>

<span data-ttu-id="2c1a2-145">Per altre informazioni sull'annullamento, vedere [Ottimizzazione dell'app asincrona (C#)](./fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-145">For more information about cancellation, see [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="2c1a2-146">Per configurare questo scenario, apportare le modifiche seguenti al codice di base fornito in [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-146">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="2c1a2-147">È anche possibile scaricare l'app finita da [esempi asincroni: rientranza nelle app desktop .NET](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-147">You can also download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="2c1a2-148">Il nome del progetto è CancelAndRestart.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-148">The name of the project is CancelAndRestart.</span></span>

1. <span data-ttu-id="2c1a2-149">Dichiarare una <xref:System.Threading.CancellationTokenSource> variabile, `cts` , che rientra nell'ambito di tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-149">Declare a <xref:System.Threading.CancellationTokenSource> variable, `cts`, that's in scope for all methods.</span></span>

    ```csharp
    public partial class MainWindow : Window   // Or class MainPage
    {
        // *** Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. <span data-ttu-id="2c1a2-150">In `StartButton_Click` determinare se un'operazione è già in corso.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-150">In `StartButton_Click`, determine whether an operation is already underway.</span></span> <span data-ttu-id="2c1a2-151">Se il valore di `cts` è Null, nessuna operazione è già attiva.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-151">If the value of `cts` is null, no operation is already active.</span></span> <span data-ttu-id="2c1a2-152">Se il valore non è null, viene annullata l'operazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-152">If the value isn't null, the operation that is already running is canceled.</span></span>

    ```csharp
    // *** If a download process is already underway, cancel it.
    if (cts != null)
    {
        cts.Cancel();
    }
    ```

3. <span data-ttu-id="2c1a2-153">Impostare `cts` su un valore diverso che rappresenti il processo corrente.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-153">Set `cts` to a different value that represents the current process.</span></span>

    ```csharp
    // *** Now set cts to a new value that you can use to cancel the current process
    // if the button is chosen again.
    CancellationTokenSource newCTS = new CancellationTokenSource();
    cts = newCTS;
    ```

4. <span data-ttu-id="2c1a2-154">Alla fine di `StartButton_Click`, il processo corrente è completo, quindi impostare il valore di `cts` nuovamente su null.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-154">At the end of `StartButton_Click`, the current process is complete, so set the value of `cts` back to null.</span></span>

    ```csharp
    // *** When the process is complete, signal that another process can begin.
    if (cts == newCTS)
        cts = null;
    ```

<span data-ttu-id="2c1a2-155">Il codice seguente illustra tutte le modifiche in `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-155">The following code shows all the changes in `StartButton_Click`.</span></span> <span data-ttu-id="2c1a2-156">Le aggiunte sono contrassegnate con asterischi.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-156">The additions are marked with asterisks.</span></span>

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

<span data-ttu-id="2c1a2-157">In `AccessTheWebAsync`, apportare le seguenti modifiche.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-157">In `AccessTheWebAsync`, make the following changes.</span></span>

- <span data-ttu-id="2c1a2-158">Aggiungere un parametro per accettare il token di annullamento da `StartButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-158">Add a parameter to accept the cancellation token from `StartButton_Click`.</span></span>

- <span data-ttu-id="2c1a2-159">Usare il metodo <xref:System.Net.Http.HttpClient.GetAsync%2A> per scaricare i siti Web, in quanto `GetAsync` accetta un argomento <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-159">Use the <xref:System.Net.Http.HttpClient.GetAsync%2A> method to download the websites because `GetAsync` accepts a <xref:System.Threading.CancellationToken> argument.</span></span>

- <span data-ttu-id="2c1a2-160">Prima di chiamare `DisplayResults` per visualizzare i risultati per ogni sito Web scaricato, controllare `ct` per verificare che l'operazione corrente non sia stata annullata.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-160">Before calling `DisplayResults` to display the results for each downloaded website, check `ct` to verify that the current operation hasn't been canceled.</span></span>

<span data-ttu-id="2c1a2-161">Il codice seguente illustra queste modifiche, contrassegnate da asterischi.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-161">The following code shows these changes, which are marked with asterisks.</span></span>

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

<span data-ttu-id="2c1a2-162">Se si sceglie il pulsante **Start** più volte durante l'esecuzione di questa app, i risultati generati devono essere simili all'output seguente.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-162">If you choose the **Start** button several times while this app is running, it should produce results that resemble the following output.</span></span>

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

<span data-ttu-id="2c1a2-163">Per eliminare gli elenchi parziali, rimuovere la prima riga di codice in `StartButton_Click` per cancellare la casella di testo ogni volta che l'utente riavvia l'operazione.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-163">To eliminate the partial lists, uncomment the first line of code in `StartButton_Click` to clear the text box each time the user restarts the operation.</span></span>

### <a name="run-multiple-operations-and-queue-the-output"></a><a name="BKMK_RunMultipleOperations"></a><span data-ttu-id="2c1a2-164">Eseguire più operazioni e accodare l'output</span><span class="sxs-lookup"><span data-stu-id="2c1a2-164">Run Multiple Operations and Queue the Output</span></span>

<span data-ttu-id="2c1a2-165">Il terzo esempio è il più complesso in quanto l'app avvia un'altra operazione asincrona ogni volta che l'utente sceglie il pulsante **Start** e tutte le operazioni vengono eseguite fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-165">This third example is the most complicated in that the app starts another asynchronous operation each time that the user chooses the **Start** button, and all the operations run to completion.</span></span> <span data-ttu-id="2c1a2-166">Tutte le operazioni richieste scaricano i siti Web dall'elenco in modo asincrono, ma l'output delle operazioni viene visualizzato in sequenza.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-166">All the requested operations download websites from the list asynchronously, but the output from the operations is presented sequentially.</span></span> <span data-ttu-id="2c1a2-167">In altre parole, l'attività di download effettiva è di tipo interleaved, come illustrato nell'output in [Riconoscimento della reentrancy](#BKMK_RecognizingReentrancy), ma l'elenco dei risultati per ogni gruppo viene visualizzato separatamente.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-167">That is, the actual downloading activity is interleaved, as the output in [Recognizing Reentrancy](#BKMK_RecognizingReentrancy) shows, but the list of results for each group is presented separately.</span></span>

<span data-ttu-id="2c1a2-168">Le operazioni condividono un codice <xref:System.Threading.Tasks.Task> globale, `pendingWork`, che funge da gatekeeper per il processo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-168">The operations share a global <xref:System.Threading.Tasks.Task>, `pendingWork`, which serves as a gatekeeper for the display process.</span></span>

<span data-ttu-id="2c1a2-169">Per configurare questo scenario, apportare le modifiche seguenti al codice di base fornito in [Revisione ed esecuzione dell'app di esempio](#BKMD_SettingUpTheExample).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-169">To set up this scenario, make the following changes to the basic code that is provided in [Reviewing and Running the Example App](#BKMD_SettingUpTheExample).</span></span> <span data-ttu-id="2c1a2-170">È anche possibile scaricare l'app finita da [esempi asincroni: rientranza nelle app desktop .NET](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-170">You can also download the finished app from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span> <span data-ttu-id="2c1a2-171">Il nome del progetto è QueueResults.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-171">The name of the project is QueueResults.</span></span>

<span data-ttu-id="2c1a2-172">Nell'output seguente viene illustrato il risultato restituito quando l'utente sceglie il pulsante **Start** una sola volta.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-172">The following output shows the result if the user chooses the **Start** button only once.</span></span> <span data-ttu-id="2c1a2-173">L'etichetta A indica che il risultato fa riferimento alla prima volta che il pulsante **Start** viene scelto.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-173">The letter label, A, indicates that the result is from the first time the **Start** button is chosen.</span></span> <span data-ttu-id="2c1a2-174">I numeri indicano l'ordine degli URL nell'elenco delle destinazioni di download.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-174">The numbers show the order of the URLs in the list of download targets.</span></span>

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

<span data-ttu-id="2c1a2-175">Se l'utente sceglie il pulsante **Start** tre volte, l'app genera un output simile alle righe seguenti.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-175">If the user chooses the **Start** button three times, the app produces output that resembles the following lines.</span></span> <span data-ttu-id="2c1a2-176">Le righe di informazioni che iniziano con un cancelletto (#) tengono traccia dello stato di avanzamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-176">The information lines that start with a pound sign (#) trace the progress of the application.</span></span>

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

<span data-ttu-id="2c1a2-177">I gruppi B e C vengono avviati prima del completamento del gruppo A, ma l'output per ogni gruppo viene visualizzato separatamente.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-177">Groups B and C start before group A has finished, but the output for the each group appears separately.</span></span> <span data-ttu-id="2c1a2-178">Viene prima visualizzato l'intero output del gruppo A, seguito dall'intero output del gruppo B e dall'intero output del gruppo C. L'app visualizza sempre i gruppi nell'ordine e, per ogni gruppo, visualizza sempre le informazioni sui singoli siti Web in base all'ordine in cui i relativi URL sono visualizzati nell'elenco di URL.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-178">All the output for group A appears first, followed by all the output for group B, and then all the output for group C. The app always displays the groups in order and, for each group, always displays the information about the individual websites in the order that the URLs appear in the list of URLs.</span></span>

<span data-ttu-id="2c1a2-179">Tuttavia, è possibile prevedere l'ordine in cui vengono eseguiti i download.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-179">However, you can't predict the order in which the downloads actually happen.</span></span> <span data-ttu-id="2c1a2-180">Dopo l'avvio di più gruppi, tutte le attività di download generate sono attive.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-180">After multiple groups have been started, the download tasks that they generate are all active.</span></span> <span data-ttu-id="2c1a2-181">Non è possibile presupporre che A-1 venga scaricato prima di B-1 e che A-1 venga scaricato prima A 2.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-181">You can't assume that A-1 will be downloaded before B-1, and you can't assume that A-1 will be downloaded before A-2.</span></span>

#### <a name="global-definitions"></a><span data-ttu-id="2c1a2-182">Definizioni globali</span><span class="sxs-lookup"><span data-stu-id="2c1a2-182">Global Definitions</span></span>

<span data-ttu-id="2c1a2-183">Il codice di esempio contiene le seguenti dichiarazioni globali visibili da tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-183">The sample code contains the following two global declarations that are visible from all methods.</span></span>

```csharp
public partial class MainWindow : Window  // Class MainPage in Windows Store app.
{
    // ***Declare the following variables where all methods can access them.
    private Task pendingWork = null;
    private char group = (char)('A' - 1);
```

<span data-ttu-id="2c1a2-184">La variabile `Task`, `pendingWork`, controlla il processo di visualizzazione e impedisce a qualsiasi gruppo di interrompere l'operazione di visualizzazione di un altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-184">The `Task` variable, `pendingWork`, oversees the display process and prevents any group from interrupting another group's display operation.</span></span> <span data-ttu-id="2c1a2-185">La variabile di tipo carattere, `group`, etichetta l'output dei vari gruppi per far sì che i risultati vengano visualizzati nell'ordine previsto.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-185">The character variable, `group`, labels the output from different groups to verify that results appear in the expected order.</span></span>

#### <a name="the-click-event-handler"></a><span data-ttu-id="2c1a2-186">Il gestore eventi Click</span><span class="sxs-lookup"><span data-stu-id="2c1a2-186">The Click Event Handler</span></span>

<span data-ttu-id="2c1a2-187">Il gestore eventi `StartButton_Click` incrementa la lettera del gruppo ogni volta che l'utente sceglie il pulsante **Start**.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-187">The event handler, `StartButton_Click`, increments the group letter each time the user chooses the **Start** button.</span></span> <span data-ttu-id="2c1a2-188">Il gestore chiama quindi `AccessTheWebAsync` per eseguire l'operazione di download.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-188">Then the handler calls `AccessTheWebAsync` to run the downloading operation.</span></span>

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

#### <a name="the-accessthewebasync-method"></a><span data-ttu-id="2c1a2-189">Il metodo AccessTheWebAsync</span><span class="sxs-lookup"><span data-stu-id="2c1a2-189">The AccessTheWebAsync Method</span></span>

<span data-ttu-id="2c1a2-190">Questo esempio suddivide `AccessTheWebAsync` in due metodi.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-190">This example splits `AccessTheWebAsync` into two methods.</span></span> <span data-ttu-id="2c1a2-191">Il primo metodo, `AccessTheWebAsync`, avvia tutte le attività di download per un gruppo e configura `pendingWork` per il controllo del processo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-191">The first method, `AccessTheWebAsync`, starts all the download tasks for a group and sets up `pendingWork` to control the display process.</span></span> <span data-ttu-id="2c1a2-192">Il metodo usa una query LINQ (Language Integrated Query) e <xref:System.Linq.Enumerable.ToArray%2A> per avviare tutte le attività di download contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-192">The method uses a Language Integrated Query (LINQ query) and <xref:System.Linq.Enumerable.ToArray%2A> to start all the download tasks at the same time.</span></span>

<span data-ttu-id="2c1a2-193">`AccessTheWebAsync` quindi chiama `FinishOneGroupAsync` per attendere il completamento di ogni download e visualizzare la relativa lunghezza.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-193">`AccessTheWebAsync` then calls `FinishOneGroupAsync` to await the completion of each download and display its length.</span></span>

<span data-ttu-id="2c1a2-194">`FinishOneGroupAsync` restituisce un'attività assegnata a `pendingWork` in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-194">`FinishOneGroupAsync` returns a task that's assigned to `pendingWork` in `AccessTheWebAsync`.</span></span> <span data-ttu-id="2c1a2-195">Tale valore impedisce l'interruzione da parte di un'altra operazione prima del completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-195">That value prevents interruption by another operation before the task is complete.</span></span>

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

#### <a name="the-finishonegroupasync-method"></a><span data-ttu-id="2c1a2-196">Il metodo FinishOneGroupAsync</span><span class="sxs-lookup"><span data-stu-id="2c1a2-196">The FinishOneGroupAsync Method</span></span>

<span data-ttu-id="2c1a2-197">Questo metodo consente di scorrere le attività di download in reciproca attesa in un gruppo, nonché visualizza la lunghezza del sito Web scaricato e aggiunge la lunghezza al totale.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-197">This method cycles through the download tasks in a group, awaiting each one, displaying the length of the downloaded website, and adding the length to the total.</span></span>

<span data-ttu-id="2c1a2-198">La prima istruzione in `FinishOneGroupAsync` usa `pendingWork` per assicurarsi che l'uso del metodo non interferisca con un'operazione già presente nel processo di visualizzazione o in attesa.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-198">The first statement in `FinishOneGroupAsync` uses `pendingWork` to make sure that entering the method doesn't interfere with an operation that is already in the display process or that's already waiting.</span></span> <span data-ttu-id="2c1a2-199">Se tale operazione è in corso, l'operazione di attivazione deve attendere il suo turno.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-199">If such an operation is in progress, the entering operation must wait its turn.</span></span>

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

#### <a name="points-of-interest"></a><span data-ttu-id="2c1a2-200">Punti di interesse</span><span class="sxs-lookup"><span data-stu-id="2c1a2-200">Points of Interest</span></span>

<span data-ttu-id="2c1a2-201">Le righe di informazioni che iniziano con un segno di cancelletto (#) nell'output descrivono il funzionamento dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-201">The information lines that start with a pound sign (#) in the output clarify how this example works.</span></span>

<span data-ttu-id="2c1a2-202">L'output mostra i modelli seguenti.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-202">The output shows the following patterns.</span></span>

- <span data-ttu-id="2c1a2-203">Un gruppo può essere avviato anche se un gruppo precedente è visualizzato nel relativo output, ma la visualizzazione dell'output del gruppo precedente non viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-203">A group can be started while a previous group is displaying its output, but the display of the previous group's output isn't interrupted.</span></span>

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

- <span data-ttu-id="2c1a2-204">L'attività `pendingWork` è Null all'inizio di `FinishOneGroupAsync` solo per il gruppo A, che viene avviato per primo.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-204">The `pendingWork` task is null  at the start of `FinishOneGroupAsync` only for group A, which started first.</span></span> <span data-ttu-id="2c1a2-205">Il gruppo A non ha ancora completato un'espressione await quando raggiunge `FinishOneGroupAsync` .</span><span class="sxs-lookup"><span data-stu-id="2c1a2-205">Group A hasn't yet completed an await expression when it reaches `FinishOneGroupAsync`.</span></span> <span data-ttu-id="2c1a2-206">Pertanto, il controllo non è stato restituito a `AccessTheWebAsync` e non è stata eseguita la prima assegnazione a `pendingWork`.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-206">Therefore, control hasn't returned to `AccessTheWebAsync`, and the first assignment to `pendingWork` hasn't occurred.</span></span>

- <span data-ttu-id="2c1a2-207">Le due righe seguenti sono sempre visualizzate insieme nell'output.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-207">The following two lines always appear together in the output.</span></span> <span data-ttu-id="2c1a2-208">Il codice non viene mai interrotto tra l'avvio dell'operazione di un gruppo in `StartButton_Click` e l'assegnazione di un'attività per il gruppo a `pendingWork`.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-208">The code is never interrupted between starting a group's operation in `StartButton_Click` and assigning a task for the group to `pendingWork`.</span></span>

    ```output
    #Starting group B.
    #Task assigned for group B. Download tasks are active.
    ```

    <span data-ttu-id="2c1a2-209">Dopo che un gruppo entra in `StartButton_Click`, l'operazione non completa un'espressione await fino a quando l'operazione non entra in `FinishOneGroupAsync`.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-209">After a group enters `StartButton_Click`, the operation doesn't complete an await expression until the operation enters `FinishOneGroupAsync`.</span></span> <span data-ttu-id="2c1a2-210">Pertanto, nessuna operazione può assumere il controllo durante l'esecuzione di tale segmento di codice.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-210">Therefore, no other operation can gain control during that segment of code.</span></span>

## <a name="reviewing-and-running-the-example-app"></a><a name="BKMD_SettingUpTheExample"></a><span data-ttu-id="2c1a2-211">Revisione ed esecuzione dell'app di esempio</span><span class="sxs-lookup"><span data-stu-id="2c1a2-211">Reviewing and Running the Example App</span></span>

<span data-ttu-id="2c1a2-212">Per comprendere meglio l'applicazione di esempio, è possibile scaricarla, compilarla manualmente o esaminare il codice alla fine di questo argomento senza implementare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-212">To better understand the example app, you can download it, build it yourself, or review the code at the end of this topic without implementing the app.</span></span>

> [!NOTE]
> <span data-ttu-id="2c1a2-213">Per eseguire l'esempio come applicazione dektop WPF (Windows Presentation Foundation), è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-213">To run the example as a Windows Presentation Foundation (WPF) desktop app, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="downloading-the-app"></a><a name="BKMK_DownloadingTheApp"></a> <span data-ttu-id="2c1a2-214">Download dell'app</span><span class="sxs-lookup"><span data-stu-id="2c1a2-214">Downloading the App</span></span>

1. <span data-ttu-id="2c1a2-215">Scaricare il file compresso da [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06) (Esempio di progetti asincroni: reentrancy in applicazioni desktop .NET).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-215">Download the compressed file from [Async Samples: Reentrancy in .NET Desktop Apps](https://code.msdn.microsoft.com/Async-Sample-Preventing-a8489f06).</span></span>

2. <span data-ttu-id="2c1a2-216">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-216">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

3. <span data-ttu-id="2c1a2-217">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-217">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

4. <span data-ttu-id="2c1a2-218">Passare alla cartella che contiene il codice di esempio decompresso e quindi aprire il file di soluzione (sln).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-218">Navigate to the folder that holds the decompressed sample code, and then open the solution (.sln) file.</span></span>

5. <span data-ttu-id="2c1a2-219">In **Esplora soluzioni** aprire il menu di scelta rapida del progetto che si vuole eseguire e scegliere **Set as StartUpProject** (Imposta come progetto di avvio).</span><span class="sxs-lookup"><span data-stu-id="2c1a2-219">In **Solution Explorer**, open the shortcut menu for the project that you want to run, and then choose **Set as StartUpProject**.</span></span>

6. <span data-ttu-id="2c1a2-220">Premere CTRL+F5 per compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-220">Choose the CTRL+F5 keys to build and run the project.</span></span>

### <a name="building-the-app"></a><a name="BKMK_BuildingTheApp"></a> <span data-ttu-id="2c1a2-221">Compilazione dell'app</span><span class="sxs-lookup"><span data-stu-id="2c1a2-221">Building the App</span></span>

<span data-ttu-id="2c1a2-222">Nella sezione seguente viene illustrato il codice per compilare l'esempio come app WPF.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-222">The following section provides the code to build the example as a WPF app.</span></span>

##### <a name="to-build-a-wpf-app"></a><span data-ttu-id="2c1a2-223">Per compilare un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="2c1a2-223">To build a WPF app</span></span>

1. <span data-ttu-id="2c1a2-224">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-224">Start Visual Studio.</span></span>

2. <span data-ttu-id="2c1a2-225">Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-225">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="2c1a2-226">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="2c1a2-226">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="2c1a2-227">Nel riquadro **Modelli installati** espandere **Visual C#** e selezionare **Windows**.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-227">In the **Installed Templates** pane, expand **Visual C#**, and then expand **Windows**.</span></span>

4. <span data-ttu-id="2c1a2-228">Dall'elenco dei tipi di progetto scegliere **Applicazione WPF**.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-228">In the list of project types, choose **WPF Application**.</span></span>

5. <span data-ttu-id="2c1a2-229">Assegnare un nome al progetto `WebsiteDownloadWPF` , scegliere .NET Framework versione 4,6 o successiva, quindi fare clic sul pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="2c1a2-229">Name the project `WebsiteDownloadWPF`, choose .NET Framework version of 4.6 or higher, and then click the **OK** button.</span></span>

     <span data-ttu-id="2c1a2-230">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-230">The new project appears in **Solution Explorer**.</span></span>

6. <span data-ttu-id="2c1a2-231">Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="2c1a2-231">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="2c1a2-232">Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow. XAML in **Esplora soluzioni**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-232">If the tab isn't visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

7. <span data-ttu-id="2c1a2-233">Nella visualizzazione **XAML** di MainWindow.xaml sostituire il codice con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-233">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

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

     <span data-ttu-id="2c1a2-234">Nella visualizzazione **Progettazione** di MainWindow.xaml viene visualizzata una finestra semplice contenente una casella di testo e un pulsante.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-234">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

8. <span data-ttu-id="2c1a2-235">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **riferimenti** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-235">In **Solution Explorer**, right-click on **References** and select **Add Reference**.</span></span>

     <span data-ttu-id="2c1a2-236">Aggiungere un riferimento per <xref:System.Net.Http> , se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-236">Add a reference for <xref:System.Net.Http>, if it is not selected already.</span></span>

9. <span data-ttu-id="2c1a2-237">In **Esplora soluzioni** aprire il menu di scelta rapida per MainWindow.xaml.cs e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-237">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

10. <span data-ttu-id="2c1a2-238">Sostituire il codice in MainWindow.xaml.cs con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-238">In MainWindow.xaml.cs, replace the code with the following code.</span></span>

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

11. <span data-ttu-id="2c1a2-239">Premere CTRL+F5 per eseguire il programma e scegliere il pulsante **Start** più volte.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-239">Choose the CTRL+F5 keys to run the program, and then choose the **Start** button several times.</span></span>

12. <span data-ttu-id="2c1a2-240">Apportare le modifiche descritte in [Disabilitare il pulsante Start](#BKMK_DisableTheStartButton), [Annullare e riavviare l'operazione](#BKMK_CancelAndRestart) o [Eseguire più operazioni e mettere in coda l'output](#BKMK_RunMultipleOperations) per gestire la reentrancy.</span><span class="sxs-lookup"><span data-stu-id="2c1a2-240">Make the changes from [Disable the Start Button](#BKMK_DisableTheStartButton), [Cancel and Restart the Operation](#BKMK_CancelAndRestart), or [Run Multiple Operations and Queue the Output](#BKMK_RunMultipleOperations) to handle the reentrancy.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c1a2-241">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c1a2-241">See also</span></span>

- [<span data-ttu-id="2c1a2-242">Procedura dettagliata: accesso al Web tramite async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="2c1a2-242">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="2c1a2-243">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="2c1a2-243">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
