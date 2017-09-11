---
title: 'Procedura: estendere la procedura dettagliata asincrona tramite Task. whenall (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 91cecc84899c9a87307ed5799485ec60ef341e65
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a><span data-ttu-id="16467-102">Procedura: estendere la procedura dettagliata asincrona tramite Task. whenall (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16467-102">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>
<span data-ttu-id="16467-103">È possibile migliorare le prestazioni della soluzione async in [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) utilizzando il <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>(metodo).</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="16467-103">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="16467-104">Questo metodo attende in modo asincrono di più operazioni asincrone vengono rappresentate come una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="16467-104">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>  
  
 <span data-ttu-id="16467-105">È possibile osservare nella procedura dettagliata che i siti Web di download a velocità diverse.</span><span class="sxs-lookup"><span data-stu-id="16467-105">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="16467-106">A volte uno dei siti Web è molto lento, che ritarda tutti i download rimanenti.</span><span class="sxs-lookup"><span data-stu-id="16467-106">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="16467-107">Quando si eseguono le soluzioni asincrone compilati nella procedura dettagliata, è possibile terminare il programma con facilità se non si desidera attendere, ma sarebbe un'opzione migliore per avviare tutti i download contemporaneamente e consentire più velocemente download continuare senza attendere che quello che viene ritardata.</span><span class="sxs-lookup"><span data-stu-id="16467-107">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>  
  
 <span data-ttu-id="16467-108">Si applica il `Task.WhenAll` (metodo) a una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="16467-108">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="16467-109">L'applicazione di `WhenAll` restituisce una singola attività che non è completezza fino al completamento di tutte le attività nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="16467-109">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="16467-110">Vengono visualizzate le attività eseguite in parallelo, ma non gli altri thread vengono creati.</span><span class="sxs-lookup"><span data-stu-id="16467-110">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="16467-111">Completare le attività in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="16467-111">The tasks can complete in any order.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="16467-112">Le procedure seguenti descrivono le estensioni per le applicazioni asincrone che sono state sviluppate [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="16467-112">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="16467-113">È possibile sviluppare le applicazioni completato la procedura dettagliata o del download del codice da [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span><span class="sxs-lookup"><span data-stu-id="16467-113">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
>   
>  <span data-ttu-id="16467-114">Per eseguire l'esempio, è necessario Visual Studio 2012 o versioni successive installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="16467-114">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>  
  
### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="16467-115">Per aggiungere alla soluzione di GetURLContentsAsync Task. whenall</span><span class="sxs-lookup"><span data-stu-id="16467-115">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>  
  
1.  <span data-ttu-id="16467-116">Aggiungere il `ProcessURLAsync` metodo per la prima applicazione che è stata sviluppata in [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="16467-116">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="16467-117">Se è stato scaricato il codice da [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), aprire il progetto AsyncWalkthrough e quindi aggiungere `ProcessURLAsync` al file MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="16467-117">If you downloaded the code from  [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="16467-118">Se il codice è stato creato completando la procedura dettagliata, aggiungere `ProcessURLAsync` all'applicazione che include il `GetURLContentsAsync` metodo.</span><span class="sxs-lookup"><span data-stu-id="16467-118">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="16467-119">Il file MainWindow.xaml.vb per questa applicazione è il primo esempio nella sezione "Codice esempi dalla procedura dettagliata completa".</span><span class="sxs-lookup"><span data-stu-id="16467-119">The MainWindow.xaml.vb file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="16467-120">Il `ProcessURLAsync` metodo consente di consolidare le azioni nel corpo del `For Each` ciclo `SumPageSizesAsync` nella procedura dettagliata originale.</span><span class="sxs-lookup"><span data-stu-id="16467-120">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="16467-121">Il metodo in modo asincrono Scarica il contenuto di un sito Web specificato come matrice di byte e quindi Visualizza e restituisce la lunghezza della matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="16467-121">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="16467-122">Impostare come commento o eliminare il `For Each` ciclo `SumPageSizesAsync`, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="16467-122">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
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
  
3.  <span data-ttu-id="16467-123">Creare una raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="16467-123">Create a collection of tasks.</span></span> <span data-ttu-id="16467-124">Il codice seguente definisce una [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) che, quando eseguita dal <xref:System.Linq.Enumerable.ToArray%2A>(metodo), crea una raccolta di attività che scaricare il contenuto di ogni sito Web.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="16467-124">The following code defines a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="16467-125">Le attività vengono avviate quando viene valutata la query.</span><span class="sxs-lookup"><span data-stu-id="16467-125">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="16467-126">Aggiungere il codice seguente al metodo `SumPageSizesAsync` dopo la dichiarazione di `urlList`.</span><span class="sxs-lookup"><span data-stu-id="16467-126">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.   
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="16467-127">Applicare `Task.WhenAll` alla raccolta di attività, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="16467-127">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="16467-128">`Task.WhenAll`Restituisce una singola attività che termina al completamento di tutte le attività nella raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="16467-128">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="16467-129">Nell'esempio seguente, il `Await` espressione attenderà il completamento dell'unico attività `WhenAll` restituisce.</span><span class="sxs-lookup"><span data-stu-id="16467-129">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="16467-130">L'espressione restituisce una matrice di interi, dove ogni valore integer è la lunghezza di un sito Web scaricato.</span><span class="sxs-lookup"><span data-stu-id="16467-130">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="16467-131">Aggiungere il codice seguente a `SumPageSizesAsync`, solo dopo il codice aggiunto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="16467-131">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="16467-132">Infine, utilizzare il <xref:System.Linq.Enumerable.Sum%2A>metodo per calcolare la somma delle lunghezze di tutti i siti Web.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="16467-132">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="16467-133">Aggiungere la riga seguente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="16467-133">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="16467-134">Per aggiungere la soluzione HttpClient.GetByteArrayAsync Task. whenall</span><span class="sxs-lookup"><span data-stu-id="16467-134">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>  
  
1.  <span data-ttu-id="16467-135">Aggiungere la seguente versione di `ProcessURLAsync` per la seconda applicazione che è stata sviluppata in [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="16467-135">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="16467-136">Se è stato scaricato il codice da [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), aprire il progetto AsyncWalkthrough_HttpClient e quindi aggiungere `ProcessURLAsync` al file MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="16467-136">If you downloaded the code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>  
  
    -   <span data-ttu-id="16467-137">Se il codice è stato creato completando la procedura dettagliata, aggiungere `ProcessURLAsync` all'applicazione che utilizza il `HttpClient.GetByteArrayAsync` metodo.</span><span class="sxs-lookup"><span data-stu-id="16467-137">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="16467-138">Il file MainWindow.xaml.vb per questa applicazione è il secondo esempio nella sezione "Codice esempi dalla procedura dettagliata completa".</span><span class="sxs-lookup"><span data-stu-id="16467-138">The MainWindow.xaml.vb file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>  
  
     <span data-ttu-id="16467-139">Il `ProcessURLAsync` metodo consente di consolidare le azioni nel corpo del `For Each` ciclo `SumPageSizesAsync` nella procedura dettagliata originale.</span><span class="sxs-lookup"><span data-stu-id="16467-139">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="16467-140">Il metodo in modo asincrono Scarica il contenuto di un sito Web specificato come matrice di byte e quindi Visualizza e restituisce la lunghezza della matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="16467-140">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>  
  
     <span data-ttu-id="16467-141">L'unica differenza rispetto di `ProcessURLAsync` metodo nella procedura precedente consiste nell'utilizzare il <xref:System.Net.Http.HttpClient>istanza, `client`.</xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="16467-141">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  <span data-ttu-id="16467-142">Impostare come commento o eliminare il `For Each` ciclo `SumPageSizesAsync`, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="16467-142">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>  
  
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
  
3.  <span data-ttu-id="16467-143">Definire un [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) che, quando eseguita dal <xref:System.Linq.Enumerable.ToArray%2A>(metodo), crea una raccolta di attività che scaricare il contenuto di ogni sito Web.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="16467-143">Define a [query](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="16467-144">Le attività vengono avviate quando viene valutata la query.</span><span class="sxs-lookup"><span data-stu-id="16467-144">The tasks are started when the query is evaluated.</span></span>  
  
     <span data-ttu-id="16467-145">Aggiungere il codice seguente al metodo `SumPageSizesAsync` dopo la dichiarazione di `client` e `urlList`.</span><span class="sxs-lookup"><span data-stu-id="16467-145">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>  
  
    ```vb  
    ' Create a query.  
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url, client)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  <span data-ttu-id="16467-146">Successivamente, si applicano `Task.WhenAll` alla raccolta di attività, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="16467-146">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="16467-147">`Task.WhenAll`Restituisce una singola attività che termina al completamento di tutte le attività nella raccolta di attività.</span><span class="sxs-lookup"><span data-stu-id="16467-147">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>  
  
     <span data-ttu-id="16467-148">Nell'esempio seguente, il `Await` espressione attenderà il completamento dell'unico attività `WhenAll` restituisce.</span><span class="sxs-lookup"><span data-stu-id="16467-148">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="16467-149">Al termine, il `Await` espressione restituisce una matrice di interi, dove ogni valore integer è la lunghezza di un sito Web scaricato.</span><span class="sxs-lookup"><span data-stu-id="16467-149">When complete, the `Await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="16467-150">Aggiungere il codice seguente a `SumPageSizesAsync`, solo dopo il codice aggiunto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="16467-150">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  <span data-ttu-id="16467-151">Infine, utilizzare il <xref:System.Linq.Enumerable.Sum%2A>metodo per ottenere la somma delle lunghezze di tutti i siti Web.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="16467-151">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="16467-152">Aggiungere la riga seguente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="16467-152">Add the following line to `SumPageSizesAsync`.</span></span>  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="16467-153">Per testare le soluzioni di Task. whenall</span><span class="sxs-lookup"><span data-stu-id="16467-153">To test the Task.WhenAll solutions</span></span>  
  
-   <span data-ttu-id="16467-154">Per entrambe le soluzioni, scegliere il tasto F5 per eseguire il programma, quindi il **avviare** pulsante.</span><span class="sxs-lookup"><span data-stu-id="16467-154">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="16467-155">L'output dovrebbe essere simile l'output dalle soluzioni async in [procedura dettagliata: accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="16467-155">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="16467-156">Tuttavia, si noti che i siti Web vengono visualizzati in un ordine diverso ogni volta.</span><span class="sxs-lookup"><span data-stu-id="16467-156">However, notice that the websites appear in a different order each time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16467-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="16467-157">Example</span></span>  
 <span data-ttu-id="16467-158">Il codice seguente mostra le estensioni per il progetto che utilizza il `GetURLContentsAsync` metodo per scaricare il contenuto dal web.</span><span class="sxs-lookup"><span data-stu-id="16467-158">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>  
  
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
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="example"></a><span data-ttu-id="16467-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="16467-159">Example</span></span>  
 <span data-ttu-id="16467-160">Il codice seguente mostra le estensioni per il progetto che usa metodo `HttpClient.GetByteArrayAsync` per scaricare il contenuto dal web.</span><span class="sxs-lookup"><span data-stu-id="16467-160">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>  
  
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
                "http://www.msdn.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="16467-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16467-161">See Also</span></span>  
 <span data-ttu-id="16467-162"><xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="16467-162"><xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="16467-163"> [Procedura dettagliata: Accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span><span class="sxs-lookup"><span data-stu-id="16467-163"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
