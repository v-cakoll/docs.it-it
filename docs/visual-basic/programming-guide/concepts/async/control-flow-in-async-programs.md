---
title: Controllare il flusso in programmi asincroni (Visual Basic) | Documenti di Microsoft
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
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 15e02fbc023db9ae2f3ee9f40598faa7c9c027a0
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="control-flow-in-async-programs-visual-basic"></a><span data-ttu-id="68565-102">Flusso di controllo in programmi asincroni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68565-102">Control Flow in Async Programs (Visual Basic)</span></span>
<span data-ttu-id="68565-103">È possibile scrivere e gestire più facilmente programmi asincroni utilizzando il `Async` e `Await` le parole chiave.</span><span class="sxs-lookup"><span data-stu-id="68565-103">You can write and maintain asynchronous programs more easily by using the `Async` and `Await` keywords.</span></span> <span data-ttu-id="68565-104">Tuttavia, i risultati potrebbero sorprendere di comprendere il funzionamento del programma.</span><span class="sxs-lookup"><span data-stu-id="68565-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="68565-105">Tracce in questo argomento il flusso di controllo tramite un programma asincrono semplice visualizzare quando il controllo si sposta da un metodo a un altro e quali informazioni verrà trasferito ogni volta.</span><span class="sxs-lookup"><span data-stu-id="68565-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68565-106">Le parole chiave `Async` e `Await` sono state introdotte in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="68565-106">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="68565-107">In generale, contrassegnare i metodi che contengono codice asincrono con il [Async](../../../../visual-basic/language-reference/modifiers/async.md) modificatore.</span><span class="sxs-lookup"><span data-stu-id="68565-107">In general, you mark methods that contain asynchronous code with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="68565-108">In un metodo contrassegnato con un modificatore async, è possibile utilizzare un [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) per specificare un in cui il metodo viene sospesa in attesa di un processo asincrono chiamato al completamento.</span><span class="sxs-lookup"><span data-stu-id="68565-108">In a method that's marked with an async modifier, you can use an [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="68565-109">Per ulteriori informazioni, vedere [la programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="68565-109">For more information, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="68565-110">L'esempio seguente usa i metodi asincroni per scaricare il contenuto di un sito Web specificato come stringa e visualizzare la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="68565-110">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="68565-111">L'esempio contiene due metodi seguenti.</span><span class="sxs-lookup"><span data-stu-id="68565-111">The example contains the following two methods.</span></span>  
  
-   <span data-ttu-id="68565-112">`startButton_Click`, che chiama `AccessTheWebAsync` e visualizza il risultato.</span><span class="sxs-lookup"><span data-stu-id="68565-112">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>  
  
-   <span data-ttu-id="68565-113">`AccessTheWebAsync`, che scarica il contenuto di un sito Web sotto forma di stringa e restituisce la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="68565-113">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="68565-114">`AccessTheWebAsync`utilizza asincrono <xref:System.Net.Http.HttpClient>metodo <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, per scaricare il contenuto.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="68565-114">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>  
  
 <span data-ttu-id="68565-115">Numerate Visualizza le righe vengono visualizzate in punti strategici in tutto il programma per comprendere come viene eseguito il programma e viene descritto cosa accade in ogni punto contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="68565-115">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="68565-116">Visualizza linee sono contrassegnate con "Uno"e "sei."</span><span class="sxs-lookup"><span data-stu-id="68565-116">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="68565-117">Le etichette di rappresentano l'ordine in cui il programma raggiunge le righe di codice.</span><span class="sxs-lookup"><span data-stu-id="68565-117">The labels represent the order in which the program reaches these lines of code.</span></span>  
  
 <span data-ttu-id="68565-118">Il codice seguente illustra una struttura del programma.</span><span class="sxs-lookup"><span data-stu-id="68565-118">The following code shows an outline of the program.</span></span>  
  
```vb  
Class MainWindow  
  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
        ' ONE  
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
        ' FOUR  
        Dim contentLength As Integer = Await getLengthTask  
  
        ' SIX  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
    End Sub  
  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' TWO  
        Dim client As HttpClient = New HttpClient()   
        Dim getStringTask As Task(Of String) =   
            client.GetStringAsync("http://msdn.microsoft.com")  
  
        ' THREE  
        Dim urlContents As String = Await getStringTask  
  
        ' FIVE  
        Return urlContents.Length  
    End Function  
  
End Class  
  
```  
  
 <span data-ttu-id="68565-119">Ognuna delle posizioni di etichetta, "Uno"e "6", vengono visualizzate informazioni sullo stato corrente del programma.</span><span class="sxs-lookup"><span data-stu-id="68565-119">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="68565-120">Viene prodotto l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="68565-120">The following output is produced.</span></span>  
  
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
  
