---
title: Annullare attività asincrone dopo un periodo di tempo (C#)
description: Usare il metodo CancellationTokenSource. CancelAfter in C# per pianificare l'annullamento di tutte le attività associate non completate entro un periodo di tempo in questo esempio.
ms.date: 07/20/2015
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: f32af1d893c60ac17648f60fa3aa90adaa0383e8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925292"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="941f7-103">Annullare attività asincrone dopo un periodo di tempo (C#)</span><span class="sxs-lookup"><span data-stu-id="941f7-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="941f7-104">È possibile annullare un'operazione asincrona dopo un periodo di tempo tramite il metodo <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> se non si vuole attendere fino al completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="941f7-104">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="941f7-105">Questo metodo pianifica l'annullamento di qualsiasi attività associata che non è stata completata nel periodo di tempo designato dall'espressione `CancelAfter`.</span><span class="sxs-lookup"><span data-stu-id="941f7-105">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="941f7-106">Questo esempio viene aggiunto al codice sviluppato in [Annullare un'attività asincrona o un elenco di attività (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) per scaricare un elenco di siti Web e per visualizzare la lunghezza del contenuto di ogni sito.</span><span class="sxs-lookup"><span data-stu-id="941f7-106">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

> [!NOTE]
> <span data-ttu-id="941f7-107">Per eseguire gli esempi, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.</span><span class="sxs-lookup"><span data-stu-id="941f7-107">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="download-the-example"></a><span data-ttu-id="941f7-108">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="941f7-108">Download the example</span></span>

<span data-ttu-id="941f7-109">È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="941f7-109">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="941f7-110">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="941f7-110">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="941f7-111">Sulla barra dei menu scegliere **file**  >  **Apri**  >  **progetto/soluzione**.</span><span class="sxs-lookup"><span data-stu-id="941f7-111">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="941f7-112">Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato decompresso e aprire il file di soluzione (SLN) per AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="941f7-112">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="941f7-113">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **CancelAfterTime** e scegliere **Imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="941f7-113">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="941f7-114">Premere **F5** per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="941f7-114">Choose the **F5** key to run the project.</span></span> <span data-ttu-id="941f7-115">Oppure premere **CTRL** + **F5** per eseguire il progetto senza eseguirne il debug).</span><span class="sxs-lookup"><span data-stu-id="941f7-115">(Or, press **Ctrl**+**F5** to run the project without debugging it).</span></span>

6. <span data-ttu-id="941f7-116">Eseguire il programma più volte per verificare che l'output visualizzi il contenuto per tutti i siti Web, per nessun sito Web o per alcuni siti Web.</span><span class="sxs-lookup"><span data-stu-id="941f7-116">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>

<span data-ttu-id="941f7-117">Se non si vuole scaricare il progetto, è possibile rivedere il file MainWindow.xaml.cs alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="941f7-117">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>

## <a name="build-the-example"></a><span data-ttu-id="941f7-118">Compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="941f7-118">Build the example</span></span>

<span data-ttu-id="941f7-119">L'esempio riportato in questo argomento aggiunge codice al progetto sviluppato in [Annullare un'attività asincrona o un elenco di attività (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) per annullare un elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="941f7-119">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="941f7-120">L'esempio usa la stessa interfaccia utente, sebbene il pulsante **Annulla** non viene usato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="941f7-120">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>

<span data-ttu-id="941f7-121">Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione "Download dell'esempio", ma scegliere **CancelAListOfTasks** come **progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="941f7-121">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="941f7-122">Aggiungere al progetto le modifiche illustrate in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="941f7-122">Add the changes in this topic to that project.</span></span>

<span data-ttu-id="941f7-123">Per specificare un tempo massimo prima che le attività vengano contrassegnate come annullate, aggiungere una chiamata a `CancelAfter` al pulsante `startButton_Click`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="941f7-123">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="941f7-124">L'aggiunta viene contrassegnata con asterischi.</span><span class="sxs-lookup"><span data-stu-id="941f7-124">The addition is marked with asterisks.</span></span>

```csharp
private async void startButton_Click(object sender, RoutedEventArgs e)
{
    // Instantiate the CancellationTokenSource.
    cts = new CancellationTokenSource();

    resultsTextBox.Clear();

    try
    {
        // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
        // can adjust the time.)
        cts.CancelAfter(2500);

        await AccessTheWebAsync(cts.Token);
        resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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
```

 <span data-ttu-id="941f7-125">Eseguire il programma più volte per verificare che l'output visualizzi il contenuto per tutti i siti Web, per nessun sito Web o per alcuni siti Web.</span><span class="sxs-lookup"><span data-stu-id="941f7-125">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="941f7-126">L'output seguente rappresenta un esempio.</span><span class="sxs-lookup"><span data-stu-id="941f7-126">The following output is a sample.</span></span>

```output
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a><span data-ttu-id="941f7-127">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="941f7-127">Complete example</span></span>

<span data-ttu-id="941f7-128">Il codice seguente è il testo completo del file MainWindow.xaml.cs per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="941f7-128">The following code is the complete text of the MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="941f7-129">Gli asterischi contrassegnano gli elementi che sono stati aggiunti per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="941f7-129">Asterisks mark the elements that were added for this example.</span></span>

<span data-ttu-id="941f7-130">Si noti che è necessario aggiungere un riferimento per <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="941f7-130">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="941f7-131">È possibile scaricare il progetto da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="941f7-131">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

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

namespace CancelAfterTime
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
                // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
                // can adjust the time.)
                cts.CancelAfter(2500);

                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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

        // You can still include a Cancel button if you want to.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // Note that the Cancel button cancels all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Sample Output:

    // Length of the downloaded string: 35990.

    // Length of the downloaded string: 407399.

    // Length of the downloaded string: 226091.

    // Downloads canceled.
}
```

## <a name="see-also"></a><span data-ttu-id="941f7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="941f7-132">See also</span></span>

- [<span data-ttu-id="941f7-133">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="941f7-133">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="941f7-134">Procedura dettagliata: accesso al Web tramite async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="941f7-134">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="941f7-135">Annullare un'attività asincrona o un elenco di attività (C#)</span><span class="sxs-lookup"><span data-stu-id="941f7-135">Cancel an Async Task or a List of Tasks (C#)</span></span>](./cancel-an-async-task-or-a-list-of-tasks.md)
- [<span data-ttu-id="941f7-136">Ottimizzazione dell'applicazione asincrona (C#)</span><span class="sxs-lookup"><span data-stu-id="941f7-136">Fine-Tuning Your Async Application (C#)</span></span>](./fine-tuning-your-async-application.md)
- <span data-ttu-id="941f7-137">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="941f7-137">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
