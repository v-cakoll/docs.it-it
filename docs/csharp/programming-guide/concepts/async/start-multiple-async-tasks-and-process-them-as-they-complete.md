---
title: Elaborare le attività asincrone quando vengono completate
ms.date: 09/12/2018
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: b618fd6bf80551231d2b285fd0e8aef688d00d93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "71736734"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a><span data-ttu-id="9a88f-102">Avviare più attività asincrone ed elaborarle quando vengono completate (C#)</span><span class="sxs-lookup"><span data-stu-id="9a88f-102">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>

<span data-ttu-id="9a88f-103">Usando <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, è possibile avviare più attività contemporaneamente ed elaborarle una ad una quando vengono completate, invece che nell'ordine in cui vengono avviate.</span><span class="sxs-lookup"><span data-stu-id="9a88f-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>

<span data-ttu-id="9a88f-104">Nell'esempio seguente viene usata una query per creare una Collection di attività.</span><span class="sxs-lookup"><span data-stu-id="9a88f-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="9a88f-105">Ogni attività scarica il contenuto di un sito Web specificato.</span><span class="sxs-lookup"><span data-stu-id="9a88f-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="9a88f-106">In ogni iterazione di un ciclo while, una chiamata attesa a `WhenAny` restituisce l'attività nella Collection di attività che completa per prima il download.</span><span class="sxs-lookup"><span data-stu-id="9a88f-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="9a88f-107">Questa attività viene rimossa dalla Collection ed elaborata.</span><span class="sxs-lookup"><span data-stu-id="9a88f-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="9a88f-108">Il ciclo si ripete finché la Collection non contiene più attività.</span><span class="sxs-lookup"><span data-stu-id="9a88f-108">The loop repeats until the collection contains no more tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="9a88f-109">Per eseguire gli esempi, è necessario avere installato nel computer Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="9a88f-109">To run the examples, you must have Visual Studio (2012 or newer) and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="download-an-example-solution"></a><span data-ttu-id="9a88f-110">Scaricare una soluzione di esempio</span><span class="sxs-lookup"><span data-stu-id="9a88f-110">Download an example solution</span></span>

<span data-ttu-id="9a88f-111">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="9a88f-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

> [!TIP]
> <span data-ttu-id="9a88f-112">Se non si desidera scaricare il progetto, è possibile esaminare il file *di MainWindow.xaml.cs* alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9a88f-112">If you don't want to download the project, you can review the *MainWindow.xaml.cs* file at the end of this topic instead.</span></span>

1. <span data-ttu-id="9a88f-113">Estrarre i file scaricati dal file *con estensione zip,* quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9a88f-113">Extract the files that you downloaded from the *.zip* file, and then start Visual Studio.</span></span>

2. <span data-ttu-id="9a88f-114">Nella barra dei menu scegliere**Apri** > **progetto/soluzione** **apri file** > .</span><span class="sxs-lookup"><span data-stu-id="9a88f-114">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="9a88f-115">Nella finestra di dialogo **Apri progetto** aprire la cartella contenente il codice di esempio scaricato, quindi aprire il file di soluzione (*sln*) per *AsyncFineTuningCS*/*AsyncFineTuningVB*.</span><span class="sxs-lookup"><span data-stu-id="9a88f-115">In the **Open Project** dialog box, open the folder that holds the sample code you downloaded, and then open the solution (*.sln*) file for *AsyncFineTuningCS*/*AsyncFineTuningVB*.</span></span>

4. <span data-ttu-id="9a88f-116">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **ProcessTasksAsTheyFinish** e quindi scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="9a88f-116">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="9a88f-117">Premere il tasto <kbd>F5</kbd> per eseguire il programma con il debug oppure premere i tasti <kbd>Ctrl</kbd>+<kbd>F5</kbd> per eseguire il programma senza eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="9a88f-117">Choose the <kbd>F5</kbd> key to run the program with debugging or, press <kbd>Ctrl</kbd>+<kbd>F5</kbd> keys to run the program without debugging it.</span></span>

6. <span data-ttu-id="9a88f-118">Eseguire il progetto più volte per verificare che le lunghezze scaricate non siano sempre nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="9a88f-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

## <a name="create-the-program-yourself"></a><span data-ttu-id="9a88f-119">Creare il programma autonomamente</span><span class="sxs-lookup"><span data-stu-id="9a88f-119">Create the program yourself</span></span>

<span data-ttu-id="9a88f-120">Questo esempio è basato sul codice sviluppato in [Annullare le attività asincrone rimanenti dopo che ne è stata completata una (C#)](cancel-remaining-async-tasks-after-one-is-complete.md) e usa la stessa interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="9a88f-120">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (C#)](cancel-remaining-async-tasks-after-one-is-complete.md), and it uses the same UI.</span></span>

<span data-ttu-id="9a88f-121">Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione [Download dell'esempio](cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example), ma scegliere **CancelAfterOneTask** come progetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="9a88f-121">To build the example yourself, step by step, follow the instructions in the [Downloading the Example](cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example) section, but set **CancelAfterOneTask** as the startup project.</span></span> <span data-ttu-id="9a88f-122">Aggiungere le modifiche in questo argomento al metodo `AccessTheWebAsync` in tale progetto.</span><span class="sxs-lookup"><span data-stu-id="9a88f-122">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="9a88f-123">Le modifiche sono contrassegnate con asterischi.</span><span class="sxs-lookup"><span data-stu-id="9a88f-123">The changes are marked with asterisks.</span></span>

<span data-ttu-id="9a88f-124">Il progetto **CancelAfterOneTask** include già una query che, se eseguita, crea una Collection di attività.</span><span class="sxs-lookup"><span data-stu-id="9a88f-124">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="9a88f-125">Ogni chiamata a `ProcessURLAsync` nel codice seguente restituisce un <xref:System.Threading.Tasks.Task%601>, dove `TResult` è un valore intero:</span><span class="sxs-lookup"><span data-stu-id="9a88f-125">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
IEnumerable<Task<int>> downloadTasksQuery = from url in urlList select ProcessURL(url, client, ct);
```

<span data-ttu-id="9a88f-126">Nel *file MainWindow.xaml.cs* del progetto, apportare `AccessTheWebAsync` le seguenti modifiche al metodo:</span><span class="sxs-lookup"><span data-stu-id="9a88f-126">In the *MainWindow.xaml.cs* file of the project, make the following changes to the `AccessTheWebAsync` method:</span></span>

- <span data-ttu-id="9a88f-127">Eseguire la query applicando <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> anziché <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a88f-127">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>

    ```csharp
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
    ```

- <span data-ttu-id="9a88f-128">Aggiungere un ciclo `while` che esegue i passaggi seguenti per ogni attività nella raccolta:</span><span class="sxs-lookup"><span data-stu-id="9a88f-128">Add a `while` loop that performs the following steps for each task in the collection:</span></span>

    1. <span data-ttu-id="9a88f-129">Attende una chiamata a `WhenAny` per identificare la prima attività nella raccolta che deve completare il relativo download.</span><span class="sxs-lookup"><span data-stu-id="9a88f-129">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>

        ```csharp
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
        ```

    2. <span data-ttu-id="9a88f-130">Rimuove l'attività dalla Collection.</span><span class="sxs-lookup"><span data-stu-id="9a88f-130">Removes that task from the collection.</span></span>

        ```csharp
        downloadTasks.Remove(firstFinishedTask);
        ```

    3. <span data-ttu-id="9a88f-131">Attende `firstFinishedTask`, che viene restituito da una chiamata a `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="9a88f-131">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="9a88f-132">La variabile `firstFinishedTask` è un <xref:System.Threading.Tasks.Task%601> dove `TReturn` è un valore intero.</span><span class="sxs-lookup"><span data-stu-id="9a88f-132">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="9a88f-133">L'attività è già stata completata, ma è possibile metterla in attesa per recuperare la lunghezza del sito Web scaricato, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9a88f-133">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span> <span data-ttu-id="9a88f-134">Se l'attività ha `await` un errore, genererà `AggregateException`la prima `Result` eccezione figlio `AggregateException`archiviata in , a differenza della lettura della proprietà che genererebbe l'oggetto .</span><span class="sxs-lookup"><span data-stu-id="9a88f-134">If the task is faulted, `await` will throw the first child exception stored in the `AggregateException`, unlike reading the `Result` property which would throw the `AggregateException`.</span></span>

        ```csharp
        int length = await firstFinishedTask;
        resultsTextBox.Text += $"\r\nLength of the download:  {length}";
        ```

<span data-ttu-id="9a88f-135">Eseguire il programma più volte per verificare che le lunghezze scaricate non siano sempre nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="9a88f-135">Run the program several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

> [!CAUTION]
> <span data-ttu-id="9a88f-136">È possibile usare `WhenAny` in un ciclo, come descritto nell'esempio, per risolvere i problemi che includono un numero limitato di attività.</span><span class="sxs-lookup"><span data-stu-id="9a88f-136">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="9a88f-137">Tuttavia, se ci sono molte attività da elaborare, altri approcci sono più efficienti.</span><span class="sxs-lookup"><span data-stu-id="9a88f-137">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="9a88f-138">Per ulteriori informazioni ed esempi, vedere Elaborazione delle attività durante il [completamento.](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/)</span><span class="sxs-lookup"><span data-stu-id="9a88f-138">For more information and examples, see [Processing tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/).</span></span>

## <a name="complete-example"></a><span data-ttu-id="9a88f-139">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="9a88f-139">Complete example</span></span>

<span data-ttu-id="9a88f-140">Il codice seguente è il testo completo del file *MainWindow.xaml.cs* per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="9a88f-140">The following code is the complete text of the *MainWindow.xaml.cs* file for the example.</span></span> <span data-ttu-id="9a88f-141">Gli asterischi contrassegnano gli elementi che sono stati aggiunti per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="9a88f-141">Asterisks mark the elements that were added for this example.</span></span> <span data-ttu-id="9a88f-142">Si noti inoltre che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="9a88f-142">Also, take note that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="9a88f-143">È possibile scaricare il progetto da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="9a88f-143">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

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

// Add the following using directive.
using System.Threading;

namespace ProcessTasksAsTheyFinish
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
            resultsTextBox.Clear();

            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            try
            {
                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";
            }

            cts = null;
        }

        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Create a query that, when executed, returns a collection of tasks.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURL(url, client, ct);

            // ***Use ToList to execute the query and start the tasks.
            List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

            // ***Add a loop to process the tasks one at a time until none remain.
            while (downloadTasks.Count > 0)
            {
                    // Identify the first task that completes.
                    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);

                    // ***Remove the selected task from the list so that you don't
                    // process it more than once.
                    downloadTasks.Remove(firstFinishedTask);

                    // Await the completed task.
                    int length = await firstFinishedTask;
                    resultsTextBox.Text += $"\r\nLength of the download:  {length}";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        async Task<int> ProcessURL(string url, HttpClient client, CancellationToken ct)
        {
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            return urlContents.Length;
        }
    }
}

// Sample Output:

// Length of the download:  226093
// Length of the download:  412588
// Length of the download:  175490
// Length of the download:  204890
// Length of the download:  158855
// Length of the download:  145790
// Length of the download:  44908
// Downloads complete.
```

## <a name="see-also"></a><span data-ttu-id="9a88f-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a88f-144">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="9a88f-145">Ottimizzazione dell'applicazione asincrona (C#)</span><span class="sxs-lookup"><span data-stu-id="9a88f-145">Fine-Tuning Your Async Application (C#)</span></span>](fine-tuning-your-async-application.md)
- [<span data-ttu-id="9a88f-146">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="9a88f-146">Asynchronous Programming with async and await (C#)</span></span>](index.md)
- <span data-ttu-id="9a88f-147">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="9a88f-147">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
