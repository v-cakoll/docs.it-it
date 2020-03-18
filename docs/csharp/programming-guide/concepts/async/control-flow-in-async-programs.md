---
title: Flusso di controllo in programmi asincroni (C#)
ms.date: 07/20/2015
ms.assetid: fc92b08b-fe1d-4d07-84ab-5192fafe06bb
ms.openlocfilehash: 99f80a86f14179c5f270064a9f96e35f8611ef13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204438"
---
# <a name="control-flow-in-async-programs-c"></a><span data-ttu-id="7a9b5-102">Flusso di controllo in programmi asincroni (C#)</span><span class="sxs-lookup"><span data-stu-id="7a9b5-102">Control flow in async programs (C#)</span></span>

<span data-ttu-id="7a9b5-103">Le parole chiave `async` e `await` consentono di scrivere e gestire più facilmente i programmi asincroni.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-103">You can write and maintain asynchronous programs more easily by using the `async` and `await` keywords.</span></span> <span data-ttu-id="7a9b5-104">Tuttavia, i risultati potrebbero creare perplessità se non si conosce il funzionamento del programma.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="7a9b5-105">Questo argomento descrive il flusso di controllo attraverso un programma asincrono semplice per indicare quando il controllo si sposta da un metodo a un altro e quali informazioni vengono trasferite ogni volta.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>

<span data-ttu-id="7a9b5-106">In generale, si contrassegnano i metodi che contengono codice asincrono con il modificatore [async (C#)](../../../language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="7a9b5-106">In general, you mark methods that contain asynchronous code with the [async (C#)](../../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="7a9b5-107">In un metodo contrassegnato con un modificatore async è possibile usare un operatore [await (C#)](../../../language-reference/operators/await.md) per specificare dove il metodo viene sospeso in attesa del completamento di un processo asincrono chiamato.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-107">In a method that's marked with an async modifier, you can use an [await (C#)](../../../language-reference/operators/await.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="7a9b5-108">Per altre informazioni, vedere [Programmazione asincrona con async e await (C#)](./index.md).</span><span class="sxs-lookup"><span data-stu-id="7a9b5-108">For more information, see [Asynchronous Programming with async and await (C#)](./index.md).</span></span>

<span data-ttu-id="7a9b5-109">L'esempio seguente usa i metodi asincroni per scaricare come stringa il contenuto di un sito Web specificato e per visualizzare la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-109">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="7a9b5-110">L'esempio contiene i due metodi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-110">The example contains the following two methods.</span></span>

- <span data-ttu-id="7a9b5-111">`startButton_Click`, che chiama `AccessTheWebAsync` e visualizza il risultato.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-111">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>

- <span data-ttu-id="7a9b5-112">`AccessTheWebAsync`, che scarica il contenuto di un sito Web come stringa e restituisce la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-112">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="7a9b5-113">`AccessTheWebAsync` usa un metodo <xref:System.Net.Http.HttpClient> asincrono, ovvero <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, per scaricare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-113">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>

<span data-ttu-id="7a9b5-114">In corrispondenza dei punti strategici del programma sono visualizzate righe numerate che consentono di comprendere come viene eseguito il programma e spiegano che cosa accade in ogni punto contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-114">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="7a9b5-115">Le righe sono evidenziate con etichette numerate da "ONE" a "SIX."</span><span class="sxs-lookup"><span data-stu-id="7a9b5-115">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="7a9b5-116">Le etichette rappresentano l'ordine in cui il programma raggiunge queste righe di codice.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-116">The labels represent the order in which the program reaches these lines of code.</span></span>

<span data-ttu-id="7a9b5-117">Il codice seguente rappresenta una struttura del programma.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-117">The following code shows an outline of the program.</span></span>

```csharp
public partial class MainWindow : Window
{
    // . . .
    private async void startButton_Click(object sender, RoutedEventArgs e)
    {
        // ONE
        Task<int> getLengthTask = AccessTheWebAsync();

        // FOUR
        int contentLength = await getLengthTask;

        // SIX
        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {contentLength}.\r\n";
    }

    async Task<int> AccessTheWebAsync()
    {
        // TWO
        HttpClient client = new HttpClient();
        Task<string> getStringTask =
            client.GetStringAsync("https://msdn.microsoft.com");

        // THREE
        string urlContents = await getStringTask;

        // FIVE
        return urlContents.Length;
    }
}
```

<span data-ttu-id="7a9b5-118">Ognuna delle posizioni con etichetta da "ONE" a "SIX" visualizza informazioni sullo stato corrente del programma.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-118">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="7a9b5-119">Viene generato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7a9b5-119">The following output is produced:</span></span>

```output
ONE:   Entering startButton_Click.
           Calling AccessTheWebAsync.

TWO:   Entering AccessTheWebAsync.
           Calling HttpClient.GetStringAsync.

THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.

FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.

FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.

SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.

Length of the downloaded string: 33946.
```

## <a name="set-up-the-program"></a><span data-ttu-id="7a9b5-120">Impostare il programma</span><span class="sxs-lookup"><span data-stu-id="7a9b5-120">Set up the program</span></span>

<span data-ttu-id="7a9b5-121">È possibile scaricare il codice usato in questo argomento da MSDN oppure crearlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-121">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>

> [!NOTE]
> <span data-ttu-id="7a9b5-122">Per eseguire l'esempio, è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-122">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="download-the-program"></a><span data-ttu-id="7a9b5-123">Scaricare il programma</span><span class="sxs-lookup"><span data-stu-id="7a9b5-123">Download the program</span></span>

<span data-ttu-id="7a9b5-124">È possibile scaricare l'applicazione di questo argomento da [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) (Esempio di attività asincrona: flusso di controllo in programmi asincroni).</span><span class="sxs-lookup"><span data-stu-id="7a9b5-124">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span></span> <span data-ttu-id="7a9b5-125">I passaggi seguenti consentono di aprire ed eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-125">The following steps open and run the program.</span></span>

1. <span data-ttu-id="7a9b5-126">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-126">Unzip the downloaded file, and then start Visual Studio.</span></span>

2. <span data-ttu-id="7a9b5-127">Nella barra dei menu scegliere**Apri** > **progetto/soluzione** **apri file** > .</span><span class="sxs-lookup"><span data-stu-id="7a9b5-127">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="7a9b5-128">Passare alla cartella che contiene il codice di esempio decompresso, aprire il file di soluzione (sln) e quindi premere **F5** per compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-128">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the **F5** key to build and run the project.</span></span>

### <a name="create-the-program-yourself"></a><span data-ttu-id="7a9b5-129">Creare il programma autonomamente</span><span class="sxs-lookup"><span data-stu-id="7a9b5-129">Create the program Yourself</span></span>

<span data-ttu-id="7a9b5-130">Il seguente progetto Windows Presentation Foundation (WPF) contiene gli esempi di codice per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-130">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>

<span data-ttu-id="7a9b5-131">Per eseguire il progetto, effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a9b5-131">To run the project, perform the following steps:</span></span>

1. <span data-ttu-id="7a9b5-132">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-132">Start Visual Studio.</span></span>

2. <span data-ttu-id="7a9b5-133">Nella barra dei menu scegliere **File** > **Nuovo** > **progetto**.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-133">On the menu bar, choose **File** > **New** > **Project**.</span></span>

     <span data-ttu-id="7a9b5-134">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="7a9b5-134">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="7a9b5-135">Scegliere la categoria**Desktop di Windows** **di** > **Visual C,** > quindi scegliere **App WPF** dall'elenco dei modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-135">Choose the **Installed** > **Visual C#** > **Windows Desktop** category, and then choose **WPF App** from the list of project templates.</span></span>

4. <span data-ttu-id="7a9b5-136">Immettere `AsyncTracer` come nome del progetto, quindi scegliere il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-136">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>

     <span data-ttu-id="7a9b5-137">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-137">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="7a9b5-138">Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="7a9b5-138">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="7a9b5-139">Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow.xaml in **Esplora soluzioni** e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-139">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

6. <span data-ttu-id="7a9b5-140">Nella visualizzazione **XAML** di MainWindow.xaml sostituire il codice con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-140">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```csharp
    <Window
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="AsyncTracer.MainWindow"
            Title="Control Flow Trace" Height="350" Width="592">
        <Grid>
            <Button x:Name="startButton" Content="Start
    " HorizontalAlignment="Left" Margin="250,10,0,0" VerticalAlignment="Top" Width="75" Height="24"  Click="startButton_Click" d:LayoutOverrides="GridBox"/>
            <TextBox x:Name="resultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="576" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" Grid.ColumnSpan="3"/>
        </Grid>
    </Window>
    ```

     <span data-ttu-id="7a9b5-141">Nella visualizzazione **Progettazione** di MainWindow.xaml viene visualizzata una finestra semplice contenente una casella di testo e un pulsante.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-141">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

7. <span data-ttu-id="7a9b5-142">Aggiunge un riferimento a <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-142">Add a reference for <xref:System.Net.Http>.</span></span>

8. <span data-ttu-id="7a9b5-143">In **Esplora soluzioni** aprire il menu di scelta rapida per MainWindow.xaml.cs e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-143">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>

9. <span data-ttu-id="7a9b5-144">Sostituire il codice in MainWindow.xaml.cs con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-144">In MainWindow.xaml.cs, replace the code with the following code.</span></span>

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

    // Add a using directive and a reference for System.Net.Http;
    using System.Net.Http;

    namespace AsyncTracer
    {
        public partial class MainWindow : Window
        {
            public MainWindow()
            {
                InitializeComponent();
            }

            private async void startButton_Click(object sender, RoutedEventArgs e)
            {
                // The display lines in the example lead you through the control shifts.
                resultsTextBox.Text += "ONE:   Entering startButton_Click.\r\n" +
                    "           Calling AccessTheWebAsync.\r\n";

                Task<int> getLengthTask = AccessTheWebAsync();

                resultsTextBox.Text += "\r\nFOUR:  Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is started.\r\n" +
                    "           About to await getLengthTask -- no caller to return to.\r\n";

                int contentLength = await getLengthTask;

                resultsTextBox.Text += "\r\nSIX:   Back in startButton_Click.\r\n" +
                    "           Task getLengthTask is finished.\r\n" +
                    "           Result from AccessTheWebAsync is stored in contentLength.\r\n" +
                    "           About to display contentLength and exit.\r\n";

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }

            async Task<int> AccessTheWebAsync()
            {
                resultsTextBox.Text += "\r\nTWO:   Entering AccessTheWebAsync.";

                // Declare an HttpClient object.
                HttpClient client = new HttpClient();

                resultsTextBox.Text += "\r\n           Calling HttpClient.GetStringAsync.\r\n";

                // GetStringAsync returns a Task<string>.
                Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");

                resultsTextBox.Text += "\r\nTHREE: Back in AccessTheWebAsync.\r\n" +
                    "           Task getStringTask is started.";

                // AccessTheWebAsync can continue to work until getStringTask is awaited.

                resultsTextBox.Text +=
                    "\r\n           About to await getStringTask and return a Task<int> to startButton_Click.\r\n";

                // Retrieve the website contents when task is complete.
                string urlContents = await getStringTask;

                resultsTextBox.Text += "\r\nFIVE:  Back in AccessTheWebAsync." +
                    "\r\n           Task getStringTask is complete." +
                    "\r\n           Processing the return statement." +
                    "\r\n           Exiting from AccessTheWebAsync.\r\n";

                return urlContents.Length;
            }
        }
    }
    ```

10. <span data-ttu-id="7a9b5-145">Premere **F5** per eseguire il programma e quindi scegliere il pulsante **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-145">Choose the **F5** key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="7a9b5-146">Viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7a9b5-146">The following output appears:</span></span>

    ```output
    ONE:   Entering startButton_Click.
               Calling AccessTheWebAsync.

    TWO:   Entering AccessTheWebAsync.
               Calling HttpClient.GetStringAsync.

    THREE: Back in AccessTheWebAsync.
               Task getStringTask is started.
               About to await getStringTask & return a Task<int> to startButton_Click.

    FOUR:  Back in startButton_Click.
               Task getLengthTask is started.
               About to await getLengthTask -- no caller to return to.

    FIVE:  Back in AccessTheWebAsync.
               Task getStringTask is complete.
               Processing the return statement.
               Exiting from AccessTheWebAsync.

    SIX:   Back in startButton_Click.
               Task getLengthTask is finished.
               Result from AccessTheWebAsync is stored in contentLength.
               About to display contentLength and exit.

    Length of the downloaded string: 33946.
    ```

## <a name="trace-the-program"></a><span data-ttu-id="7a9b5-147">Analizzare il programma</span><span class="sxs-lookup"><span data-stu-id="7a9b5-147">Trace the program</span></span>

### <a name="steps-one-and-two"></a><span data-ttu-id="7a9b5-148">Passaggi UNO e DUE</span><span class="sxs-lookup"><span data-stu-id="7a9b5-148">Steps ONE and TWO</span></span>

<span data-ttu-id="7a9b5-149">Le prime due righe di visualizzazione tracciano il percorso poiché `startButton_Click` chiama `AccessTheWebAsync` e `AccessTheWebAsync` chiama il metodo asincrono <xref:System.Net.Http.HttpClient>, ovvero <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-149">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="7a9b5-150">Nell'immagine seguente vengono illustrate le chiamate metodo a metodo.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-150">The following image outlines the calls from method to method.</span></span>

<span data-ttu-id="7a9b5-151">![Passaggi UNO e DUE](./media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span><span class="sxs-lookup"><span data-stu-id="7a9b5-151">![Steps ONE and TWO](./media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>

<span data-ttu-id="7a9b5-152">Il tipo restituito di `AccessTheWebAsync` e `client.GetStringAsync` è <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-152">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="7a9b5-153">Per `AccessTheWebAsync` TResult è un numero intero.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-153">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="7a9b5-154">Per `GetStringAsync` TResult è una stringa.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-154">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="7a9b5-155">Per altre informazioni sui tipi restituiti dei metodi asincroni, vedere [Tipi restituiti asincroni (C#)](./async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="7a9b5-155">For more information about async method return types, see [Async Return Types (C#)](./async-return-types.md).</span></span>

<span data-ttu-id="7a9b5-156">Un metodo asincrono che restituisce un'attività restituisce un'istanza dell'attività quando il controllo torna al chiamante.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-156">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="7a9b5-157">Il controllo viene restituito da un metodo asincrono al relativo chiamante quando viene rilevato un operatore `await` nel metodo chiamato o quando termina il metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-157">Control returns from an async method to its caller either when an `await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="7a9b5-158">Le righe evidenziate con le etichette da "THREE" a "SIX" analizzano questa parte del processo.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-158">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>

### <a name="step-three"></a><span data-ttu-id="7a9b5-159">Passaggio TRE</span><span class="sxs-lookup"><span data-stu-id="7a9b5-159">Step THREE</span></span>

<span data-ttu-id="7a9b5-160">In `AccessTheWebAsync`, il metodo asincrono <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> viene chiamato per scaricare il contenuto della pagina Web di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-160">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="7a9b5-161">Il controllo viene restituito da `client.GetStringAsync` a `AccessTheWebAsync` quando viene restituito `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-161">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>

 <span data-ttu-id="7a9b5-162">Il metodo `client.GetStringAsync` restituisce un'attività di stringa che viene assegnata alla variabile `getStringTask` in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-162">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="7a9b5-163">La riga seguente nel programma di esempio indica la chiamata a `client.GetStringAsync` e l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-163">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>

```csharp
Task<string> getStringTask = client.GetStringAsync("https://msdn.microsoft.com");
```

 <span data-ttu-id="7a9b5-164">Si può pensare all'attività come a una promessa fatta da `client.GetStringAsync` di produrre una stringa reale alla fine.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-164">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="7a9b5-165">Nel frattempo, se `AccessTheWebAsync` ha del lavoro da svolgere che non dipende dalla stringa promessa da `client.GetStringAsync`, il lavoro può continuare mentre `client.GetStringAsync` rimane in attesa.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-165">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="7a9b5-166">Nell'esempio, le righe di output seguenti, che sono contrassegnate con "THREE", rappresentano la possibilità di eseguire operazioni indipendenti</span><span class="sxs-lookup"><span data-stu-id="7a9b5-166">In the example, the following lines of output, which are labeled "THREE," represent the opportunity to do independent work</span></span>

```output
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 <span data-ttu-id="7a9b5-167">L'istruzione seguente sospende lo stato di avanzamento in `AccessTheWebAsync` quando si attende `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-167">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>

```csharp
string urlContents = await getStringTask;
```

 <span data-ttu-id="7a9b5-168">L'immagine che segue illustra il flusso di controllo da `client.GetStringAsync` all'assegnazione a `getStringTask` e dalla creazione di `getStringTask` all'applicazione di un operatore await.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-168">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an await operator.</span></span>

 <span data-ttu-id="7a9b5-169">![Fase TRE](./media/asynctrace-three.png "AsyncTrace-TreAsyncTrace-Three")</span><span class="sxs-lookup"><span data-stu-id="7a9b5-169">![Step THREE](./media/asynctrace-three.png "AsyncTrace-Three")</span></span>

 <span data-ttu-id="7a9b5-170">L'espressione await sospende `AccessTheWebAsync` finché non viene restituito `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-170">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="7a9b5-171">Nel frattempo il controllo viene restituito al chiamante di `AccessTheWebAsync`, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-171">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>

> [!NOTE]
> <span data-ttu-id="7a9b5-172">In genere, la chiamata a un metodo asincrono si attende immediatamente.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-172">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="7a9b5-173">Ad esempio, l'assegnazione seguente potrebbe sostituire il codice precedente che crea e quindi attende `getStringTask`:`string urlContents = await client.GetStringAsync("https://msdn.microsoft.com");`</span><span class="sxs-lookup"><span data-stu-id="7a9b5-173">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `string urlContents = await client.GetStringAsync("https://msdn.microsoft.com");`</span></span>
>
> <span data-ttu-id="7a9b5-174">In questo argomento l'operatore await viene applicato in un secondo tempo per contenere le righe di output che indicano il flusso di controllo attraverso il programma.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-174">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>

### <a name="step-four"></a><span data-ttu-id="7a9b5-175">Passaggio QUATTRO</span><span class="sxs-lookup"><span data-stu-id="7a9b5-175">Step FOUR</span></span>

<span data-ttu-id="7a9b5-176">Il tipo restituito dichiarato di `AccessTheWebAsync` è `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-176">The declared return type of `AccessTheWebAsync` is `Task<int>`.</span></span> <span data-ttu-id="7a9b5-177">Di conseguenza, quando `AccessTheWebAsync` è sospeso, restituisce un'attività di valori integer a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-177">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="7a9b5-178">È necessario comprendere che l'attività restituita non è `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-178">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="7a9b5-179">L'attività restituita è una nuova attività di valori integer che rappresenta ciò che resta da eseguire nel metodo sospeso, `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-179">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="7a9b5-180">L'attività è una promessa da parte di `AccessTheWebAsync` di produrre un numero intero al termine dell'attività.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-180">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>

<span data-ttu-id="7a9b5-181">L'istruzione seguente assegna questa attività alla variabile `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-181">The following statement assigns this task to the `getLengthTask` variable.</span></span>

```csharp
Task<int> getLengthTask = AccessTheWebAsync();
```

 <span data-ttu-id="7a9b5-182">Come in `AccessTheWebAsync`, `startButton_Click` può continuare a eseguire operazioni che non dipendono dai risultati dell'attività asincrona (`getLengthTask`) finché si è in attesa dell'attività.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-182">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="7a9b5-183">Le seguenti righe di output rappresentano tali operazioni.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-183">The following output lines represent that work.</span></span>

```output
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

 <span data-ttu-id="7a9b5-184">Lo stato di avanzamento in `startButton_Click` viene sospeso quando si attende `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-184">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="7a9b5-185">La seguente istruzione di assegnazione sospende `startButton_Click` finché non si completa `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-185">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>

```csharp
int contentLength = await getLengthTask;
```

 <span data-ttu-id="7a9b5-186">Nella figura seguente le frecce indicano il flusso di controllo dall'espressione await in `AccessTheWebAsync` all'assegnazione di un valore a `getLengthTask`, seguita dall'elaborazione normale in `startButton_Click` finché si è in attesa di `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-186">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>

 <span data-ttu-id="7a9b5-187">![Passo QUATTRO](./media/asynctrace-four.png "AsyncTrace-FOUR")</span><span class="sxs-lookup"><span data-stu-id="7a9b5-187">![Step FOUR](./media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>

### <a name="step-five"></a><span data-ttu-id="7a9b5-188">Passaggio CINQUE</span><span class="sxs-lookup"><span data-stu-id="7a9b5-188">Step FIVE</span></span>

<span data-ttu-id="7a9b5-189">Quando l'attività `client.GetStringAsync` segnala il proprio completamento, l'elaborazione in `AccessTheWebAsync` viene rilasciata dalla sospensione e può continuare oltre l'istruzione await.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-189">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="7a9b5-190">Le seguenti righe di output rappresentano la ripresa dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-190">The following lines of output represent the resumption of processing.</span></span>

```output
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

 <span data-ttu-id="7a9b5-191">L'operando dell'istruzione return, `urlContents.Length`, viene archiviato nell'attività restituita da `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-191">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="7a9b5-192">L'espressione await recupera tale valore da `getLengthTask` in `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-192">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>

 <span data-ttu-id="7a9b5-193">L'immagine seguente illustra il trasferimento del controllo dopo il completamento di `client.GetStringAsync` (e `getStringTask`).</span><span class="sxs-lookup"><span data-stu-id="7a9b5-193">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>

 <span data-ttu-id="7a9b5-194">![Passaggio CINQUE](./media/asynctrace-five.png "AsyncTrace-FIVE")</span><span class="sxs-lookup"><span data-stu-id="7a9b5-194">![Step FIVE](./media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>

 <span data-ttu-id="7a9b5-195">`AccessTheWebAsync` viene eseguita fino al completamento e il controllo viene restituito a `startButton_Click`, che è in attesa del completamento.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-195">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>

### <a name="step-six"></a><span data-ttu-id="7a9b5-196">Passaggio SEI</span><span class="sxs-lookup"><span data-stu-id="7a9b5-196">Step SIX</span></span>

<span data-ttu-id="7a9b5-197">Quando l'attività `AccessTheWebAsync` segnala il proprio completamento, l'elaborazione può continuare oltre l'istruzione await in `startButton_Async`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-197">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="7a9b5-198">Di fatto il programma non ha altre operazioni da eseguire.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-198">In fact, the program has nothing more to do.</span></span>

<span data-ttu-id="7a9b5-199">Le seguenti righe di output rappresentano la ripresa dell'elaborazione in `startButton_Async`:</span><span class="sxs-lookup"><span data-stu-id="7a9b5-199">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>

```output
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

 <span data-ttu-id="7a9b5-200">L'espressione await recupera da `getLengthTask` il valore integer che rappresenta l'operando dell'istruzione return in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-200">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="7a9b5-201">L'istruzione seguente assegna tale valore alla variabile `contentLength`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-201">The following statement assigns that value to the `contentLength` variable.</span></span>

```csharp
int contentLength = await getLengthTask;
```

 <span data-ttu-id="7a9b5-202">La figura seguente illustra la restituzione del controllo da `AccessTheWebAsync` a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="7a9b5-202">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>

 <span data-ttu-id="7a9b5-203">![Passaggio SEI](./media/asynctrace-six.png "AsyncTrace-SIX")</span><span class="sxs-lookup"><span data-stu-id="7a9b5-203">![Step SIX](./media/asynctrace-six.png "AsyncTrace-SIX")</span></span>

## <a name="see-also"></a><span data-ttu-id="7a9b5-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a9b5-204">See also</span></span>

- [<span data-ttu-id="7a9b5-205">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="7a9b5-205">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="7a9b5-206">Tipi restituiti async (C#)</span><span class="sxs-lookup"><span data-stu-id="7a9b5-206">Async Return Types (C#)</span></span>](./async-return-types.md)
- [<span data-ttu-id="7a9b5-207">Procedura dettagliata: accesso al Web tramite async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="7a9b5-207">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- <span data-ttu-id="7a9b5-208">[Async Sample: Control Flow in Async Programs (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) (Esempio di attività asincrona: Flusso di controllo in programmi asincroni (C# e Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="7a9b5-208">[Async Sample: Control Flow in Async Programs (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)</span></span>