## <a name="set-up-the-program"></a><span data-ttu-id="68565-121">Impostare il programma</span><span class="sxs-lookup"><span data-stu-id="68565-121">Set Up the Program</span></span>  
 <span data-ttu-id="68565-122">È possibile scaricare il codice utilizzato in questo argomento da MSDN o è possibile generarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="68565-122">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68565-123">Per eseguire l'esempio, è necessario disporre di Visual Studio 2012 o versione successiva e .NET Framework 4.5 o versioni successive installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="68565-123">To run the example, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
### <a name="download-the-program"></a><span data-ttu-id="68565-124">Scaricare il programma</span><span class="sxs-lookup"><span data-stu-id="68565-124">Download the Program</span></span>  
 <span data-ttu-id="68565-125">È possibile scaricare l'applicazione di questo argomento da [esempio asincrono: flusso di controllo in programmi asincroni](http://go.microsoft.com/fwlink/?LinkId=255285).</span><span class="sxs-lookup"><span data-stu-id="68565-125">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](http://go.microsoft.com/fwlink/?LinkId=255285).</span></span> <span data-ttu-id="68565-126">I passaggi seguenti aprono ed eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="68565-126">The following steps open and run the program.</span></span>  
  
1.  <span data-ttu-id="68565-127">Decomprimere il file scaricato e quindi avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="68565-127">Unzip the downloaded file, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="68565-128">Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="68565-128">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="68565-129">Passare alla cartella che contiene il codice di esempio non compressi, aprire il file di soluzione (sln) e quindi premere il tasto F5 per compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="68565-129">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the F5 key to build and run the project.</span></span>  
  
### <a name="build-the-program-yourself"></a><span data-ttu-id="68565-130">Compilare il programma autonomamente</span><span class="sxs-lookup"><span data-stu-id="68565-130">Build the Program Yourself</span></span>  
 <span data-ttu-id="68565-131">Il progetto Windows Presentation Foundation (WPF) seguente contiene l'esempio di codice per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="68565-131">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>  
  
 <span data-ttu-id="68565-132">Per eseguire il progetto, effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="68565-132">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="68565-133">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="68565-133">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="68565-134">Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="68565-134">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="68565-135">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="68565-135">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="68565-136">Nel **modelli installati** riquadro, scegliere **Visual Basic**, quindi scegliere **applicazione WPF** dall'elenco dei tipi di progetto.</span><span class="sxs-lookup"><span data-stu-id="68565-136">In the **Installed Templates** pane, choose **Visual Basic**, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="68565-137">Immettere `AsyncTracer` come nome del progetto, quindi scegliere il **OK** pulsante.</span><span class="sxs-lookup"><span data-stu-id="68565-137">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="68565-138">Il nuovo progetto verrà visualizzato **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="68565-138">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="68565-139">Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="68565-139">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="68565-140">Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow. XAML in **Esplora**, quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="68565-140">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="68565-141">Nel **XAML** visualizzazione di MainWindow. XAML, sostituire il codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="68565-141">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"  
        Title="Control Flow Trace" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     <span data-ttu-id="68565-142">Viene visualizzata una finestra semplice che contiene una casella di testo e un pulsante nel **progettazione** visualizzazione di MainWindow. Xaml.</span><span class="sxs-lookup"><span data-stu-id="68565-142">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="68565-143">Aggiungere un riferimento per <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="68565-143">Add a reference for <xref:System.Net.Http>.</span></span>  
  
8.  <span data-ttu-id="68565-144">In **Esplora**, aprire il menu di scelta rapida per MainWindow.xaml.vb e quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="68565-144">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
9. <span data-ttu-id="68565-145">Nel file MainWindow.xaml.vb, sostituire il codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="68565-145">In MainWindow.xaml.vb , replace the code with the following code.</span></span>  
  
    ```vb  
    ' Add an Imports statement and a reference for System.Net.Http.  
    Imports System.Net.Http  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
            ' The display lines in the example lead you through the control shifts.  
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &  
                "           Calling AccessTheWebAsync." & vbCrLf  
  
            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is started." & vbCrLf &  
                "           About to await getLengthTask -- no caller to return to." & vbCrLf  
  
            Dim contentLength As Integer = Await getLengthTask  
  
            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is finished." & vbCrLf &  
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &  
                "           About to display contentLength and exit." & vbCrLf  
  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
        End Sub  
  
        Async Function AccessTheWebAsync() As Task(Of Integer)  
  
            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."  
  
            ' Declare an HttpClient object.  
            Dim client As HttpClient = New HttpClient()  
  
            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf  
  
            ' GetStringAsync returns a Task(Of String).   
            Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
  
            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &  
                "           Task getStringTask is started."  
  
            ' AccessTheWebAsync can continue to work until getStringTask is awaited.  
  
            ResultsTextBox.Text &=  
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf  
  
            ' Retrieve the website contents when task is complete.  
            Dim urlContents As String = Await getStringTask  
  
            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &  
                vbCrLf & "           Task getStringTask is complete." &  
                vbCrLf & "           Processing the return statement." &  
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf  
  
            Return urlContents.Length  
        End Function  
  
    End Class  
    ```  
  
