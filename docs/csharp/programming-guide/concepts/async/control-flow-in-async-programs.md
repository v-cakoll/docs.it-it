---
title: Flusso di controllo in programmi asincroni (C#)
ms.date: 07/20/2015
ms.assetid: fc92b08b-fe1d-4d07-84ab-5192fafe06bb
ms.openlocfilehash: 7367b55a665a911a4d94f7b235cdc559a69854cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336623"
---
# <a name="control-flow-in-async-programs-c"></a><span data-ttu-id="6423b-102">Flusso di controllo in programmi asincroni (C#)</span><span class="sxs-lookup"><span data-stu-id="6423b-102">Control Flow in Async Programs (C#)</span></span>
<span data-ttu-id="6423b-103">Le parole chiave `async` e `await` consentono di scrivere e gestire più facilmente i programmi asincroni.</span><span class="sxs-lookup"><span data-stu-id="6423b-103">You can write and maintain asynchronous programs more easily by using the `async` and `await` keywords.</span></span> <span data-ttu-id="6423b-104">Tuttavia, i risultati potrebbero creare perplessità se non si conosce il funzionamento del programma.</span><span class="sxs-lookup"><span data-stu-id="6423b-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="6423b-105">Questo argomento descrive il flusso di controllo attraverso un programma asincrono semplice per indicare quando il controllo si sposta da un metodo a un altro e quali informazioni vengono trasferite ogni volta.</span><span class="sxs-lookup"><span data-stu-id="6423b-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6423b-106">Le parole chiave `async` e `await` sono state introdotte in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="6423b-106">The `async` and `await` keywords were introduced in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="6423b-107">In generale, si contrassegnano i metodi che contengono codice asincrono con il modificatore [async (C#)](../../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="6423b-107">In general, you mark methods that contain asynchronous code with the [async (C#)](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="6423b-108">In un metodo contrassegnato con un modificatore async è possibile usare un operatore [await (C#)](../../../../csharp/language-reference/keywords/await.md) per specificare dove il metodo viene sospeso in attesa del completamento di un processo asincrono chiamato.</span><span class="sxs-lookup"><span data-stu-id="6423b-108">In a method that's marked with an async modifier, you can use an [await (C#)](../../../../csharp/language-reference/keywords/await.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="6423b-109">Per altre informazioni, vedere [Programmazione asincrona con async e await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="6423b-109">For more information, see [Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="6423b-110">L'esempio seguente usa i metodi asincroni per scaricare come stringa il contenuto di un sito Web specificato e per visualizzare la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="6423b-110">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="6423b-111">L'esempio contiene i due metodi seguenti.</span><span class="sxs-lookup"><span data-stu-id="6423b-111">The example contains the following two methods.</span></span>  
  
-   <span data-ttu-id="6423b-112">`startButton_Click`, che chiama `AccessTheWebAsync` e visualizza il risultato.</span><span class="sxs-lookup"><span data-stu-id="6423b-112">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>  
  
-   <span data-ttu-id="6423b-113">`AccessTheWebAsync`, che scarica il contenuto di un sito Web come stringa e restituisce la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="6423b-113">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="6423b-114">`AccessTheWebAsync` usa un metodo <xref:System.Net.Http.HttpClient> asincrono, ovvero <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, per scaricare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="6423b-114">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>  
  
 <span data-ttu-id="6423b-115">In corrispondenza dei punti strategici del programma sono visualizzate righe numerate che consentono di comprendere come viene eseguito il programma e spiegano che cosa accade in ogni punto contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="6423b-115">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="6423b-116">Le righe sono evidenziate con etichette numerate da "ONE" a "SIX."</span><span class="sxs-lookup"><span data-stu-id="6423b-116">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="6423b-117">Le etichette rappresentano l'ordine in cui il programma raggiunge queste righe di codice.</span><span class="sxs-lookup"><span data-stu-id="6423b-117">The labels represent the order in which the program reaches these lines of code.</span></span>  
  
 <span data-ttu-id="6423b-118">Il codice seguente rappresenta una struttura del programma.</span><span class="sxs-lookup"><span data-stu-id="6423b-118">The following code shows an outline of the program.</span></span>  
  
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
            String.Format("\r\nLength of the downloaded string: {0}.\r\n", contentLength);  
    }  
  
    async Task<int> AccessTheWebAsync()  
    {  
        // TWO  
        HttpClient client = new HttpClient();  
        Task<string> getStringTask =  
            client.GetStringAsync("http://msdn.microsoft.com");  
  
        // THREE                   
        string urlContents = await getStringTask;  
  
        // FIVE  
        return urlContents.Length;  
    }  
}  
```  
  
 <span data-ttu-id="6423b-119">Ognuna delle posizioni con etichetta da "ONE" a "SIX" visualizza informazioni sullo stato corrente del programma.</span><span class="sxs-lookup"><span data-stu-id="6423b-119">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="6423b-120">Viene visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="6423b-120">The following output is produced.</span></span>  
  
```  
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
  
