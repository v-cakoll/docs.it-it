---
title: Multithreading con il componente BackgroundWorker (Visual Basic) | Documenti di Microsoft
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
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
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
ms.openlocfilehash: 88d0711c8e417ae5c95b0e109504b69882015241
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="5a083-102">Procedura dettagliata: Multithreading con il componente BackgroundWorker (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a083-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="5a083-103">Questa procedura dettagliata viene illustrato come creare un'applicazione Windows Form con multithreading che cerca un file di testo per le occorrenze di una parola.</span><span class="sxs-lookup"><span data-stu-id="5a083-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="5a083-104">Viene illustrato come:</span><span class="sxs-lookup"><span data-stu-id="5a083-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="5a083-105">Definizione di una classe con un metodo che può essere chiamato dal <xref:System.ComponentModel.BackgroundWorker>component.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="5a083-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="5a083-106">Gestione degli eventi generati dal <xref:System.ComponentModel.BackgroundWorker>component.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="5a083-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="5a083-107">Avvio di un <xref:System.ComponentModel.BackgroundWorker>componente per l'esecuzione di un metodo.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="5a083-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="5a083-108">Implementazione di un `Cancel` pulsante che consente di arrestare il <xref:System.ComponentModel.BackgroundWorker>component.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="5a083-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="5a083-109">Per creare l'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="5a083-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="5a083-110">Aprire un nuovo progetto applicazione Windows Form di Visual Basic e creare un form denominato `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5a083-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="5a083-111">Aggiungere due pulsanti e quattro caselle di testo per `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5a083-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="5a083-112">Denominare gli oggetti come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5a083-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="5a083-113">Oggetto</span><span class="sxs-lookup"><span data-stu-id="5a083-113">Object</span></span>|<span data-ttu-id="5a083-114">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5a083-114">Property</span></span>|<span data-ttu-id="5a083-115">Impostazione</span><span class="sxs-lookup"><span data-stu-id="5a083-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="5a083-116">Primo pulsante</span><span class="sxs-lookup"><span data-stu-id="5a083-116">First button</span></span>|<span data-ttu-id="5a083-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="5a083-117">`Name`, `Text`</span></span>|<span data-ttu-id="5a083-118">Inizio, avvio</span><span class="sxs-lookup"><span data-stu-id="5a083-118">Start, Start</span></span>|  
    |<span data-ttu-id="5a083-119">Secondo pulsante</span><span class="sxs-lookup"><span data-stu-id="5a083-119">Second button</span></span>|<span data-ttu-id="5a083-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="5a083-120">`Name`, `Text`</span></span>|<span data-ttu-id="5a083-121">Annulla, Annulla</span><span class="sxs-lookup"><span data-stu-id="5a083-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="5a083-122">Prima casella di testo</span><span class="sxs-lookup"><span data-stu-id="5a083-122">First text box</span></span>|<span data-ttu-id="5a083-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="5a083-123">`Name`, `Text`</span></span>|<span data-ttu-id="5a083-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="5a083-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="5a083-125">Seconda casella di testo</span><span class="sxs-lookup"><span data-stu-id="5a083-125">Second text box</span></span>|<span data-ttu-id="5a083-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="5a083-126">`Name`, `Text`</span></span>|<span data-ttu-id="5a083-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="5a083-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="5a083-128">Terza casella di testo</span><span class="sxs-lookup"><span data-stu-id="5a083-128">Third text box</span></span>|<span data-ttu-id="5a083-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="5a083-129">`Name`, `Text`</span></span>|<span data-ttu-id="5a083-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="5a083-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="5a083-131">Quarta casella di testo</span><span class="sxs-lookup"><span data-stu-id="5a083-131">Fourth text box</span></span>|<span data-ttu-id="5a083-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="5a083-132">`Name`, `Text`</span></span>|<span data-ttu-id="5a083-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="5a083-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="5a083-134">Aggiungere un'etichetta accanto a ciascuna casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5a083-134">Add a label next to each text box.</span></span> <span data-ttu-id="5a083-135">Impostare il `Text` proprietà per ogni etichetta, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5a083-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="5a083-136">Oggetto</span><span class="sxs-lookup"><span data-stu-id="5a083-136">Object</span></span>|<span data-ttu-id="5a083-137">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5a083-137">Property</span></span>|<span data-ttu-id="5a083-138">Impostazione</span><span class="sxs-lookup"><span data-stu-id="5a083-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="5a083-139">Prima etichetta</span><span class="sxs-lookup"><span data-stu-id="5a083-139">First label</span></span>|`Text`|<span data-ttu-id="5a083-140">File di origine</span><span class="sxs-lookup"><span data-stu-id="5a083-140">Source File</span></span>|  
    |<span data-ttu-id="5a083-141">Seconda etichetta</span><span class="sxs-lookup"><span data-stu-id="5a083-141">Second label</span></span>|`Text`|<span data-ttu-id="5a083-142">Confronto di stringhe</span><span class="sxs-lookup"><span data-stu-id="5a083-142">Compare String</span></span>|  
    |<span data-ttu-id="5a083-143">Terza etichetta</span><span class="sxs-lookup"><span data-stu-id="5a083-143">Third label</span></span>|`Text`|<span data-ttu-id="5a083-144">Numero di termini corrispondenti</span><span class="sxs-lookup"><span data-stu-id="5a083-144">Matching Words</span></span>|  
    |<span data-ttu-id="5a083-145">Quarta etichetta</span><span class="sxs-lookup"><span data-stu-id="5a083-145">Fourth label</span></span>|`Text`|<span data-ttu-id="5a083-146">Conteggiata righe</span><span class="sxs-lookup"><span data-stu-id="5a083-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="5a083-147">Per creare un componente BackgroundWorker e sottoscrivere gli eventi</span><span class="sxs-lookup"><span data-stu-id="5a083-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="5a083-148">Aggiungere un <xref:System.ComponentModel.BackgroundWorker>componente il **componenti** sezione il **della casella degli strumenti** al form.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="5a083-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="5a083-149">Verrà visualizzato nella barra dei componenti del form.</span><span class="sxs-lookup"><span data-stu-id="5a083-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="5a083-150">Impostare le proprietà seguenti per l'oggetto BackgroundWorker1.</span><span class="sxs-lookup"><span data-stu-id="5a083-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="5a083-151">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5a083-151">Property</span></span>|<span data-ttu-id="5a083-152">Impostazione</span><span class="sxs-lookup"><span data-stu-id="5a083-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="5a083-153">True</span><span class="sxs-lookup"><span data-stu-id="5a083-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="5a083-154">True</span><span class="sxs-lookup"><span data-stu-id="5a083-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="5a083-155">Per definire il metodo che verrà eseguito in un thread separato</span><span class="sxs-lookup"><span data-stu-id="5a083-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="5a083-156">Dal **progetto** menu, scegliere **Aggiungi classe** per aggiungere una classe al progetto.</span><span class="sxs-lookup"><span data-stu-id="5a083-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="5a083-157">Il **Aggiungi nuovo elemento** viene visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="5a083-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="5a083-158">Selezionare **classe** nella finestra dei modelli e immettere `Words.vb` nel campo nome.</span><span class="sxs-lookup"><span data-stu-id="5a083-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="5a083-159">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5a083-159">Click **Add**.</span></span> <span data-ttu-id="5a083-160">La `Words` classe viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="5a083-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="5a083-161">Aggiungere il codice seguente alla classe `Words` :</span><span class="sxs-lookup"><span data-stu-id="5a083-161">Add the following code to the `Words` class:</span></span>  
  
    ```vb  
    Public Class Words  
        ' Object to store the current state, for passing to the caller.  
        Public Class CurrentState  
            Public LinesCounted As Integer  
            Public WordsMatched As Integer  
        End Class  
  
        Public SourceFile As String  
        Public CompareString As String  
        Private WordCount As Integer = 0  
        Private LinesCounted As Integer = 0  
  
        Public Sub CountWords(  
            ByVal worker As System.ComponentModel.BackgroundWorker,  
            ByVal e As System.ComponentModel.DoWorkEventArgs  
        )  
            ' Initialize the variables.  
            Dim state As New CurrentState  
            Dim line = ""  
            Dim elapsedTime = 20  
            Dim lastReportDateTime = Now  
  
            If CompareString Is Nothing OrElse  
               CompareString = System.String.Empty Then  
  
               Throw New Exception("CompareString not specified.")  
            End If  
  
            Using myStream As New System.IO.StreamReader(SourceFile)  
  
                ' Process lines while there are lines remaining in the file.  
                Do While Not myStream.EndOfStream  
                    If worker.CancellationPending Then  
                        e.Cancel = True  
                        Exit Do  
                    Else  
                        line = myStream.ReadLine  
                        WordCount += CountInString(line, CompareString)  
                        LinesCounted += 1  
  
                        ' Raise an event so the form can monitor progress.  
                        If Now > lastReportDateTime.AddMilliseconds(elapsedTime) Then  
                            state.LinesCounted = LinesCounted  
                            state.WordsMatched = WordCount  
                            worker.ReportProgress(0, state)  
                            lastReportDateTime = Now  
                        End If  
  
                        ' Uncomment for testing.  
                        'System.Threading.Thread.Sleep(5)  
                    End If  
                Loop  
  
                ' Report the final count values.  
                state.LinesCounted = LinesCounted  
                state.WordsMatched = WordCount  
                worker.ReportProgress(0, state)  
            End Using  
        End Sub  
  
        Private Function CountInString(  
            ByVal SourceString As String,  
            ByVal CompareString As String  
        ) As Integer  
            ' This function counts the number of times  
            ' a word is found in a line.  
            If SourceString Is Nothing Then  
                Return 0  
            End If  
  
            Dim EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString)  
  
            ' To count all occurrences of the string, even within words, remove  
            ' both instances of "\b".  
            Dim regex As New System.Text.RegularExpressions.Regex(  
                "\b" + EscapedCompareString + "\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase)  
  
            Dim matches As System.Text.RegularExpressions.MatchCollection  
            matches = regex.Matches(SourceString)  
            Return matches.Count  
        End Function  
    End Class  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="5a083-162">Per gestire gli eventi dal thread</span><span class="sxs-lookup"><span data-stu-id="5a083-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="5a083-163">Aggiungere i gestori eventi seguenti al form principale:</span><span class="sxs-lookup"><span data-stu-id="5a083-163">Add the following event handlers to your main form:</span></span>  
  
    ```vb  
    Private Sub BackgroundWorker1_RunWorkerCompleted(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
      ) Handles BackgroundWorker1.RunWorkerCompleted  
  
        ' This event handler is called when the background thread finishes.  
        ' This method runs on the main thread.  
        If e.Error IsNot Nothing Then  
            MessageBox.Show("Error: " & e.Error.Message)  
        ElseIf e.Cancelled Then  
            MessageBox.Show("Word counting canceled.")  
        Else  
            MessageBox.Show("Finished counting words.")  
        End If  
    End Sub  
  
    Private Sub BackgroundWorker1_ProgressChanged(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.ProgressChangedEventArgs  
      ) Handles BackgroundWorker1.ProgressChanged  
  
        ' This method runs on the main thread.  
        Dim state As Words.CurrentState =   
            CType(e.UserState, Words.CurrentState)  
        Me.LinesCounted.Text = state.LinesCounted.ToString  
        Me.WordsCounted.Text = state.WordsMatched.ToString  
    End Sub  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="5a083-164">Per avviare e chiamare un nuovo thread che esegue il metodo WordCount</span><span class="sxs-lookup"><span data-stu-id="5a083-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="5a083-165">Aggiungere le seguenti procedure per il programma:</span><span class="sxs-lookup"><span data-stu-id="5a083-165">Add the following procedures to your program:</span></span>  
  
    ```vb  
    Private Sub BackgroundWorker1_DoWork(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.DoWorkEventArgs  
      ) Handles BackgroundWorker1.DoWork  
  
        ' This event handler is where the actual work is done.  
        ' This method runs on the background thread.  
  
        ' Get the BackgroundWorker object that raised this event.  
        Dim worker As System.ComponentModel.BackgroundWorker  
        worker = CType(sender, System.ComponentModel.BackgroundWorker)  
  
        ' Get the Words object and call the main method.  
        Dim WC As Words = CType(e.Argument, Words)  
        WC.CountWords(worker, e)  
    End Sub  
  
    Sub StartThread()  
        ' This method runs on the main thread.  
        Me.WordsCounted.Text = "0"  
  
        ' Initialize the object that the background worker calls.  
        Dim WC As New Words  
        WC.CompareString = Me.CompareString.Text  
        WC.SourceFile = Me.SourceFile.Text  
  
        ' Start the asynchronous operation.  
        BackgroundWorker1.RunWorkerAsync(WC)  
    End Sub  
    ```  
  
2.  <span data-ttu-id="5a083-166">Chiamare il `StartThread` dal metodo di `Start` pulsante nel form:</span><span class="sxs-lookup"><span data-stu-id="5a083-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="5a083-167">Per implementare un pulsante Annulla che interrompe il thread</span><span class="sxs-lookup"><span data-stu-id="5a083-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="5a083-168">Chiamare il `StopThread` procedura il `Click` gestore eventi per il `Cancel` pulsante.</span><span class="sxs-lookup"><span data-stu-id="5a083-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="5a083-169">Test</span><span class="sxs-lookup"><span data-stu-id="5a083-169">Testing</span></span>  
 <span data-ttu-id="5a083-170">È ora possibile testare l'applicazione per assicurarsi che funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="5a083-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="5a083-171">Per eseguire il test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="5a083-171">To test the application</span></span>  
  
1.  <span data-ttu-id="5a083-172">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5a083-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="5a083-173">Quando viene visualizzato il modulo, immettere il percorso del file per il file che si desidera testare il `sourceFile` casella.</span><span class="sxs-lookup"><span data-stu-id="5a083-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="5a083-174">Ad esempio, supponendo che il file di test è denominato test. txt, immettere c:\test.txt..</span><span class="sxs-lookup"><span data-stu-id="5a083-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="5a083-175">Nella seconda casella di testo, immettere una parola o frase per l'applicazione per la ricerca nel file di testo.</span><span class="sxs-lookup"><span data-stu-id="5a083-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="5a083-176">Fare clic sul pulsante `Start`.</span><span class="sxs-lookup"><span data-stu-id="5a083-176">Click the `Start` button.</span></span> <span data-ttu-id="5a083-177">Il `LinesCounted` pulsante dovrebbe iniziare immediatamente.</span><span class="sxs-lookup"><span data-stu-id="5a083-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="5a083-178">L'applicazione visualizza il messaggio "Terminata Counting" è terminato.</span><span class="sxs-lookup"><span data-stu-id="5a083-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="5a083-179">Per testare il pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="5a083-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="5a083-180">Premere F5 per avviare l'applicazione e immettere il file nome e la ricerca come descritto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="5a083-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="5a083-181">Assicurarsi che il file che scelto è sufficientemente elevato da garantire che essere in grado di annullare la procedura prima del completamento.</span><span class="sxs-lookup"><span data-stu-id="5a083-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="5a083-182">Fare clic sul `Start` pulsante per avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5a083-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="5a083-183">Fare clic sul pulsante `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="5a083-183">Click the `Cancel` button.</span></span> <span data-ttu-id="5a083-184">Il conteggio dovrebbe arrestarsi immediatamente.</span><span class="sxs-lookup"><span data-stu-id="5a083-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5a083-185">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5a083-185">Next Steps</span></span>  
 <span data-ttu-id="5a083-186">Questa applicazione contiene alcune gestione degli errori di base.</span><span class="sxs-lookup"><span data-stu-id="5a083-186">This application contains some basic error handling.</span></span> <span data-ttu-id="5a083-187">Rileva le stringhe di ricerca vuoto.</span><span class="sxs-lookup"><span data-stu-id="5a083-187">It detects blank search strings.</span></span> <span data-ttu-id="5a083-188">È possibile rendere più affidabile questo programma tramite la gestione di altri errori, ad esempio il superamento del numero massimo di parole o le righe che possono essere conteggiate.</span><span class="sxs-lookup"><span data-stu-id="5a083-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a083-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a083-189">See Also</span></span>  
 <span data-ttu-id="5a083-190">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="5a083-190">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
<span data-ttu-id="5a083-191"> [Procedura dettagliata: Creazione di componenti multithreading semplici con Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001) </span><span class="sxs-lookup"><span data-stu-id="5a083-191"> [Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001) </span></span>  
<span data-ttu-id="5a083-192"> [Procedura: Eseguire e annullare la sottoscrizione a eventi](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span><span class="sxs-lookup"><span data-stu-id="5a083-192"> [How to: Subscribe to and Unsubscribe from Events](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span></span>