10. <span data-ttu-id="68565-146">Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .</span><span class="sxs-lookup"><span data-stu-id="68565-146">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="68565-147">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="68565-147">The following output should appear.</span></span>  
  
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
  
## <a name="trace-the-program"></a><span data-ttu-id="68565-148">Il programma di analisi</span><span class="sxs-lookup"><span data-stu-id="68565-148">Trace the Program</span></span>  
  
### <a name="steps-one-and-two"></a><span data-ttu-id="68565-149">Passaggi UNO e DUE</span><span class="sxs-lookup"><span data-stu-id="68565-149">Steps ONE and TWO</span></span>  
 <span data-ttu-id="68565-150">Visualizza prime due righe di traccia il percorso come `startButton_Click` chiamate `AccessTheWebAsync`, e `AccessTheWebAsync` chiama il <xref:System.Net.Http.HttpClient>metodo <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient> asincrono</span><span class="sxs-lookup"><span data-stu-id="68565-150">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="68565-151">Nell'immagine seguente vengono illustrate le chiamate da un metodo a.</span><span class="sxs-lookup"><span data-stu-id="68565-151">The following image outlines the calls from method to method.</span></span>  
  
 <span data-ttu-id="68565-152">![Passaggi uno e due](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace ONETWO")</span><span class="sxs-lookup"><span data-stu-id="68565-152">![Steps ONE and TWO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>  
  
 <span data-ttu-id="68565-153">Il tipo restituito di `AccessTheWebAsync` e `client.GetStringAsync` è <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="68565-153">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="68565-154">Per `AccessTheWebAsync`, TResult è un numero intero.</span><span class="sxs-lookup"><span data-stu-id="68565-154">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="68565-155">Per `GetStringAsync`, TResult è una stringa.</span><span class="sxs-lookup"><span data-stu-id="68565-155">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="68565-156">Per ulteriori informazioni sui tipi restituiti di metodi asincroni, vedere [Async restituire tipi (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="68565-156">For more information about async method return types, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
 <span data-ttu-id="68565-157">Un metodo asincrono che restituisce task restituisce un'istanza dell'attività quando il controllo passa al chiamante.</span><span class="sxs-lookup"><span data-stu-id="68565-157">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="68565-158">Controllo viene restituito da un metodo asincrono al chiamante quando un `Await` operatore viene rilevata nel metodo chiamato o quando termina il metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="68565-158">Control returns from an async method to its caller either when an `Await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="68565-159">Visualizza linee che sono contrassegnate con "Tre"e "sei" tracciano questa parte del processo.</span><span class="sxs-lookup"><span data-stu-id="68565-159">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>  
  
### <a name="step-three"></a><span data-ttu-id="68565-160">Passaggio TRE</span><span class="sxs-lookup"><span data-stu-id="68565-160">Step THREE</span></span>  
 <span data-ttu-id="68565-161">In `AccessTheWebAsync`, il metodo asincrono <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>viene chiamato per scaricare il contenuto della pagina Web di destinazione.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="68565-161">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="68565-162">Controllo viene restituito da `client.GetStringAsync` a `AccessTheWebAsync` quando `client.GetStringAsync` restituisce.</span><span class="sxs-lookup"><span data-stu-id="68565-162">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>  
  
 <span data-ttu-id="68565-163">Il `client.GetStringAsync` un'attività di stringa che viene assegnato a un metodo di `getStringTask` variabile in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="68565-163">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="68565-164">La riga seguente nel programma di esempio illustra la chiamata a `client.GetStringAsync` e l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="68565-164">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>  
  
<span data-ttu-id="68565-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="68565-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="68565-166">Può essere considerato dell'attività come una promessa da `client.GetStringAsync` per produrre una stringa effettiva alla fine.</span><span class="sxs-lookup"><span data-stu-id="68565-166">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="68565-167">Nel frattempo, se `AccessTheWebAsync` dispone di lavoro che non dipende dalla stringa promessa di `client.GetStringAsync`, che possibile continuare a lavorare mentre `client.GetStringAsync` rimane in attesa.</span><span class="sxs-lookup"><span data-stu-id="68565-167">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="68565-168">Nell'esempio, le seguenti righe di output, che sono contrassegnate con "Tre", rappresentano la possibilità di eseguire operazioni indipendenti</span><span class="sxs-lookup"><span data-stu-id="68565-168">In the example, the following lines of output, which are labeled "THREE,” represent the opportunity to do independent work</span></span>  
  
<span data-ttu-id="68565-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="68565-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="68565-170">L'istruzione seguente consente di sospendere lo stato di avanzamento in `AccessTheWebAsync` quando `getStringTask` è atteso.</span><span class="sxs-lookup"><span data-stu-id="68565-170">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>  
  
<span data-ttu-id="68565-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="68565-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="68565-172">Di seguito viene illustrato il flusso di controllo da `client.GetStringAsync` per l'assegnazione al `getStringTask` e dalla creazione di `getStringTask` all'applicazione di un operatore Await.</span><span class="sxs-lookup"><span data-stu-id="68565-172">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an Await operator.</span></span>  
  
 <span data-ttu-id="68565-173">![Passaggio tre](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace tre")</span><span class="sxs-lookup"><span data-stu-id="68565-173">![Step THREE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span></span>  
  
 <span data-ttu-id="68565-174">L'espressione await sospende `AccessTheWebAsync` fino a quando non `client.GetStringAsync` restituisce.</span><span class="sxs-lookup"><span data-stu-id="68565-174">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="68565-175">Nel frattempo il controllo viene restituito al chiamante di `AccessTheWebAsync`, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="68565-175">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68565-176">In genere, si attende immediatamente la chiamata a un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="68565-176">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="68565-177">Ad esempio, l'assegnazione seguente Impossibile sostituire il codice precedente che crea e quindi attende `getStringTask`:`Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span><span class="sxs-lookup"><span data-stu-id="68565-177">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span></span>  
>   
>  <span data-ttu-id="68565-178">In questo argomento, l'operatore await viene applicato in un secondo momento per contenere le righe di output che indicano il flusso di controllo tramite il programma.</span><span class="sxs-lookup"><span data-stu-id="68565-178">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>  
  
### <a name="step-four"></a><span data-ttu-id="68565-179">Passaggio QUATTRO</span><span class="sxs-lookup"><span data-stu-id="68565-179">Step FOUR</span></span>  
 <span data-ttu-id="68565-180">Dichiarato il tipo restituito di `AccessTheWebAsync` è `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="68565-180">The declared return type of `AccessTheWebAsync` is `Task(Of Integer)`.</span></span> <span data-ttu-id="68565-181">Pertanto, quando `AccessTheWebAsync` è sospeso, restituisce un'attività di intero a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="68565-181">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="68565-182">È necessario comprendere che l'attività restituita non è `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="68565-182">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="68565-183">L'attività restituita è una nuova attività di integer che rappresenta ciò che resta da eseguire nel metodo sospeso, `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="68565-183">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="68565-184">L'attività è una promessa da `AccessTheWebAsync` per produrre un numero intero quando l'attività è completata.</span><span class="sxs-lookup"><span data-stu-id="68565-184">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>  
  
 <span data-ttu-id="68565-185">L'istruzione seguente assegna questa attività per il `getLengthTask` variabile.</span><span class="sxs-lookup"><span data-stu-id="68565-185">The following statement assigns this task to the `getLengthTask` variable.</span></span>  
  
<span data-ttu-id="68565-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="68565-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="68565-187">Come in `AccessTheWebAsync`, `startButton_Click` possibile continuare con un lavoro che non dipenda dai risultati dell'attività asincrona (`getLengthTask`) fino a quando l'attività è atteso.</span><span class="sxs-lookup"><span data-stu-id="68565-187">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="68565-188">Le seguenti righe di output rappresentano il lavoro.</span><span class="sxs-lookup"><span data-stu-id="68565-188">The following output lines represent that work.</span></span>  
  
<span data-ttu-id="68565-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="68565-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="68565-190">Stato di avanzamento `startButton_Click` viene sospesa quando `getLengthTask` è atteso.</span><span class="sxs-lookup"><span data-stu-id="68565-190">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="68565-191">Sospende la seguente istruzione di assegnazione `startButton_Click` fino a quando non `AccessTheWebAsync` è stata completata.</span><span class="sxs-lookup"><span data-stu-id="68565-191">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>  
  
<span data-ttu-id="68565-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="68565-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="68565-193">Nella figura seguente, le frecce indicano il flusso di controllo dall'espressione await in `AccessTheWebAsync` per l'assegnazione di un valore a `getLengthTask`, seguito dall'elaborazione normale in `startButton_Click` fino a quando non `getLengthTask` è atteso.</span><span class="sxs-lookup"><span data-stu-id="68565-193">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>  
  
 <span data-ttu-id="68565-194">![Passaggio quattro](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace quattro")</span><span class="sxs-lookup"><span data-stu-id="68565-194">![Step FOUR](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>  
  
### <a name="step-five"></a><span data-ttu-id="68565-195">Passaggio CINQUE</span><span class="sxs-lookup"><span data-stu-id="68565-195">Step FIVE</span></span>  
 <span data-ttu-id="68565-196">Quando `client.GetStringAsync` segnala che è completo, l'elaborazione `AccessTheWebAsync` viene rilasciato dalla sospensione e può continuare oltre l'istruzione await.</span><span class="sxs-lookup"><span data-stu-id="68565-196">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="68565-197">Le seguenti righe di output rappresentano la ripresa dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="68565-197">The following lines of output represent the resumption of processing.</span></span>  
  
<span data-ttu-id="68565-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="68565-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="68565-199">L'operando dell'istruzione return, `urlContents.Length`, viene archiviato nell'attività che `AccessTheWebAsync` restituisce.</span><span class="sxs-lookup"><span data-stu-id="68565-199">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="68565-200">L'espressione await recupera il valore da `getLengthTask` in `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="68565-200">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>  
  
 <span data-ttu-id="68565-201">Di seguito viene illustrato il trasferimento del controllo dopo `client.GetStringAsync` (e `getStringTask`) sono state completate.</span><span class="sxs-lookup"><span data-stu-id="68565-201">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>  
  
 <span data-ttu-id="68565-202">![Passaggio cinque](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "cinque AsyncTrace")</span><span class="sxs-lookup"><span data-stu-id="68565-202">![Step FIVE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>  
  
 <span data-ttu-id="68565-203">`AccessTheWebAsync`Restituisce fino al completamento e il controllo `startButton_Click`, che è in attesa del completamento.</span><span class="sxs-lookup"><span data-stu-id="68565-203">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>  
  
### <a name="step-six"></a><span data-ttu-id="68565-204">Passaggio SEI</span><span class="sxs-lookup"><span data-stu-id="68565-204">Step SIX</span></span>  
 <span data-ttu-id="68565-205">Quando `AccessTheWebAsync` segnala che è completo, l'elaborazione può continuare oltre all'istruzione await nel `startButton_Async`.</span><span class="sxs-lookup"><span data-stu-id="68565-205">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="68565-206">Infatti, il programma è nulla da eseguire.</span><span class="sxs-lookup"><span data-stu-id="68565-206">In fact, the program has nothing more to do.</span></span>  
  
 <span data-ttu-id="68565-207">Le seguenti righe di output rappresentano la ripresa dell'elaborazione in `startButton_Async`:</span><span class="sxs-lookup"><span data-stu-id="68565-207">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>  
  
<span data-ttu-id="68565-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="68565-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="68565-209">L'espressione await recupera da `getLengthTask` il valore intero che rappresenta l'operando dell'istruzione return in `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="68565-209">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="68565-210">L'istruzione seguente assegna tale valore per il `contentLength` variabile.</span><span class="sxs-lookup"><span data-stu-id="68565-210">The following statement assigns that value to the `contentLength` variable.</span></span>  
  
<span data-ttu-id="68565-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="68565-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="68565-212">La figura seguente mostra la restituzione del controllo da `AccessTheWebAsync` a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="68565-212">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>  
  
 <span data-ttu-id="68565-213">![Passaggio sei](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace sei")</span><span class="sxs-lookup"><span data-stu-id="68565-213">![Step SIX](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68565-214">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68565-214">See Also</span></span>  
 <span data-ttu-id="68565-215">[Programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="68565-215">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="68565-216"> [Tipi restituiti asincroni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="68565-216"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="68565-217"> [Procedura dettagliata: Accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="68565-217"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="68565-218"> [Esempio asincrono: Flusso di controllo in programmi asincroni (c# e Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)</span><span class="sxs-lookup"><span data-stu-id="68565-218"> [Async Sample: Control Flow in Async Programs (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)</span></span>
