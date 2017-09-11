---
title: "Procedura: Eseguire più richieste Web in parallelo tramite async e await (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 19745899-f97a-4499-a7c7-e813d1447580
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bfa7781241b837f353fe34d43b8cc6ab82f15564
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-c"></a><span data-ttu-id="7bc9a-102">Procedura: Eseguire più richieste Web in parallelo tramite async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="7bc9a-102">How to: Make Multiple Web Requests in Parallel by Using async and await (C#)</span></span>
<span data-ttu-id="7bc9a-103">In un metodo asincrono le attività vengono avviate al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-103">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="7bc9a-104">L'operatore [await](../../../../csharp/language-reference/keywords/await.md) viene applicato all'attività in un punto del metodo in cui è impossibile continuare l'elaborazione finché l'attività non è terminata.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-104">The [await](../../../../csharp/language-reference/keywords/await.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="7bc9a-105">Spesso un'attività viene messa in attesa al momento della creazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-105">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>  
  
```csharp  
var result = await someWebAccessMethodAsync(url);  
```  
  
 <span data-ttu-id="7bc9a-106">Tuttavia, è possibile separare la creazione dalla messa in attesa dell'attività se il programma ha altro lavoro da eseguire che non dipende dal completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-106">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>  
  
```csharp  
// The following line creates and starts the task.  
var myTask = someWebAccessMethodAsync(url);  
  
// While the task is running, you can do other work that doesn't depend  
// on the results of the task.  
// . . . . .  
  
// The application of await suspends the rest of this method until the task is complete.  
var result = await myTask;  
```  
  
 <span data-ttu-id="7bc9a-107">Tra l'avvio di un'attività e la messa in attesa, è possibile avviare altre attività.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-107">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="7bc9a-108">Le attività aggiuntive vengono eseguite in modo implicito in parallelo, ma non vengono creati thread aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-108">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>  
  
 <span data-ttu-id="7bc9a-109">Il programma seguente avvia tre download Web asincroni e quindi li mette in attesa nell'ordine in cui vengono chiamati.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-109">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="7bc9a-110">Si noti che, quando si esegue il programma, non sempre le attività finiscono nell'ordine in cui sono state create e messe in attesa.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-110">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="7bc9a-111">Vengono avviate al momento della creazione ed è possibile che una o più di una finiscano prima che il metodo raggiunga le espressioni await.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-111">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bc9a-112">Per completare il progetto, è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-112">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>  
  
 <span data-ttu-id="7bc9a-113">Per un altro esempio che avvii più operazioni contemporaneamente, vedere [Procedura: Estendere la procedura dettagliata asincrona usando Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="7bc9a-113">For another example that starts multiple tasks at the same time, see [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="7bc9a-114">È possibile scaricare il codice per l'esempio da [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=254906) (Esempi di codice per sviluppatori).</span><span class="sxs-lookup"><span data-stu-id="7bc9a-114">You can download the code for this example from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=254906).</span></span>  
  
### <a name="to-set-up-the-project"></a><span data-ttu-id="7bc9a-115">Per impostare il progetto</span><span class="sxs-lookup"><span data-stu-id="7bc9a-115">To set up the project</span></span>  
  
1.  <span data-ttu-id="7bc9a-116">Per configurare un'applicazione WPF, completare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-116">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="7bc9a-117">È possibile trovare istruzioni dettagliate per i passaggi in [Procedura dettagliata: Accesso al Web tramite async e await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="7bc9a-117">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="7bc9a-118">Creare un'applicazione WPF che contenga una casella di testo e un pulsante.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-118">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="7bc9a-119">Denominare il pulsante `startButton` e la casella di testo `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-119">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="7bc9a-120">Aggiunge un riferimento a <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-120">Add a reference for <xref:System.Net.Http>.</span></span>  
  
    -   <span data-ttu-id="7bc9a-121">Nel file MainWindow.xaml.cs aggiungere una direttiva `using` per `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-121">In the MainWindow.xaml.cs file, add a `using` directive for `System.Net.Http`.</span></span>  
  
### <a name="to-add-the-code"></a><span data-ttu-id="7bc9a-122">Per aggiungere il codice</span><span class="sxs-lookup"><span data-stu-id="7bc9a-122">To add the code</span></span>  
  
1.  <span data-ttu-id="7bc9a-123">Nella finestra di progettazione MainWindow.xaml fare doppio clic sul pulsante per creare il gestore eventi `startButton_Click` in MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-123">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="7bc9a-124">Copiare il codice seguente e incollarlo nel corpo di `startButton_Click` in MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-124">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.cs.</span></span>  
  
    ```csharp  
    resultsTextBox.Clear();  
    await CreateMultipleTasksAsync();  
    resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
    ```  
  
     <span data-ttu-id="7bc9a-125">Il codice chiama un metodo asincrono, `CreateMultipleTasksAsync`, che avvia l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-125">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>  
  
3.  <span data-ttu-id="7bc9a-126">Aggiungere i metodi di supporto seguenti al progetto:</span><span class="sxs-lookup"><span data-stu-id="7bc9a-126">Add the following support methods to the project:</span></span>  
  
    -   <span data-ttu-id="7bc9a-127">`ProcessURLAsync` usa un metodo <xref:System.Net.Http.HttpClient> per scaricare il contenuto di un sito Web come matrice di byte.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-127">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="7bc9a-128">Il metodo di supporto `ProcessURLAsync` visualizza e restituisce la lunghezza della matrice.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-128">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>  
  
    -   <span data-ttu-id="7bc9a-129">`DisplayResults` visualizza il numero di byte della matrice di byte per ogni URL.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-129">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="7bc9a-130">Questa visualizzazione indica quando ogni attività ha terminato il download.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-130">This display shows when each task has finished downloading.</span></span>  
  
     <span data-ttu-id="7bc9a-131">Copiare i metodi seguenti e incollarli dopo il gestore eventi `startButton_Click` in MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-131">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
    ```csharp  
    async Task<int> ProcessURLAsync(string url, HttpClient client)  
    {  
        var byteArray = await client.GetByteArrayAsync(url);  
        DisplayResults(url, byteArray);  
        return byteArray.Length;  
    }  
  
    private void DisplayResults(string url, byte[] content)  
    {  
        // Display the length of each website. The string format   
        // is designed to be used with a monospaced font, such as  
        // Lucida Console or Global Monospace.  
        var bytes = content.Length;  
        // Strip off the "http://".  
        var displayURL = url.Replace("http://", "");  
        resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
    }  
    ```  
  
4.  <span data-ttu-id="7bc9a-132">Infine, definire il metodo `CreateMultipleTasksAsync`, che esegue i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-132">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>  
  
    -   <span data-ttu-id="7bc9a-133">Il metodo dichiara un oggetto `HttpClient`, che è necessario per accedere al metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-133">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>  
  
    -   <span data-ttu-id="7bc9a-134">Il metodo crea e avvia tre attività di tipo <xref:System.Threading.Tasks.Task%601>, dove `TResult` è un numero intero.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-134">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="7bc9a-135">Al termine di ogni attività, `DisplayResults` vengono visualizzati l'URL dell'attività e la lunghezza del contenuto scaricato.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-135">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="7bc9a-136">Poiché le attività sono in esecuzione in modo asincrono, l'ordine in cui vengono visualizzati i risultati potrebbe essere diverso da quello in cui le attività sono stati dichiarate.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-136">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>  
  
    -   <span data-ttu-id="7bc9a-137">Il metodo attende il completamento di ogni attività.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-137">The method awaits the completion of each task.</span></span> <span data-ttu-id="7bc9a-138">Ogni operatore `await` sospende l'esecuzione di `CreateMultipleTasksAsync` finché non viene completata l'attività in attesa.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-138">Each `await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="7bc9a-139">L'operatore recupera anche il valore restituito dalla chiamata a `ProcessURLAsync` da ogni attività completata.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-139">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>  
  
    -   <span data-ttu-id="7bc9a-140">Quando sono state completate le attività e sono stati recuperati i valori interi, il metodo somma le lunghezze dei siti Web e visualizza il risultato.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-140">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>  
  
     <span data-ttu-id="7bc9a-141">Copiare il metodo seguente e incollarlo nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-141">Copy the following method, and paste it into your solution.</span></span>  
  
    ```csharp  
    private async Task CreateMultipleTasksAsync()  
    {  
        // Declare an HttpClient object, and increase the buffer size. The  
        // default buffer size is 65,536.  
        HttpClient client =  
            new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
        // Create and start the tasks. As each task finishes, DisplayResults   
        // displays its length.  
        Task<int> download1 =   
            ProcessURLAsync("http://msdn.microsoft.com", client);  
        Task<int> download2 =   
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
        Task<int> download3 =   
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
        // Await each task.  
        int length1 = await download1;  
        int length2 = await download2;  
        int length3 = await download3;  
  
        int total = length1 + length2 + length3;  
  
        // Display the total count for the downloaded websites.  
        resultsTextBox.Text +=  
            string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
    }  
    ```  
  
5.  <span data-ttu-id="7bc9a-142">Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .</span><span class="sxs-lookup"><span data-stu-id="7bc9a-142">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="7bc9a-143">Eseguire il programma più volte per verificare che le tre attività non vengano completate sempre nello stesso ordine e che l'ordine in cui vengono completate non è necessariamente l'ordine in cui sono state create e messe in attesa.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-143">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bc9a-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bc9a-144">Example</span></span>  
 <span data-ttu-id="7bc9a-145">Il codice seguente contiene l'esempio completo.</span><span class="sxs-lookup"><span data-stu-id="7bc9a-145">The following code contains the full example.</span></span>  
  
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
  
// Add the following using directive, and add a reference for System.Net.Http.  
using System.Net.Http;  
  
namespace AsyncExample_MultipleTasks  
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
            await CreateMultipleTasksAsync();  
            resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
        }  
  
        private async Task CreateMultipleTasksAsync()  
        {  
            // Declare an HttpClient object, and increase the buffer size. The  
            // default buffer size is 65,536.  
            HttpClient client =  
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
            // Create and start the tasks. As each task finishes, DisplayResults   
            // displays its length.  
            Task<int> download1 =   
                ProcessURLAsync("http://msdn.microsoft.com", client);  
            Task<int> download2 =   
                ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
            Task<int> download3 =   
                ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
            // Await each task.  
            int length1 = await download1;  
            int length2 = await download2;  
            int length3 = await download3;  
  
            int total = length1 + length2 + length3;  
  
            // Display the total count for the downloaded websites.  
            resultsTextBox.Text +=  
                string.Format("\r\n\r\nTotal bytes returned:  {0}\r\n", total);  
        }  
  
        async Task<int> ProcessURLAsync(string url, HttpClient client)  
        {  
            var byteArray = await client.GetByteArrayAsync(url);  
            DisplayResults(url, byteArray);  
            return byteArray.Length;  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format   
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "http://".  
            var displayURL = url.Replace("http://", "");  
            resultsTextBox.Text += string.Format("\n{0,-58} {1,8}", displayURL, bytes);  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bc9a-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bc9a-146">See Also</span></span>  
 <span data-ttu-id="7bc9a-147">[Procedura dettagliata: Accesso al Web tramite async e await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="7bc9a-147">[Walkthrough: Accessing the Web by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
 <span data-ttu-id="7bc9a-148">[Programmazione asincrona con async e await (C#)](../../../../csharp/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="7bc9a-148">[Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md) </span></span>  
 [<span data-ttu-id="7bc9a-149">Procedura: Estendere la procedura dettagliata asincrona usando Task.WhenAll (C#)</span><span class="sxs-lookup"><span data-stu-id="7bc9a-149">How to: Extend the async Walkthrough by Using Task.WhenAll (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)

