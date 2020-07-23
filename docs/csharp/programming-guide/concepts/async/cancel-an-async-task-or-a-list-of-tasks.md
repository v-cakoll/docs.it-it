---
title: Annullare un'attività asincrona o un elenco di attività (C#)
description: Usare questi esempi per aggiungere un pulsante che annulla un'applicazione asincrona prima del completamento. Questa applicazione C# Scarica il contenuto di uno o più siti Web.
ms.date: 07/20/2015
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 21bdbc3bc7c3b752fab160429d71356fb87d9976
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925346"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-c"></a><span data-ttu-id="a17b8-104">Annullare un'attività asincrona o un elenco di attività (C#)</span><span class="sxs-lookup"><span data-stu-id="a17b8-104">Cancel an async task or a list of tasks (C#)</span></span>

<span data-ttu-id="a17b8-105">È possibile impostare un pulsante che consenta di annullare un'applicazione asincrona se non si vuole attendere il suo completamento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-105">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="a17b8-106">Seguendo gli esempi in questo argomento, è possibile aggiungere un pulsante di annullamento di un'applicazione che scarica il contenuto di un sito Web o di un elenco di siti Web.</span><span class="sxs-lookup"><span data-stu-id="a17b8-106">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>

<span data-ttu-id="a17b8-107">Negli esempi viene usata l'interfaccia utente che illustra l'[ottimizzazione dell'applicazione Async (C#)](./fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="a17b8-107">The examples use the UI that [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) describes.</span></span>

> [!NOTE]
> <span data-ttu-id="a17b8-108">Per eseguire gli esempi, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.</span><span class="sxs-lookup"><span data-stu-id="a17b8-108">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="cancel-a-task"></a><span data-ttu-id="a17b8-109">Annullare un'attività</span><span class="sxs-lookup"><span data-stu-id="a17b8-109">Cancel a task</span></span>

<span data-ttu-id="a17b8-110">Il primo esempio associa il pulsante **Annulla** con un'attività di download singola.</span><span class="sxs-lookup"><span data-stu-id="a17b8-110">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="a17b8-111">Se si sceglie il pulsante mentre l'applicazione sta scaricando il contenuto, il download viene annullato.</span><span class="sxs-lookup"><span data-stu-id="a17b8-111">If you choose the button while the application is downloading content, the download is canceled.</span></span>

### <a name="download-the-example"></a><span data-ttu-id="a17b8-112">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="a17b8-112">Download the example</span></span>

<span data-ttu-id="a17b8-113">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="a17b8-113">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="a17b8-114">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a17b8-114">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="a17b8-115">Sulla barra dei menu scegliere **file**  >  **Apri**  >  **progetto/soluzione**.</span><span class="sxs-lookup"><span data-stu-id="a17b8-115">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="a17b8-116">Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e aprire il file di soluzione (SLN) per AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="a17b8-116">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="a17b8-117">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelATask** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="a17b8-117">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="a17b8-118">Premere **F5** per eseguire il progetto (oppure **CTRL**+**F5** per eseguire il progetto senza il debug).</span><span class="sxs-lookup"><span data-stu-id="a17b8-118">Choose the **F5** key to run the project (or, press **Ctrl**+**F5** to run the project without debugging it).</span></span>

> [!TIP]
> <span data-ttu-id="a17b8-119">Se non si vuole scaricare il progetto, è possibile rivedere i file MainWindow.xaml.cs alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-119">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>

### <a name="build-the-example"></a><span data-ttu-id="a17b8-120">Compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="a17b8-120">Build the example</span></span>
 <span data-ttu-id="a17b8-121">Le modifiche seguenti aggiungono un pulsante **Annulla** a un'applicazione che scarica un sito Web.</span><span class="sxs-lookup"><span data-stu-id="a17b8-121">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="a17b8-122">Se non si vuole scaricare o compilare l'esempio, è possibile rivedere il prodotto finale nella sezione "Esempi completi" alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-122">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="a17b8-123">Gli asterischi contrassegnano le modifiche nel codice.</span><span class="sxs-lookup"><span data-stu-id="a17b8-123">Asterisks mark the changes in the code.</span></span>

 <span data-ttu-id="a17b8-124">Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **StarterCode** come **progetto di avvio** anziché **CancelATask**.</span><span class="sxs-lookup"><span data-stu-id="a17b8-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>

 <span data-ttu-id="a17b8-125">Aggiungere quindi le modifiche seguenti al file MainWindow.xaml.cs di tale progetto.</span><span class="sxs-lookup"><span data-stu-id="a17b8-125">Then add the following changes to the MainWindow.xaml.cs file of that project.</span></span>

1. <span data-ttu-id="a17b8-126">Dichiarare una variabile `CancellationTokenSource`, `cts`, che sia nell'ambito di accesso di tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="a17b8-126">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>

    ```csharp
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. <span data-ttu-id="a17b8-127">Aggiungere il gestore eventi seguente per il pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="a17b8-127">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="a17b8-128">Il gestore dell'evento usa il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> per inviare notifica a `cts` quando l'utente richiede l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-128">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method to notify `cts` when the user requests cancellation.</span></span>

    ```csharp
    // ***Add an event handler for the Cancel button.
    private void cancelButton_Click(object sender, RoutedEventArgs e)
    {
        if (cts != null)
        {
            cts.Cancel();
        }
    }
    ```

3. <span data-ttu-id="a17b8-129">Apportare le modifiche seguenti nel gestore eventi per il pulsante **Avvio**, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="a17b8-129">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>

    - <span data-ttu-id="a17b8-130">Creare un'istanza di `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="a17b8-130">Instantiate the `CancellationTokenSource`, `cts`.</span></span>

        ```csharp
        // ***Instantiate the CancellationTokenSource.
        cts = new CancellationTokenSource();
        ```

    - <span data-ttu-id="a17b8-131">Nella chiamata a `AccessTheWebAsync`, che scarica il contenuto di un sito Web specifico, inviare la proprietà <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> di `cts` come argomento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-131">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> property of `cts` as an argument.</span></span> <span data-ttu-id="a17b8-132">La proprietà `Token` propaga il messaggio se viene richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-132">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="a17b8-133">Aggiungere un blocco catch che visualizzi un messaggio se l'utente sceglie di annullare l'operazione di download.</span><span class="sxs-lookup"><span data-stu-id="a17b8-133">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="a17b8-134">Il codice seguente illustra le modifiche.</span><span class="sxs-lookup"><span data-stu-id="a17b8-134">The following code shows the changes.</span></span>

        ```csharp
        try
        {
            // ***Send a token to carry the message if cancellation is requested.
            int contentLength = await AccessTheWebAsync(cts.Token);
            resultsTextBox.Text += $"\r\nLength of the downloaded string: {contentLength}.\r\n";
        }
        // *** If cancellation is requested, an OperationCanceledException results.
        catch (OperationCanceledException)
        {
            resultsTextBox.Text += "\r\nDownload canceled.\r\n";
        }
        catch (Exception)
        {
            resultsTextBox.Text += "\r\nDownload failed.\r\n";
        }
        ```

4. <span data-ttu-id="a17b8-135">In `AccessTheWebAsync` usare l'overload <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> del metodo `GetAsync` nel tipo <xref:System.Net.Http.HttpClient> per scaricare il contenuto di un sito Web.</span><span class="sxs-lookup"><span data-stu-id="a17b8-135">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="a17b8-136">Passare `ct`, il parametro <xref:System.Threading.CancellationToken> di `AccessTheWebAsync`, come secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-136">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="a17b8-137">Il token trasporta il messaggio se l'utente sceglie il pulsante **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="a17b8-137">The token carries the message if the user chooses the **Cancel** button.</span></span>

     <span data-ttu-id="a17b8-138">Il codice seguente illustra tutte le modifiche in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="a17b8-138">The following code shows the changes in `AccessTheWebAsync`.</span></span>

    ```csharp
    // ***Provide a parameter for the CancellationToken.
    async Task<int> AccessTheWebAsync(CancellationToken ct)
    {
        HttpClient client = new HttpClient();

        resultsTextBox.Text += "\r\nReady to download.\r\n";

        // You might need to slow things down to have a chance to cancel.
        await Task.Delay(250);

        // GetAsync returns a Task<HttpResponseMessage>.
        // ***The ct argument carries the message if the Cancel button is chosen.
        HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // The result of the method is the length of the downloaded website.
        return urlContents.Length;
    }
    ```

5. <span data-ttu-id="a17b8-139">Se non si annulla il programma, viene prodotto l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="a17b8-139">If you don’t cancel the program, it produces the following output.</span></span>

    ```text
    Ready to download.
    Length of the downloaded string: 158125.
    ```

     <span data-ttu-id="a17b8-140">Se si sceglie il pulsante **Annulla** prima che il programma termini il download del contenuto, viene prodotto l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="a17b8-140">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>

    ```text
    Ready to download.
    Download canceled.
    ```

## <a name="cancel-a-list-of-tasks"></a><span data-ttu-id="a17b8-141">Annullare un elenco di attività</span><span class="sxs-lookup"><span data-stu-id="a17b8-141">Cancel a list of tasks</span></span>

<span data-ttu-id="a17b8-142">È possibile estendere l'esempio precedente per annullare più attività associando la stessa istanza `CancellationTokenSource` con ogni attività.</span><span class="sxs-lookup"><span data-stu-id="a17b8-142">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="a17b8-143">Se si sceglie il pulsante **Annulla**, vengono annullate tutte le attività che non sono ancora complete.</span><span class="sxs-lookup"><span data-stu-id="a17b8-143">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>

### <a name="download-the-example"></a><span data-ttu-id="a17b8-144">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="a17b8-144">Download the example</span></span>

<span data-ttu-id="a17b8-145">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="a17b8-145">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="a17b8-146">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a17b8-146">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="a17b8-147">Sulla barra dei menu scegliere **file**  >  **Apri**  >  **progetto/soluzione**.</span><span class="sxs-lookup"><span data-stu-id="a17b8-147">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="a17b8-148">Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e aprire il file di soluzione (SLN) per AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="a17b8-148">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="a17b8-149">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelAListOfTasks** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="a17b8-149">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="a17b8-150">Premere **F5** per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="a17b8-150">Choose the **F5** key to run the project.</span></span>

     <span data-ttu-id="a17b8-151">Premere il **tasto CTRL** + **F5** per eseguire il progetto senza eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="a17b8-151">Choose the **Ctrl**+**F5** keys to run the project without debugging it.</span></span>

<span data-ttu-id="a17b8-152">Se non si vuole scaricare il progetto, è possibile rivedere i file MainWindow.xaml.cs alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-152">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>

### <a name="build-the-example"></a><span data-ttu-id="a17b8-153">Compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="a17b8-153">Build the example</span></span>

<span data-ttu-id="a17b8-154">Per estendere l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **CancelATask** come **progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="a17b8-154">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="a17b8-155">Aggiungere le modifiche seguenti a tale progetto.</span><span class="sxs-lookup"><span data-stu-id="a17b8-155">Add the following changes to that project.</span></span> <span data-ttu-id="a17b8-156">Gli asterischi contrassegnano le modifiche nel programma.</span><span class="sxs-lookup"><span data-stu-id="a17b8-156">Asterisks mark the changes in the program.</span></span>

1. <span data-ttu-id="a17b8-157">Aggiungere un metodo per creare un elenco di indirizzi Web.</span><span class="sxs-lookup"><span data-stu-id="a17b8-157">Add a method to create a list of web addresses.</span></span>

    ```csharp
    // ***Add a method that creates a list of web addresses.
    private List<string> SetUpURLList()
    {
        List<string> urls = new List<string>
        {
            "https://msdn.microsoft.com",
            "https://msdn.microsoft.com/library/hh290138.aspx",
            "https://msdn.microsoft.com/library/hh290140.aspx",
            "https://msdn.microsoft.com/library/dd470362.aspx",
            "https://msdn.microsoft.com/library/aa578028.aspx",
            "https://msdn.microsoft.com/library/ms404677.aspx",
            "https://msdn.microsoft.com/library/ff730837.aspx"
        };
        return urls;
    }
    ```

2. <span data-ttu-id="a17b8-158">Chiamare il metodo in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="a17b8-158">Call the method in `AccessTheWebAsync`.</span></span>

    ```csharp
    // ***Call SetUpURLList to make a list of web addresses.
    List<string> urlList = SetUpURLList();
    ```

3. <span data-ttu-id="a17b8-159">Aggiungere il ciclo seguente in `AccessTheWebAsync` per elaborare gli indirizzi Web nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a17b8-159">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>

    ```csharp
    // ***Add a loop to process the list of web addresses.
    foreach (var url in urlList)
    {
        // GetAsync returns a Task<HttpResponseMessage>.
        // Argument ct carries the message if the Cancel button is chosen.
        // ***Note that the Cancel button can cancel all remaining downloads.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
    }
    ```

4. <span data-ttu-id="a17b8-160">Poiché `AccessTheWebAsync` visualizza le lunghezze, il metodo non deve restituire nessun valore.</span><span class="sxs-lookup"><span data-stu-id="a17b8-160">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="a17b8-161">Rimuovere l'istruzione return e modificare il tipo restituito del metodo in <xref:System.Threading.Tasks.Task> anziché <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="a17b8-161">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>

    ```csharp
    async Task AccessTheWebAsync(CancellationToken ct)
    ```

     <span data-ttu-id="a17b8-162">Chiamare il metodo da `startButton_Click` usando un'istruzione anziché un'espressione.</span><span class="sxs-lookup"><span data-stu-id="a17b8-162">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>

    ```csharp
    await AccessTheWebAsync(cts.Token);
    ```

5. <span data-ttu-id="a17b8-163">Se non si annulla il programma, viene prodotto l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="a17b8-163">If you don’t cancel the program, it produces the following output.</span></span>

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

     <span data-ttu-id="a17b8-164">Se si sceglie il pulsante **Annulla** prima di aver completato i download, l'output contiene le lunghezze dei download completati prima dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-164">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="complete-examples"></a><span data-ttu-id="a17b8-165">Esempi completi</span><span class="sxs-lookup"><span data-stu-id="a17b8-165">Complete examples</span></span>

<span data-ttu-id="a17b8-166">Le sezioni seguenti contengono il codice per ognuno degli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="a17b8-166">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="a17b8-167">Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="a17b8-167">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="a17b8-168">È possibile scaricare i progetti da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="a17b8-168">You can download the projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

### <a name="example---cancel-a-task"></a><span data-ttu-id="a17b8-169">Esempio - Annullare un'attività</span><span class="sxs-lookup"><span data-stu-id="a17b8-169">Example - Cancel a task</span></span>

<span data-ttu-id="a17b8-170">Il codice seguente è il file completo del file MainWindow.xaml.cs per l'esempio che annulla un'attività singola.</span><span class="sxs-lookup"><span data-stu-id="a17b8-170">The following code is the complete MainWindow.xaml.cs file for the example that cancels a single task.</span></span>

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

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive for System.Threading.

using System.Threading;
namespace CancelATask
{
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // ***Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                // ***Send a token to carry the message if cancellation is requested.
                int contentLength = await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }
            // *** If cancellation is requested, an OperationCanceledException results.
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownload canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownload failed.\r\n";
            }

            // ***Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // ***Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // ***Provide a parameter for the CancellationToken.
        async Task<int> AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            resultsTextBox.Text += "\r\nReady to download.\r\n";

            // You might need to slow things down to have a chance to cancel.
            await Task.Delay(250);

            // GetAsync returns a Task<HttpResponseMessage>.
            // ***The ct argument carries the message if the Cancel button is chosen.
            HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            // The result of the method is the length of the downloaded website.
            return urlContents.Length;
        }
    }

    // Output for a successful download:

    // Ready to download.

    // Length of the downloaded string: 158125.

    // Or, if you cancel:

    // Ready to download.

    // Download canceled.
}
```

### <a name="example---cancel-a-list-of-tasks"></a><span data-ttu-id="a17b8-171">Esempio - Annullare un elenco di attività</span><span class="sxs-lookup"><span data-stu-id="a17b8-171">Example - Cancel a list of tasks</span></span>

<span data-ttu-id="a17b8-172">Il codice seguente è il file MainWindow.xaml.cs completo per l'esempio che annulla un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="a17b8-172">The following code is the complete MainWindow.xaml.cs file for the example that cancels a list of tasks.</span></span>

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

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive for System.Threading.
using System.Threading;

namespace CancelAListOfTasks
{
    public partial class MainWindow : Window
    {
        // Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                await AccessTheWebAsync(cts.Token);
                // ***Small change in the display lines.
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.";
            }

            // Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // Provide a parameter for the CancellationToken.
        // ***Change the return type to Task because the method has no return statement.
        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // ***Call SetUpURLList to make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Add a loop to process the list of web addresses.
            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // ***Note that the Cancel button can cancel all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        // ***Add a method that creates a list of web addresses.
        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Output if you do not choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Length of the downloaded string: 158124.

    //Length of the downloaded string: 204890.

    //Length of the downloaded string: 175488.

    //Length of the downloaded string: 145790.

    //Downloads complete.

    // Sample output if you choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Downloads canceled.
}
```

## <a name="see-also"></a><span data-ttu-id="a17b8-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a17b8-173">See also</span></span>

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [<span data-ttu-id="a17b8-174">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="a17b8-174">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="a17b8-175">Ottimizzazione dell'applicazione asincrona (C#)</span><span class="sxs-lookup"><span data-stu-id="a17b8-175">Fine-Tuning Your Async Application (C#)</span></span>](./fine-tuning-your-async-application.md)
- <span data-ttu-id="a17b8-176">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="a17b8-176">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
