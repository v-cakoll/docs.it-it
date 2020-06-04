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
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a><span data-ttu-id="5b1a0-102">Procedura: Estendere la procedura dettagliata asincrona tramite Task.WhenAll (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b1a0-102">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>

<span data-ttu-id="5b1a0-103">È possibile migliorare le prestazioni della soluzione asincrona in [procedura dettagliata: accesso al Web tramite Async e await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md) tramite il <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-103">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5b1a0-104">Questo metodo mette in attesa più operazioni asincrone, rappresentate come una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-104">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>

<span data-ttu-id="5b1a0-105">Si noti che nella procedura dettagliata i siti Web vengono scaricati a velocità diverse.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-105">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="5b1a0-106">A volte un sito Web è molto lento e causa il ritardo di tutti i download rimanenti.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-106">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="5b1a0-107">Quando si eseguono le soluzioni asincrone compilate nella procedura dettagliata, è possibile terminare il programma con facilità se non si vuole attendere. Un'opzione migliore consiste nell'avviare tutti i download contemporaneamente e consentire a quelli più veloci di continuare senza attendere il termine di quello più lento.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-107">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>

<span data-ttu-id="5b1a0-108">Si applica il metodo `Task.WhenAll` a una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-108">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="5b1a0-109">L'applicazione di `WhenAll` restituisce una singola attività che non viene completata fino quando non vengono completate tutte le attività nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-109">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="5b1a0-110">Le attività vengono eseguite in parallelo, ma non vengono creati thread aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-110">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="5b1a0-111">Il completamento delle attività può avvenire in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-111">The tasks can complete in any order.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b1a0-112">Nelle procedure riportate di seguito vengono descritte le estensioni per le applicazioni asincrone sviluppate in [procedura dettagliata: accesso al Web tramite Async e await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="5b1a0-112">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="5b1a0-113">È possibile sviluppare le applicazioni completando la procedura dettagliata o scaricando il codice da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempi di codice per gli sviluppatori).</span><span class="sxs-lookup"><span data-stu-id="5b1a0-113">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>
>
> <span data-ttu-id="5b1a0-114">Per eseguire l'esempio, è necessario avere Visual Studio 2012 o versioni successive installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-114">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="5b1a0-115">Per aggiungere Task.WhenAll alla soluzione GetURLContentsAsync</span><span class="sxs-lookup"><span data-stu-id="5b1a0-115">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>

1. <span data-ttu-id="5b1a0-116">Aggiungere il `ProcessURLAsync` metodo alla prima applicazione sviluppata in [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="5b1a0-116">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="5b1a0-117">Se è stato scaricato il codice dagli [esempi di codice dello sviluppatore](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), aprire il progetto AsyncWalkthrough e quindi aggiungere `ProcessURLAsync` al file MainWindow. XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-117">If you downloaded the code from  [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>

    - <span data-ttu-id="5b1a0-118">Se il codice è stato sviluppato completando la procedura dettagliata, aggiungere `ProcessURLAsync` all'applicazione che include il metodo `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-118">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="5b1a0-119">Il file MainWindow. XAML. vb per questa applicazione è il primo esempio della sezione "esempi di codice completi della procedura dettagliata".</span><span class="sxs-lookup"><span data-stu-id="5b1a0-119">The MainWindow.xaml.vb file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>

     <span data-ttu-id="5b1a0-120">Il metodo `ProcessURLAsync` consente di consolidare le azioni nel corpo del ciclo `For Each` in `SumPageSizesAsync` nella procedura dettagliata originale.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-120">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="5b1a0-121">Il metodo scarica in modo asincrono il contenuto di un sito Web specificato come matrice di byte e quindi visualizza e restituisce la lunghezza della matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-121">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

    ```vb
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. <span data-ttu-id="5b1a0-122">Impostare come commento o eliminare il ciclo `For Each` in `SumPageSizesAsync`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-122">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

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

3. <span data-ttu-id="5b1a0-123">Creare una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-123">Create a collection of tasks.</span></span> <span data-ttu-id="5b1a0-124">Il codice seguente definisce una [query](../linq/index.md) che, quando eseguita dal metodo <xref:System.Linq.Enumerable.ToArray%2A>, crea una raccolta di attività che scaricano il contenuto di ogni sito Web.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-124">The following code defines a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="5b1a0-125">Le attività vengono avviate quando viene valutata la query.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-125">The tasks are started when the query is evaluated.</span></span>

     <span data-ttu-id="5b1a0-126">Aggiungere il codice seguente al metodo `SumPageSizesAsync` dopo la dichiarazione di `urlList`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-126">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. <span data-ttu-id="5b1a0-127">Applicare `Task.WhenAll` alla raccolta di attività, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-127">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="5b1a0-128">`Task.WhenAll` restituisce una singola attività che termina al completamento di tutte le attività della raccolta.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-128">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

     <span data-ttu-id="5b1a0-129">Nell'esempio seguente, l'espressione `Await` mette in attesa il completamento della singola attività restituita da `WhenAll`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-129">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="5b1a0-130">L'espressione restituisce una matrice di numeri interi, dove ogni numero intero rappresenta la lunghezza di un sito Web scaricato.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-130">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="5b1a0-131">Aggiungere il codice seguente a `SumPageSizesAsync`, dopo il codice aggiunto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-131">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. <span data-ttu-id="5b1a0-132">Infine, usare il metodo <xref:System.Linq.Enumerable.Sum%2A> per calcolare la somma delle lunghezze di tutti i siti Web.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-132">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="5b1a0-133">Aggiungere la riga seguente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-133">Add the following line to `SumPageSizesAsync`.</span></span>

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="5b1a0-134">Per aggiungere Task.WhenAll alla soluzione HttpClient.GetByteArrayAsync</span><span class="sxs-lookup"><span data-stu-id="5b1a0-134">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>

1. <span data-ttu-id="5b1a0-135">Aggiungere la versione seguente di `ProcessURLAsync` alla seconda applicazione sviluppata in [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="5b1a0-135">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="5b1a0-136">Se è stato scaricato il codice dagli [esempi di codice dello sviluppatore](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), aprire il progetto AsyncWalkthrough_HttpClient e quindi aggiungere `ProcessURLAsync` al file MainWindow. XAML. vb.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-136">If you downloaded the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>

    - <span data-ttu-id="5b1a0-137">Se il codice è stato sviluppato completando la procedura dettagliata, aggiungere `ProcessURLAsync` all'applicazione che usa il metodo `HttpClient.GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-137">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="5b1a0-138">Il file MainWindow. XAML. vb per questa applicazione è il secondo esempio della sezione "esempi di codice completi della procedura dettagliata".</span><span class="sxs-lookup"><span data-stu-id="5b1a0-138">The MainWindow.xaml.vb file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>

     <span data-ttu-id="5b1a0-139">Il metodo `ProcessURLAsync` consente di consolidare le azioni nel corpo del ciclo `For Each` in `SumPageSizesAsync` nella procedura dettagliata originale.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-139">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="5b1a0-140">Il metodo scarica in modo asincrono il contenuto di un sito Web specificato come matrice di byte e quindi visualizza e restituisce la lunghezza della matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-140">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

     <span data-ttu-id="5b1a0-141">L'unica differenza rispetto al metodo `ProcessURLAsync` nella procedura precedente consiste nell'uso dell'istanza di <xref:System.Net.Http.HttpClient>, `client`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-141">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>

    ```vb
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. <span data-ttu-id="5b1a0-142">Impostare come commento o eliminare il ciclo `For Each` in `SumPageSizesAsync`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-142">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

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

3. <span data-ttu-id="5b1a0-143">Definire una [query](../linq/index.md) che, quando eseguita dal metodo <xref:System.Linq.Enumerable.ToArray%2A>, crea una raccolta di attività che scaricano il contenuto di ogni sito Web.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-143">Define a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="5b1a0-144">Le attività vengono avviate quando viene valutata la query.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-144">The tasks are started when the query is evaluated.</span></span>

     <span data-ttu-id="5b1a0-145">Aggiungere il codice seguente al metodo `SumPageSizesAsync` dopo la dichiarazione di `client` e `urlList`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-145">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. <span data-ttu-id="5b1a0-146">In seguito applicare `Task.WhenAll` alla raccolta di attività, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-146">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="5b1a0-147">`Task.WhenAll` restituisce una singola attività che termina al completamento di tutte le attività della raccolta.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-147">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

     <span data-ttu-id="5b1a0-148">Nell'esempio seguente, l'espressione `Await` mette in attesa il completamento della singola attività restituita da `WhenAll`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-148">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="5b1a0-149">Al termine dell'operazione, l'espressione `Await` restituisce una matrice di numeri interi, dove ogni numero intero rappresenta la lunghezza di un sito Web scaricato.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-149">When complete, the `Await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="5b1a0-150">Aggiungere il codice seguente a `SumPageSizesAsync`, dopo il codice aggiunto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-150">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. <span data-ttu-id="5b1a0-151">Infine, usare il metodo <xref:System.Linq.Enumerable.Sum%2A> per ottenere la somma delle lunghezze di tutti i siti Web.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-151">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="5b1a0-152">Aggiungere la riga seguente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-152">Add the following line to `SumPageSizesAsync`.</span></span>

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="5b1a0-153">Per testare le soluzioni Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="5b1a0-153">To test the Task.WhenAll solutions</span></span>

<span data-ttu-id="5b1a0-154">Per tutte le soluzioni, premere F5 per eseguire il programma e scegliere il pulsante **Start**.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-154">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="5b1a0-155">L'output dovrebbe essere simile all'output delle soluzioni asincrone in [procedura dettagliata: accesso al Web tramite Async e await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="5b1a0-155">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="5b1a0-156">Tuttavia, si noti che i siti Web vengono visualizzati ogni volta in un ordine diverso.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-156">However, notice that the websites appear in a different order each time.</span></span>

## <a name="example"></a><span data-ttu-id="5b1a0-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b1a0-157">Example</span></span>

<span data-ttu-id="5b1a0-158">Il codice seguente illustra le estensioni per il progetto che usa il metodo `GetURLContentsAsync` per scaricare il contenuto dal Web.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-158">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>

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

## <a name="example"></a><span data-ttu-id="5b1a0-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b1a0-159">Example</span></span>

<span data-ttu-id="5b1a0-160">Il codice seguente illustra le estensioni per il progetto che usa il metodo `HttpClient.GetByteArrayAsync` per scaricare il contenuto dal Web.</span><span class="sxs-lookup"><span data-stu-id="5b1a0-160">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5b1a0-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b1a0-161">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5b1a0-162">Procedura dettagliata: accesso al Web con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b1a0-162">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](walkthrough-accessing-the-web-by-using-async-and-await.md)
