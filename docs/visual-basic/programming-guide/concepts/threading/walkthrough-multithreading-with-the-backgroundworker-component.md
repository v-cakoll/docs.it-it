---
title: Multithreading con il componente BackgroundWorker (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
ms.openlocfilehash: 07700aa526866729f1ba1a8d846f22ce333c356d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654291"
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="a9427-102">Procedura dettagliata: Multithreading con il componente BackgroundWorker (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9427-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="a9427-103">Questa procedura dettagliata spiega come creare un'applicazione Windows Form multithreading che cerca le occorrenze di una parola in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="a9427-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="a9427-104">Illustra quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a9427-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="a9427-105">Definizione di una classe con un metodo che può essere chiamato dal componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="a9427-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="a9427-106">Gestione degli eventi generati dal componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="a9427-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="a9427-107">Avvio di un componente <xref:System.ComponentModel.BackgroundWorker> per l'esecuzione di un metodo.</span><span class="sxs-lookup"><span data-stu-id="a9427-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="a9427-108">Implementazione di un pulsante `Cancel` che arresta il componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="a9427-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="a9427-109">Per creare l'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a9427-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="a9427-110">Aprire un nuovo progetto applicazione Windows Form di Visual Basic e creare un form denominato `Form1`.</span><span class="sxs-lookup"><span data-stu-id="a9427-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="a9427-111">Aggiungere due pulsanti e quattro caselle di testo a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="a9427-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="a9427-112">Assegnare i nomi agli oggetti come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a9427-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="a9427-113">Oggetto</span><span class="sxs-lookup"><span data-stu-id="a9427-113">Object</span></span>|<span data-ttu-id="a9427-114">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a9427-114">Property</span></span>|<span data-ttu-id="a9427-115">Impostazione</span><span class="sxs-lookup"><span data-stu-id="a9427-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="a9427-116">Primo pulsante</span><span class="sxs-lookup"><span data-stu-id="a9427-116">First button</span></span>|<span data-ttu-id="a9427-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a9427-117">`Name`, `Text`</span></span>|<span data-ttu-id="a9427-118">Start, Start</span><span class="sxs-lookup"><span data-stu-id="a9427-118">Start, Start</span></span>|  
    |<span data-ttu-id="a9427-119">Secondo pulsante</span><span class="sxs-lookup"><span data-stu-id="a9427-119">Second button</span></span>|<span data-ttu-id="a9427-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a9427-120">`Name`, `Text`</span></span>|<span data-ttu-id="a9427-121">Cancel, Cancel</span><span class="sxs-lookup"><span data-stu-id="a9427-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="a9427-122">Prima casella di testo</span><span class="sxs-lookup"><span data-stu-id="a9427-122">First text box</span></span>|<span data-ttu-id="a9427-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a9427-123">`Name`, `Text`</span></span>|<span data-ttu-id="a9427-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="a9427-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="a9427-125">Seconda casella di testo</span><span class="sxs-lookup"><span data-stu-id="a9427-125">Second text box</span></span>|<span data-ttu-id="a9427-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a9427-126">`Name`, `Text`</span></span>|<span data-ttu-id="a9427-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="a9427-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="a9427-128">Terza casella di testo</span><span class="sxs-lookup"><span data-stu-id="a9427-128">Third text box</span></span>|<span data-ttu-id="a9427-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a9427-129">`Name`, `Text`</span></span>|<span data-ttu-id="a9427-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="a9427-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="a9427-131">Quarta casella di testo</span><span class="sxs-lookup"><span data-stu-id="a9427-131">Fourth text box</span></span>|<span data-ttu-id="a9427-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="a9427-132">`Name`, `Text`</span></span>|<span data-ttu-id="a9427-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="a9427-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="a9427-134">Aggiungere un'etichetta accanto a ogni casella di testo.</span><span class="sxs-lookup"><span data-stu-id="a9427-134">Add a label next to each text box.</span></span> <span data-ttu-id="a9427-135">Impostare la proprietà `Text` per ogni etichetta come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a9427-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="a9427-136">Object</span><span class="sxs-lookup"><span data-stu-id="a9427-136">Object</span></span>|<span data-ttu-id="a9427-137">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a9427-137">Property</span></span>|<span data-ttu-id="a9427-138">Impostazione</span><span class="sxs-lookup"><span data-stu-id="a9427-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="a9427-139">Prima etichetta</span><span class="sxs-lookup"><span data-stu-id="a9427-139">First label</span></span>|`Text`|<span data-ttu-id="a9427-140">File di origine</span><span class="sxs-lookup"><span data-stu-id="a9427-140">Source File</span></span>|  
    |<span data-ttu-id="a9427-141">Seconda etichetta</span><span class="sxs-lookup"><span data-stu-id="a9427-141">Second label</span></span>|`Text`|<span data-ttu-id="a9427-142">Stringa di confronto</span><span class="sxs-lookup"><span data-stu-id="a9427-142">Compare String</span></span>|  
    |<span data-ttu-id="a9427-143">Terza etichetta</span><span class="sxs-lookup"><span data-stu-id="a9427-143">Third label</span></span>|`Text`|<span data-ttu-id="a9427-144">Parole corrispondenti</span><span class="sxs-lookup"><span data-stu-id="a9427-144">Matching Words</span></span>|  
    |<span data-ttu-id="a9427-145">Quarta etichetta</span><span class="sxs-lookup"><span data-stu-id="a9427-145">Fourth label</span></span>|`Text`|<span data-ttu-id="a9427-146">Righe conteggiate</span><span class="sxs-lookup"><span data-stu-id="a9427-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="a9427-147">Per creare un componente BackgroundWorker e sottoscrivere i relativi eventi</span><span class="sxs-lookup"><span data-stu-id="a9427-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="a9427-148">Aggiungere al form un componente <xref:System.ComponentModel.BackgroundWorker> dalla sezione **Componenti** della **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="a9427-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="a9427-149">Verrà visualizzato nella barra dei componenti del form.</span><span class="sxs-lookup"><span data-stu-id="a9427-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="a9427-150">Impostare le proprietà seguenti per l'oggetto BackgroundWorker1.</span><span class="sxs-lookup"><span data-stu-id="a9427-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="a9427-151">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a9427-151">Property</span></span>|<span data-ttu-id="a9427-152">Impostazione</span><span class="sxs-lookup"><span data-stu-id="a9427-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="a9427-153">True</span><span class="sxs-lookup"><span data-stu-id="a9427-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="a9427-154">True</span><span class="sxs-lookup"><span data-stu-id="a9427-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="a9427-155">Per definire il metodo che verrà eseguito in un thread separato</span><span class="sxs-lookup"><span data-stu-id="a9427-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="a9427-156">Scegliere **Aggiungi classe** dal menu **Progetto** per aggiungere una classe al progetto.</span><span class="sxs-lookup"><span data-stu-id="a9427-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="a9427-157">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a9427-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="a9427-158">Selezionare **Classe** nella finestra dei modelli e immettere `Words.vb` nel campo del nome.</span><span class="sxs-lookup"><span data-stu-id="a9427-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="a9427-159">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a9427-159">Click **Add**.</span></span> <span data-ttu-id="a9427-160">Viene visualizzata la classe `Words`.</span><span class="sxs-lookup"><span data-stu-id="a9427-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="a9427-161">Aggiungere il codice seguente alla classe `Words` :</span><span class="sxs-lookup"><span data-stu-id="a9427-161">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="a9427-162">Per gestire gli eventi dal thread</span><span class="sxs-lookup"><span data-stu-id="a9427-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="a9427-163">Aggiungere i seguenti gestori eventi al form principale:</span><span class="sxs-lookup"><span data-stu-id="a9427-163">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="a9427-164">Per avviare e chiamare un nuovo thread che esegue il metodo WordCount</span><span class="sxs-lookup"><span data-stu-id="a9427-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="a9427-165">Aggiungere le procedure seguenti al programma:</span><span class="sxs-lookup"><span data-stu-id="a9427-165">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="a9427-166">Chiamare il metodo `StartThread` dal pulsante `Start` nel form:</span><span class="sxs-lookup"><span data-stu-id="a9427-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="a9427-167">Per implementare un pulsante Annulla che interrompe il thread</span><span class="sxs-lookup"><span data-stu-id="a9427-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="a9427-168">Chiamare la procedura`StopThread` dal gestore eventi `Click` per il pulsante `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="a9427-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="a9427-169">Test</span><span class="sxs-lookup"><span data-stu-id="a9427-169">Testing</span></span>  
 <span data-ttu-id="a9427-170">È ora possibile testare l'applicazione per verificare che funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9427-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="a9427-171">Per eseguire il test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a9427-171">To test the application</span></span>  
  
1.  <span data-ttu-id="a9427-172">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a9427-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="a9427-173">Quando viene visualizzato il form immettere il percorso del file da testare nella casella `sourceFile`.</span><span class="sxs-lookup"><span data-stu-id="a9427-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="a9427-174">Ad esempio, se il file di test è denominato Test.txt, immettere C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="a9427-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="a9427-175">Nella seconda casella di testo immettere una parola o frase per l'applicazione da cercare nel file di testo.</span><span class="sxs-lookup"><span data-stu-id="a9427-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="a9427-176">Fare clic sul pulsante `Start`.</span><span class="sxs-lookup"><span data-stu-id="a9427-176">Click the `Start` button.</span></span> <span data-ttu-id="a9427-177">Il pulsante `LinesCounted` dovrebbe iniziare immediatamente ad aumentare.</span><span class="sxs-lookup"><span data-stu-id="a9427-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="a9427-178">Al termine l'applicazione visualizza un messaggio che indica che il conteggio è terminato.</span><span class="sxs-lookup"><span data-stu-id="a9427-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="a9427-179">Per testare il pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="a9427-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="a9427-180">Premere F5 per avviare l'applicazione e immettere il nome del file e la parola di ricerca come descritto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="a9427-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="a9427-181">Verificare che il file che scelto sia abbastanza grande da garantire di avere tempo a sufficienza per annullare la procedura prima che venga completata.</span><span class="sxs-lookup"><span data-stu-id="a9427-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="a9427-182">Fare clic sul pulsante `Start` per avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a9427-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="a9427-183">Fare clic sul pulsante `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="a9427-183">Click the `Cancel` button.</span></span> <span data-ttu-id="a9427-184">L'applicazione deve interrompere immediatamente il conteggio.</span><span class="sxs-lookup"><span data-stu-id="a9427-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a9427-185">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a9427-185">Next Steps</span></span>  
 <span data-ttu-id="a9427-186">Questa applicazione contiene alcune operazioni di base per la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="a9427-186">This application contains some basic error handling.</span></span> <span data-ttu-id="a9427-187">Rileva le stringhe di ricerca vuote.</span><span class="sxs-lookup"><span data-stu-id="a9427-187">It detects blank search strings.</span></span> <span data-ttu-id="a9427-188">È possibile rendere più efficace questo aggiungendo la gestione di altri errori, ad esempio il superamento del numero massimo di parole o righe che possono essere conteggiate.</span><span class="sxs-lookup"><span data-stu-id="a9427-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9427-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9427-189">See Also</span></span>  
 [<span data-ttu-id="a9427-190">Threading (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9427-190">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="a9427-191">Procedura dettagliata: Creazione di un componente con multithreading semplice con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9427-191">Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic</span></span>](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [<span data-ttu-id="a9427-192">Procedura: Eseguire e annullare la sottoscrizione a eventi</span><span class="sxs-lookup"><span data-stu-id="a9427-192">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