## <a name="set-up-the-program"></a><span data-ttu-id="6423b-121">Impostare il programma</span><span class="sxs-lookup"><span data-stu-id="6423b-121">Set Up the Program</span></span>  
 <span data-ttu-id="6423b-122">È possibile scaricare il codice usato in questo argomento da MSDN oppure crearlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="6423b-122">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6423b-123">Per eseguire l'esempio, è necessario che Visual Studio 2012 o versione successiva e .NET Framework 4.5 o versione successiva siano installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6423b-123">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
### <a name="download-the-program"></a><span data-ttu-id="6423b-124">Scaricare il programma</span><span class="sxs-lookup"><span data-stu-id="6423b-124">Download the Program</span></span>  
 <span data-ttu-id="6423b-125">È possibile scaricare l'applicazione di questo argomento da [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) (Esempio di attività asincrona: flusso di controllo in programmi asincroni).</span><span class="sxs-lookup"><span data-stu-id="6423b-125">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span></span> <span data-ttu-id="6423b-126">I passaggi seguenti consentono di aprire ed eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="6423b-126">The following steps open and run the program.</span></span>  
  
1.  <span data-ttu-id="6423b-127">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6423b-127">Unzip the downloaded file, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="6423b-128">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="6423b-128">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="6423b-129">Passare alla cartella che contiene il codice di esempio decompresso, aprire il file della soluzione (SLN) e quindi scegliere il tasto F5 per compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="6423b-129">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the F5 key to build and run the project.</span></span>  
  
### <a name="build-the-program-yourself"></a><span data-ttu-id="6423b-130">Compilare il programma autonomamente</span><span class="sxs-lookup"><span data-stu-id="6423b-130">Build the Program Yourself</span></span>  
 <span data-ttu-id="6423b-131">Il seguente progetto Windows Presentation Foundation (WPF) contiene gli esempi di codice per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6423b-131">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>  
  
 <span data-ttu-id="6423b-132">Per eseguire il progetto, effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6423b-132">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="6423b-133">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6423b-133">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="6423b-134">Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="6423b-134">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="6423b-135">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="6423b-135">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="6423b-136">Nel riquadro **Modelli installati** scegliere **Visual C#** e quindi **Applicazione WPF** nell'elenco dei tipi di progetto.</span><span class="sxs-lookup"><span data-stu-id="6423b-136">In the **Installed Templates** pane, choose **Visual C#**, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="6423b-137">Immettere `AsyncTracer` come nome del progetto, quindi scegliere il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="6423b-137">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="6423b-138">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="6423b-138">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="6423b-139">Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="6423b-139">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="6423b-140">Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow.xaml in **Esplora soluzioni** e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="6423b-140">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="6423b-141">Nella visualizzazione **XAML** di MainWindow.xaml sostituire il codice con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6423b-141">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
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
  
     <span data-ttu-id="6423b-142">Nella visualizzazione **Progettazione** di MainWindow.xaml viene visualizzata una finestra semplice contenente una casella di testo e un pulsante.</span><span class="sxs-lookup"><span data-stu-id="6423b-142">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="6423b-143">Aggiunge un riferimento a <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="6423b-143">Add a reference for <xref:System.Net.Http>.</span></span>  
  
8.  <span data-ttu-id="6423b-144">In **Esplora soluzioni** aprire il menu di scelta rapida per MainWindow.xaml.cs e quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="6423b-144">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>  
  
