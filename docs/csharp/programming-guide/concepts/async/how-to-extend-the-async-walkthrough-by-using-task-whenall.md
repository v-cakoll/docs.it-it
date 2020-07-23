---
title: Come estendere la procedura dettagliata asincrona tramite Task. WhenAll (C#)
description: Informazioni su come migliorare le prestazioni della soluzione asincrona in C# tramite Task. WhenAll. Questo metodo attende in modo asincrono più operazioni asincrone.
ms.date: 07/20/2015
ms.assetid: f6927ef2-dc6c-43f8-bc82-bbeac42de423
ms.openlocfilehash: 275f4aeca854f8938642dbea40bf7fd9dc5362d9
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925215"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-c"></a><span data-ttu-id="34f1f-104">Come estendere la procedura dettagliata asincrona tramite Task. WhenAll (C#)</span><span class="sxs-lookup"><span data-stu-id="34f1f-104">How to extend the async walkthrough by using Task.WhenAll (C#)</span></span>

<span data-ttu-id="34f1f-105">È possibile migliorare le prestazioni della soluzione asincrona in [Procedura dettagliata: accesso al Web con Async e Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) usando il metodo <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34f1f-105">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="34f1f-106">Questo metodo mette in attesa più operazioni asincrone, rappresentate come una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="34f1f-106">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>

<span data-ttu-id="34f1f-107">Si noti che nella procedura dettagliata i siti Web vengono scaricati a velocità diverse.</span><span class="sxs-lookup"><span data-stu-id="34f1f-107">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="34f1f-108">A volte un sito Web è molto lento e causa il ritardo di tutti i download rimanenti.</span><span class="sxs-lookup"><span data-stu-id="34f1f-108">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="34f1f-109">Quando si eseguono le soluzioni asincrone compilate nella procedura dettagliata, è possibile terminare il programma con facilità se non si vuole attendere. Un'opzione migliore consiste nell'avviare tutti i download contemporaneamente e consentire a quelli più veloci di continuare senza attendere il termine di quello più lento.</span><span class="sxs-lookup"><span data-stu-id="34f1f-109">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>

<span data-ttu-id="34f1f-110">Si applica il metodo `Task.WhenAll` a una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="34f1f-110">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="34f1f-111">L'applicazione di `WhenAll` restituisce una singola attività che non viene completata fino quando non vengono completate tutte le attività nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="34f1f-111">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="34f1f-112">Le attività vengono eseguite in parallelo, ma non vengono creati thread aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="34f1f-112">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="34f1f-113">Il completamento delle attività può avvenire in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="34f1f-113">The tasks can complete in any order.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34f1f-114">Le procedure seguenti descrivono le estensioni per le applicazioni asincrone che sono state sviluppate in [Procedura dettagliata: accesso al Web tramite async e await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="34f1f-114">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="34f1f-115">È possibile sviluppare le applicazioni completando la procedura dettagliata o scaricando il codice da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempi di codice per gli sviluppatori).</span><span class="sxs-lookup"><span data-stu-id="34f1f-115">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>
>
> <span data-ttu-id="34f1f-116">Per eseguire l'esempio, è necessario avere Visual Studio 2012 o versioni successive installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="34f1f-116">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="34f1f-117">Per aggiungere Task.WhenAll alla soluzione GetURLContentsAsync</span><span class="sxs-lookup"><span data-stu-id="34f1f-117">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>

1. <span data-ttu-id="34f1f-118">Aggiungere il metodo `ProcessURLAsync` per la prima applicazione che è stata sviluppata in [Procedura dettagliata: accesso al Web tramite async e await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="34f1f-118">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="34f1f-119">Se è stato scaricato il codice da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempi di codice per gli sviluppatori), aprire il progetto AsyncWalkthrough e aggiungere `ProcessURLAsync` nel file MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="34f1f-119">If you downloaded the code from  [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.cs file.</span></span>

    - <span data-ttu-id="34f1f-120">Se il codice è stato sviluppato completando la procedura dettagliata, aggiungere `ProcessURLAsync` all'applicazione che include il metodo `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-120">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="34f1f-121">Il file MainWindow.xaml.cs per questa applicazione è il primo esempio nella sezione dedicata agli esempi di codice della procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="34f1f-121">The MainWindow.xaml.cs file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>

    <span data-ttu-id="34f1f-122">Il metodo `ProcessURLAsync` consente di consolidare le azioni nel corpo del ciclo `foreach` in `SumPageSizesAsync` nella procedura dettagliata originale.</span><span class="sxs-lookup"><span data-stu-id="34f1f-122">The `ProcessURLAsync` method consolidates the actions in the body of the `foreach` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="34f1f-123">Il metodo scarica in modo asincrono il contenuto di un sito Web specificato come matrice di byte e quindi visualizza e restituisce la lunghezza della matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="34f1f-123">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

    ```csharp
    private async Task<int> ProcessURLAsync(string url)
    {
        var byteArray = await GetURLContentsAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. <span data-ttu-id="34f1f-124">Impostare come commento o eliminare il ciclo `foreach` in `SumPageSizesAsync`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="34f1f-124">Comment out or delete the `foreach` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    byte[] urlContents = await GetURLContentsAsync(url);

    //    // The previous line abbreviates the following two assignment statements.
    //    // GetURLContentsAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //    //byte[] urlContents = await getContentsTask;

    //    DisplayResults(url, urlContents);

    //    // Update the total.
    //    total += urlContents.Length;
    //}
    ```

3. <span data-ttu-id="34f1f-125">Creare una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="34f1f-125">Create a collection of tasks.</span></span> <span data-ttu-id="34f1f-126">Il codice seguente definisce una [query](../linq/index.md) che, quando eseguita dal metodo <xref:System.Linq.Enumerable.ToArray%2A>, crea una raccolta di attività che scaricano il contenuto di ogni sito Web.</span><span class="sxs-lookup"><span data-stu-id="34f1f-126">The following code defines a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="34f1f-127">Le attività vengono avviate quando viene valutata la query.</span><span class="sxs-lookup"><span data-stu-id="34f1f-127">The tasks are started when the query is evaluated.</span></span>

    <span data-ttu-id="34f1f-128">Aggiungere il codice seguente al metodo `SumPageSizesAsync` dopo la dichiarazione di `urlList`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-128">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. <span data-ttu-id="34f1f-129">Applicare `Task.WhenAll` alla raccolta di attività, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-129">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="34f1f-130">`Task.WhenAll` restituisce una singola attività che termina al completamento di tutte le attività della raccolta.</span><span class="sxs-lookup"><span data-stu-id="34f1f-130">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

    <span data-ttu-id="34f1f-131">Nell'esempio seguente, l'espressione `await` mette in attesa il completamento della singola attività restituita da `WhenAll`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-131">In the following example, the `await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="34f1f-132">L'espressione restituisce una matrice di numeri interi, dove ogni numero intero rappresenta la lunghezza di un sito Web scaricato.</span><span class="sxs-lookup"><span data-stu-id="34f1f-132">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="34f1f-133">Aggiungere il codice seguente a `SumPageSizesAsync`, dopo il codice aggiunto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="34f1f-133">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. <span data-ttu-id="34f1f-134">Infine, usare il metodo <xref:System.Linq.Enumerable.Sum%2A> per calcolare la somma delle lunghezze di tutti i siti Web.</span><span class="sxs-lookup"><span data-stu-id="34f1f-134">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="34f1f-135">Aggiungere la riga seguente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-135">Add the following line to `SumPageSizesAsync`.</span></span>

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="34f1f-136">Per aggiungere Task.WhenAll alla soluzione HttpClient.GetByteArrayAsync</span><span class="sxs-lookup"><span data-stu-id="34f1f-136">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>

1. <span data-ttu-id="34f1f-137">Aggiungere la versione seguente di `ProcessURLAsync` alla seconda applicazione sviluppata in [Procedura dettagliata: accesso al Web tramite async e await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="34f1f-137">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="34f1f-138">Se è stato scaricato il codice da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempi di codice per gli sviluppatori), aprire il progetto AsyncWalkthrough_HttpClient e aggiungere `ProcessURLAsync` nel file MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="34f1f-138">If you downloaded the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.cs file.</span></span>

    - <span data-ttu-id="34f1f-139">Se il codice è stato sviluppato completando la procedura dettagliata, aggiungere `ProcessURLAsync` all'applicazione che usa il metodo `HttpClient.GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-139">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="34f1f-140">Il file MainWindow.xaml.cs per questa applicazione è il secondo esempio nella sezione dedicata agli esempi di codice della procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="34f1f-140">The MainWindow.xaml.cs file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>

    <span data-ttu-id="34f1f-141">Il metodo `ProcessURLAsync` consente di consolidare le azioni nel corpo del ciclo `foreach` in `SumPageSizesAsync` nella procedura dettagliata originale.</span><span class="sxs-lookup"><span data-stu-id="34f1f-141">The `ProcessURLAsync` method consolidates the actions in the body of the `foreach` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="34f1f-142">Il metodo scarica in modo asincrono il contenuto di un sito Web specificato come matrice di byte e quindi visualizza e restituisce la lunghezza della matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="34f1f-142">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

    <span data-ttu-id="34f1f-143">L'unica differenza rispetto al metodo `ProcessURLAsync` nella procedura precedente consiste nell'uso dell'istanza di <xref:System.Net.Http.HttpClient>, `client`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-143">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>

    ```csharp
    async Task<int> ProcessURLAsync(string url, HttpClient client)
    {
        byte[] byteArray = await client.GetByteArrayAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. <span data-ttu-id="34f1f-144">Impostare come commento o eliminare il ciclo `For Each` o `foreach` in `SumPageSizesAsync`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="34f1f-144">Comment out or delete the `For Each` or `foreach` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    // GetByteArrayAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    byte[] urlContent = await client.GetByteArrayAsync(url);

    //    // The previous line abbreviates the following two assignment
    //    // statements.
    //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
    //    byte[] urlContent = await getContentTask;

    //    DisplayResults(url, urlContent);

    //    // Update the total.
    //    total += urlContent.Length;
    //}
    ```

3. <span data-ttu-id="34f1f-145">Definire una [query](../linq/index.md) che, quando eseguita dal metodo <xref:System.Linq.Enumerable.ToArray%2A>, crea una raccolta di attività che scaricano il contenuto di ogni sito Web.</span><span class="sxs-lookup"><span data-stu-id="34f1f-145">Define a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="34f1f-146">Le attività vengono avviate quando viene valutata la query.</span><span class="sxs-lookup"><span data-stu-id="34f1f-146">The tasks are started when the query is evaluated.</span></span>

    <span data-ttu-id="34f1f-147">Aggiungere il codice seguente al metodo `SumPageSizesAsync` dopo la dichiarazione di `client` e `urlList`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-147">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url, client);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. <span data-ttu-id="34f1f-148">In seguito applicare `Task.WhenAll` alla raccolta di attività, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-148">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="34f1f-149">`Task.WhenAll` restituisce una singola attività che termina al completamento di tutte le attività della raccolta.</span><span class="sxs-lookup"><span data-stu-id="34f1f-149">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

    <span data-ttu-id="34f1f-150">Nell'esempio seguente, l'espressione `await` mette in attesa il completamento della singola attività restituita da `WhenAll`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-150">In the following example, the `await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="34f1f-151">Al termine dell'operazione, l'espressione `await` restituisce una matrice di numeri interi, dove ogni numero intero rappresenta la lunghezza di un sito Web scaricato.</span><span class="sxs-lookup"><span data-stu-id="34f1f-151">When complete, the `await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="34f1f-152">Aggiungere il codice seguente a `SumPageSizesAsync`, dopo il codice aggiunto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="34f1f-152">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. <span data-ttu-id="34f1f-153">Infine, usare il metodo <xref:System.Linq.Enumerable.Sum%2A> per ottenere la somma delle lunghezze di tutti i siti Web.</span><span class="sxs-lookup"><span data-stu-id="34f1f-153">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="34f1f-154">Aggiungere la riga seguente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="34f1f-154">Add the following line to `SumPageSizesAsync`.</span></span>

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="34f1f-155">Per testare le soluzioni Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="34f1f-155">To test the Task.WhenAll solutions</span></span>

- <span data-ttu-id="34f1f-156">Per tutte le soluzioni, premere F5 per eseguire il programma e scegliere il pulsante **Start**.</span><span class="sxs-lookup"><span data-stu-id="34f1f-156">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="34f1f-157">L'output dovrebbe essere simile all'output delle soluzioni asincrone in [Procedura dettagliata: accesso al Web tramite async e await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="34f1f-157">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="34f1f-158">Tuttavia, si noti che i siti Web vengono visualizzati ogni volta in un ordine diverso.</span><span class="sxs-lookup"><span data-stu-id="34f1f-158">However, notice that the websites appear in a different order each time.</span></span>

## <a name="example"></a><span data-ttu-id="34f1f-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="34f1f-159">Example</span></span>

<span data-ttu-id="34f1f-160">Il codice seguente illustra le estensioni per il progetto che usa il metodo `GetURLContentsAsync` per scaricare il contenuto dal Web.</span><span class="sxs-lookup"><span data-stu-id="34f1f-160">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_WhenAll
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Two-step async call.
            Task sumTask = SumPageSizesAsync();
            await sumTask;

            // One-step async call.
            //await SumPageSizesAsync();

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    byte[] urlContents = await GetURLContentsAsync(url);

            //    // The previous line abbreviates the following two assignment statements.
            //    // GetURLContentsAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
            //    //byte[] urlContents = await getContentsTask;

            //    DisplayResults(url, urlContents);

            //    // Update the total.
            //    total += urlContents.Length;
            //}

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        private async Task<int> ProcessURLAsync(string url)
        {
            var byteArray = await GetURLContentsAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    await responseStream.CopyToAsync(content);
                }
            }

            // Return the result as a byte array.
            return content.ToArray();

        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="example"></a><span data-ttu-id="34f1f-161">Esempio</span><span class="sxs-lookup"><span data-stu-id="34f1f-161">Example</span></span>

<span data-ttu-id="34f1f-162">Il codice seguente illustra le estensioni per il progetto che usa il metodo `HttpClient.GetByteArrayAsync` per scaricare il contenuto dal Web.</span><span class="sxs-lookup"><span data-stu-id="34f1f-162">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_HttpClient_WhenAll
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client = new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url, client);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    // GetByteArrayAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    byte[] urlContent = await client.GetByteArrayAsync(url);

            //    // The previous line abbreviates the following two assignment
            //    // statements.
            //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
            //    byte[] urlContent = await getContentTask;

            //    DisplayResults(url, urlContent);

            //    // Update the total.
            //    total += urlContent.Length;
            //}

            // Display the total count for all of the web addresses.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
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
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        async Task<int> ProcessURLAsync(string url, HttpClient client)
        {
            byte[] byteArray = await client.GetByteArrayAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each web site. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="34f1f-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34f1f-163">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [<span data-ttu-id="34f1f-164">Procedura dettagliata: accesso al Web tramite async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="34f1f-164">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