9. <span data-ttu-id="6423b-145">Sostituire il codice in MainWindow.xaml.cs con quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6423b-145">In MainWindow.xaml.cs, replace the code with the following code.</span></span>  
  
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
                    String.Format("\r\nLength of the downloaded string: {0}.\r\n", contentLength);  
            }  
  
            async Task<int> AccessTheWebAsync()  
            {  
                resultsTextBox.Text += "\r\nTWO:   Entering AccessTheWebAsync.";  
  
                // Declare an HttpClient object.  
                HttpClient client = new HttpClient();  
  
                resultsTextBox.Text += "\r\n           Calling HttpClient.GetStringAsync.\r\n";  
  
                // GetStringAsync returns a Task<string>.   
                Task<string> getStringTask = client.GetStringAsync("http://msdn.microsoft.com");  
  
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
  
10. <span data-ttu-id="6423b-146">Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .</span><span class="sxs-lookup"><span data-stu-id="6423b-146">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="6423b-147">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="6423b-147">The following output should appear.</span></span>  
  
    ```  
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
  
## <a name="trace-the-program"></a><span data-ttu-id="6423b-148">Analizzare il programma</span><span class="sxs-lookup"><span data-stu-id="6423b-148">Trace the Program</span></span>  
  
### <a name="steps-one-and-two"></a><span data-ttu-id="6423b-149">Passaggi UNO e DUE</span><span class="sxs-lookup"><span data-stu-id="6423b-149">Steps ONE and TWO</span></span>  
 <span data-ttu-id="6423b-150">Le prime due righe di visualizzazione tracciano il percorso poiché `startButton_Click` chiama `AccessTheWebAsync` e `AccessTheWebAsync` chiama il metodo asincrono <xref:System.Net.Http.HttpClient>, ovvero <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="6423b-150">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="6423b-151">Nell'immagine seguente vengono illustrate le chiamate metodo a metodo.</span><span class="sxs-lookup"><span data-stu-id="6423b-151">The following image outlines the calls from method to method.</span></span>  
  
 <span data-ttu-id="6423b-152">![Passaggi UNO e DUE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span><span class="sxs-lookup"><span data-stu-id="6423b-152">![Steps ONE and TWO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>  
  
 <span data-ttu-id="6423b-153">Il tipo restituito di `AccessTheWebAsync` e `client.GetStringAsync` è <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="6423b-153">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="6423b-154">Per `AccessTheWebAsync` TResult è un numero intero.</span><span class="sxs-lookup"><span data-stu-id="6423b-154">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="6423b-155">Per `GetStringAsync` TResult è una stringa.</span><span class="sxs-lookup"><span data-stu-id="6423b-155">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="6423b-156">Per altre informazioni sui tipi restituiti dei metodi asincroni, vedere [Tipi restituiti asincroni (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="6423b-156">For more information about async method return types, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
 <span data-ttu-id="6423b-157">Un metodo asincrono che restituisce un'attività restituisce un'istanza dell'attività quando il controllo torna al chiamante.</span><span class="sxs-lookup"><span data-stu-id="6423b-157">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="6423b-158">Il controllo viene restituito da un metodo asincrono al relativo chiamante quando viene rilevato un operatore `await` nel metodo chiamato o quando termina il metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="6423b-158">Control returns from an async method to its caller either when an `await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="6423b-159">Le righe evidenziate con le etichette da "THREE" a "SIX" analizzano questa parte del processo.</span><span class="sxs-lookup"><span data-stu-id="6423b-159">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>  
  
### <a name="step-three"></a><span data-ttu-id="6423b-160">Passaggio TRE</span><span class="sxs-lookup"><span data-stu-id="6423b-160">Step THREE</span></span>  
 <span data-ttu-id="6423b-161">In `AccessTheWebAsync`, il metodo asincrono <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> viene chiamato per scaricare il contenuto della pagina Web di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6423b-161">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="6423b-162">Il controllo viene restituito da `client.GetStringAsync` a `AccessTheWebAsync` quando viene restituito `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="6423b-162">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>  
  
 <span data-ttu-id="6423b-163">Il metodo `client.GetStringAsync` restituisce un'attività di stringa che viene assegnata alla variabile `getStringTask` in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="6423b-163">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="6423b-164">La riga seguente nel programma di esempio indica la chiamata a `client.GetStringAsync` e l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="6423b-164">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>  
  
```csharp  
Task<string> getStringTask = client.GetStringAsync("http://msdn.microsoft.com");  
```  
  
 <span data-ttu-id="6423b-165">Si può pensare all'attività come a una promessa fatta da `client.GetStringAsync` di produrre una stringa reale alla fine.</span><span class="sxs-lookup"><span data-stu-id="6423b-165">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="6423b-166">Nel frattempo, se `AccessTheWebAsync` ha del lavoro da svolgere che non dipende dalla stringa promessa da `client.GetStringAsync`, il lavoro può continuare mentre `client.GetStringAsync` rimane in attesa.</span><span class="sxs-lookup"><span data-stu-id="6423b-166">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="6423b-167">Nell'esempio, le righe di output seguenti, che sono contrassegnate con "THREE", rappresentano la possibilità di eseguire operazioni indipendenti</span><span class="sxs-lookup"><span data-stu-id="6423b-167">In the example, the following lines of output, which are labeled "THREE," represent the opportunity to do independent work</span></span>  
  
```  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
```  
  
 <span data-ttu-id="6423b-168">L'istruzione seguente sospende lo stato di avanzamento in `AccessTheWebAsync` quando si attende `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="6423b-168">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>  
  
```csharp  
string urlContents = await getStringTask;  
```  
  
 <span data-ttu-id="6423b-169">L'immagine che segue illustra il flusso di controllo da `client.GetStringAsync` all'assegnazione a `getStringTask` e dalla creazione di `getStringTask` all'applicazione di un operatore await.</span><span class="sxs-lookup"><span data-stu-id="6423b-169">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an await operator.</span></span>  
  
 <span data-ttu-id="6423b-170">![Passaggio TRE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace tre")</span><span class="sxs-lookup"><span data-stu-id="6423b-170">![Step THREE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span></span>  
  
 <span data-ttu-id="6423b-171">L'espressione await sospende `AccessTheWebAsync` finché non viene restituito `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="6423b-171">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="6423b-172">Nel frattempo il controllo viene restituito al chiamante di `AccessTheWebAsync`, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="6423b-172">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6423b-173">In genere, la chiamata a un metodo asincrono si attende immediatamente.</span><span class="sxs-lookup"><span data-stu-id="6423b-173">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="6423b-174">Ad esempio, l'assegnazione seguente potrebbe sostituire il codice precedente che crea e quindi attende `getStringTask`:`string urlContents = await client.GetStringAsync("http://msdn.microsoft.com");`</span><span class="sxs-lookup"><span data-stu-id="6423b-174">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `string urlContents = await client.GetStringAsync("http://msdn.microsoft.com");`</span></span>  
>   
>  <span data-ttu-id="6423b-175">In questo argomento l'operatore await viene applicato in un secondo tempo per contenere le righe di output che indicano il flusso di controllo attraverso il programma.</span><span class="sxs-lookup"><span data-stu-id="6423b-175">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>  
  
### <a name="step-four"></a><span data-ttu-id="6423b-176">Passaggio QUATTRO</span><span class="sxs-lookup"><span data-stu-id="6423b-176">Step FOUR</span></span>  
 <span data-ttu-id="6423b-177">Il tipo restituito dichiarato di `AccessTheWebAsync` è `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="6423b-177">The declared return type of `AccessTheWebAsync` is `Task<int>`.</span></span> <span data-ttu-id="6423b-178">Di conseguenza, quando `AccessTheWebAsync` è sospeso, restituisce un'attività di valori integer a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="6423b-178">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="6423b-179">È necessario comprendere che l'attività restituita non è `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="6423b-179">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="6423b-180">L'attività restituita è una nuova attività di valori integer che rappresenta ciò che resta da eseguire nel metodo sospeso, `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="6423b-180">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="6423b-181">L'attività è una promessa da parte di `AccessTheWebAsync` di produrre un numero intero al termine dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6423b-181">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>  
  
 <span data-ttu-id="6423b-182">L'istruzione seguente assegna questa attività alla variabile `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="6423b-182">The following statement assigns this task to the `getLengthTask` variable.</span></span>  
  
```csharp  
Task<int> getLengthTask = AccessTheWebAsync();  
```  
  
 <span data-ttu-id="6423b-183">Come in `AccessTheWebAsync`, `startButton_Click` può continuare a eseguire operazioni che non dipendono dai risultati dell'attività asincrona (`getLengthTask`) finché si è in attesa dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6423b-183">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="6423b-184">Le seguenti righe di output rappresentano tali operazioni.</span><span class="sxs-lookup"><span data-stu-id="6423b-184">The following output lines represent that work.</span></span>  
  
```  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
```  
  
 <span data-ttu-id="6423b-185">Lo stato di avanzamento in `startButton_Click` viene sospeso quando si attende `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="6423b-185">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="6423b-186">La seguente istruzione di assegnazione sospende `startButton_Click` finché non si completa `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="6423b-186">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>  
  
```csharp  
int contentLength = await getLengthTask;  
```  
  
 <span data-ttu-id="6423b-187">Nella figura seguente le frecce indicano il flusso di controllo dall'espressione await in `AccessTheWebAsync` all'assegnazione di un valore a `getLengthTask`, seguita dall'elaborazione normale in `startButton_Click` finché si è in attesa di `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="6423b-187">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>  
  
 <span data-ttu-id="6423b-188">![Passaggio QUATTRO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span><span class="sxs-lookup"><span data-stu-id="6423b-188">![Step FOUR](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>  
  
### <a name="step-five"></a><span data-ttu-id="6423b-189">Passaggio CINQUE</span><span class="sxs-lookup"><span data-stu-id="6423b-189">Step FIVE</span></span>  
 <span data-ttu-id="6423b-190">Quando l'attività `client.GetStringAsync` segnala il proprio completamento, l'elaborazione in `AccessTheWebAsync` viene rilasciata dalla sospensione e può continuare oltre l'istruzione await.</span><span class="sxs-lookup"><span data-stu-id="6423b-190">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="6423b-191">Le seguenti righe di output rappresentano la ripresa dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="6423b-191">The following lines of output represent the resumption of processing.</span></span>  
  
```  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
```  
  
 <span data-ttu-id="6423b-192">L'operando dell'istruzione return, `urlContents.Length`, viene archiviato nell'attività restituita da `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="6423b-192">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="6423b-193">L'espressione await recupera tale valore da `getLengthTask` in `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="6423b-193">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>  
  
 <span data-ttu-id="6423b-194">L'immagine seguente illustra il trasferimento del controllo dopo il completamento di `client.GetStringAsync` (e `getStringTask`).</span><span class="sxs-lookup"><span data-stu-id="6423b-194">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>  
  
 <span data-ttu-id="6423b-195">![Passaggio CINQUE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span><span class="sxs-lookup"><span data-stu-id="6423b-195">![Step FIVE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>  
  
 <span data-ttu-id="6423b-196">`AccessTheWebAsync` viene eseguita fino al completamento e il controllo viene restituito a `startButton_Click`, che è in attesa del completamento.</span><span class="sxs-lookup"><span data-stu-id="6423b-196">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>  
  
### <a name="step-six"></a><span data-ttu-id="6423b-197">Passaggio SEI</span><span class="sxs-lookup"><span data-stu-id="6423b-197">Step SIX</span></span>  
 <span data-ttu-id="6423b-198">Quando l'attività `AccessTheWebAsync` segnala il proprio completamento, l'elaborazione può continuare oltre l'istruzione await in `startButton_Async`.</span><span class="sxs-lookup"><span data-stu-id="6423b-198">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="6423b-199">Di fatto il programma non ha altre operazioni da eseguire.</span><span class="sxs-lookup"><span data-stu-id="6423b-199">In fact, the program has nothing more to do.</span></span>  
  
 <span data-ttu-id="6423b-200">Le seguenti righe di output rappresentano la ripresa dell'elaborazione in `startButton_Async`:</span><span class="sxs-lookup"><span data-stu-id="6423b-200">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>  
  
```  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
```  
  
 <span data-ttu-id="6423b-201">L'espressione await recupera da `getLengthTask` il valore integer che rappresenta l'operando dell'istruzione return in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="6423b-201">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="6423b-202">L'istruzione seguente assegna tale valore alla variabile `contentLength`.</span><span class="sxs-lookup"><span data-stu-id="6423b-202">The following statement assigns that value to the `contentLength` variable.</span></span>  
  
```csharp  
int contentLength = await getLengthTask;  
```  
  
 <span data-ttu-id="6423b-203">La figura seguente illustra la restituzione del controllo da `AccessTheWebAsync` a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="6423b-203">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>  
  
 <span data-ttu-id="6423b-204">![Passaggio SEI](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span><span class="sxs-lookup"><span data-stu-id="6423b-204">![Step SIX](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6423b-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6423b-205">See Also</span></span>  
 [<span data-ttu-id="6423b-206">Programmazione asincrona con Async e Await (C#)</span><span class="sxs-lookup"><span data-stu-id="6423b-206">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="6423b-207">Tipi restituiti asincroni (C#)</span><span class="sxs-lookup"><span data-stu-id="6423b-207">Async Return Types (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/async-return-types.md)  
 [<span data-ttu-id="6423b-208">Procedura dettagliata: Accesso al Web con Async e Await (C#)</span><span class="sxs-lookup"><span data-stu-id="6423b-208">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 <span data-ttu-id="6423b-209">[Async Sample: Control Flow in Async Programs (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) (Esempio di attività asincrona: Flusso di controllo in programmi asincroni (C# e Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="6423b-209">[Async Sample: Control Flow in Async Programs (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)</span></span>
