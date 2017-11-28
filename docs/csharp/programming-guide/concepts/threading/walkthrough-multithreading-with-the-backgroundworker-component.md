---
title: 'Procedura dettagliata: Multithreading con il componente BackgroundWorker (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ff670fbf-a0ac-40c1-ab08-9ed53768f880
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 72d6e9ab42ca270ebe0691be23ebe181b973620d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a><span data-ttu-id="7b159-102">Procedura dettagliata: Multithreading con il componente BackgroundWorker (C#)</span><span class="sxs-lookup"><span data-stu-id="7b159-102">Walkthrough: Multithreading with the BackgroundWorker Component (C#)</span></span>
<span data-ttu-id="7b159-103">Questa procedura dettagliata spiega come creare un'applicazione Windows Form multithreading che cerca le occorrenze di una parola in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="7b159-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="7b159-104">Illustra quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7b159-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="7b159-105">Definizione di una classe con un metodo che può essere chiamato dal componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="7b159-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="7b159-106">Gestione degli eventi generati dal componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="7b159-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="7b159-107">Avvio di un componente <xref:System.ComponentModel.BackgroundWorker> per l'esecuzione di un metodo.</span><span class="sxs-lookup"><span data-stu-id="7b159-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="7b159-108">Implementazione di un pulsante `Cancel` che arresta il componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="7b159-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="7b159-109">Per creare l'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="7b159-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="7b159-110">Aprire un nuovo progetto a Windows Forms Application in C# e creare un form denominato `Form1`.</span><span class="sxs-lookup"><span data-stu-id="7b159-110">Open a new C# Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="7b159-111">Aggiungere due pulsanti e quattro caselle di testo a `Form1`.</span><span class="sxs-lookup"><span data-stu-id="7b159-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="7b159-112">Assegnare i nomi agli oggetti come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7b159-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="7b159-113">Oggetto</span><span class="sxs-lookup"><span data-stu-id="7b159-113">Object</span></span>|<span data-ttu-id="7b159-114">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7b159-114">Property</span></span>|<span data-ttu-id="7b159-115">Impostazione</span><span class="sxs-lookup"><span data-stu-id="7b159-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="7b159-116">Primo pulsante</span><span class="sxs-lookup"><span data-stu-id="7b159-116">First button</span></span>|<span data-ttu-id="7b159-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="7b159-117">`Name`, `Text`</span></span>|<span data-ttu-id="7b159-118">Start, Start</span><span class="sxs-lookup"><span data-stu-id="7b159-118">Start, Start</span></span>|  
    |<span data-ttu-id="7b159-119">Secondo pulsante</span><span class="sxs-lookup"><span data-stu-id="7b159-119">Second button</span></span>|<span data-ttu-id="7b159-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="7b159-120">`Name`, `Text`</span></span>|<span data-ttu-id="7b159-121">Cancel, Cancel</span><span class="sxs-lookup"><span data-stu-id="7b159-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="7b159-122">Prima casella di testo</span><span class="sxs-lookup"><span data-stu-id="7b159-122">First text box</span></span>|<span data-ttu-id="7b159-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="7b159-123">`Name`, `Text`</span></span>|<span data-ttu-id="7b159-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="7b159-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="7b159-125">Seconda casella di testo</span><span class="sxs-lookup"><span data-stu-id="7b159-125">Second text box</span></span>|<span data-ttu-id="7b159-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="7b159-126">`Name`, `Text`</span></span>|<span data-ttu-id="7b159-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="7b159-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="7b159-128">Terza casella di testo</span><span class="sxs-lookup"><span data-stu-id="7b159-128">Third text box</span></span>|<span data-ttu-id="7b159-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="7b159-129">`Name`, `Text`</span></span>|<span data-ttu-id="7b159-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="7b159-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="7b159-131">Quarta casella di testo</span><span class="sxs-lookup"><span data-stu-id="7b159-131">Fourth text box</span></span>|<span data-ttu-id="7b159-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="7b159-132">`Name`, `Text`</span></span>|<span data-ttu-id="7b159-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="7b159-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="7b159-134">Aggiungere un'etichetta accanto a ogni casella di testo.</span><span class="sxs-lookup"><span data-stu-id="7b159-134">Add a label next to each text box.</span></span> <span data-ttu-id="7b159-135">Impostare la proprietà `Text` per ogni etichetta come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7b159-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="7b159-136">Oggetto</span><span class="sxs-lookup"><span data-stu-id="7b159-136">Object</span></span>|<span data-ttu-id="7b159-137">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7b159-137">Property</span></span>|<span data-ttu-id="7b159-138">Impostazione</span><span class="sxs-lookup"><span data-stu-id="7b159-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="7b159-139">Prima etichetta</span><span class="sxs-lookup"><span data-stu-id="7b159-139">First label</span></span>|`Text`|<span data-ttu-id="7b159-140">File di origine</span><span class="sxs-lookup"><span data-stu-id="7b159-140">Source File</span></span>|  
    |<span data-ttu-id="7b159-141">Seconda etichetta</span><span class="sxs-lookup"><span data-stu-id="7b159-141">Second label</span></span>|`Text`|<span data-ttu-id="7b159-142">Stringa di confronto</span><span class="sxs-lookup"><span data-stu-id="7b159-142">Compare String</span></span>|  
    |<span data-ttu-id="7b159-143">Terza etichetta</span><span class="sxs-lookup"><span data-stu-id="7b159-143">Third label</span></span>|`Text`|<span data-ttu-id="7b159-144">Parole corrispondenti</span><span class="sxs-lookup"><span data-stu-id="7b159-144">Matching Words</span></span>|  
    |<span data-ttu-id="7b159-145">Quarta etichetta</span><span class="sxs-lookup"><span data-stu-id="7b159-145">Fourth label</span></span>|`Text`|<span data-ttu-id="7b159-146">Righe conteggiate</span><span class="sxs-lookup"><span data-stu-id="7b159-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="7b159-147">Per creare un componente BackgroundWorker e sottoscrivere i relativi eventi</span><span class="sxs-lookup"><span data-stu-id="7b159-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="7b159-148">Aggiungere al form un componente <xref:System.ComponentModel.BackgroundWorker> dalla sezione **Componenti** della **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="7b159-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="7b159-149">Verrà visualizzato nella barra dei componenti del form.</span><span class="sxs-lookup"><span data-stu-id="7b159-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="7b159-150">Impostare le proprietà seguenti per l'oggetto backgroundWorker1.</span><span class="sxs-lookup"><span data-stu-id="7b159-150">Set the following properties for the backgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="7b159-151">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7b159-151">Property</span></span>|<span data-ttu-id="7b159-152">Impostazione</span><span class="sxs-lookup"><span data-stu-id="7b159-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="7b159-153">True</span><span class="sxs-lookup"><span data-stu-id="7b159-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="7b159-154">True</span><span class="sxs-lookup"><span data-stu-id="7b159-154">True</span></span>|  
  
3.  <span data-ttu-id="7b159-155">Sottoscrivere gli eventi dell'oggetto backgroundWorker1.</span><span class="sxs-lookup"><span data-stu-id="7b159-155">Subscribe to the events of the backgroundWorker1 object.</span></span> <span data-ttu-id="7b159-156">Nella parte superiore della finestra **Proprietà** fare clic sull'icona **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="7b159-156">At the top of the **Properties** window, click the **Events** icon.</span></span> <span data-ttu-id="7b159-157">Fare doppio clic sull'evento `RunWorkerCompleted` per creare un metodo del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="7b159-157">Double-click the `RunWorkerCompleted` event to create an event handler method.</span></span> <span data-ttu-id="7b159-158">Eseguire la stessa operazione per gli eventi `ProgressChanged` e `DoWork`.</span><span class="sxs-lookup"><span data-stu-id="7b159-158">Do the same for the `ProgressChanged` and `DoWork` events.</span></span>  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="7b159-159">Per definire il metodo che verrà eseguito in un thread separato</span><span class="sxs-lookup"><span data-stu-id="7b159-159">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="7b159-160">Scegliere **Aggiungi classe** dal menu **Progetto** per aggiungere una classe al progetto.</span><span class="sxs-lookup"><span data-stu-id="7b159-160">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="7b159-161">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="7b159-161">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="7b159-162">Selezionare **Classe** nella finestra dei modelli e immettere `Words.cs` nel campo del nome.</span><span class="sxs-lookup"><span data-stu-id="7b159-162">Select **Class** from the templates window and enter `Words.cs` in the name field.</span></span>  
  
3.  <span data-ttu-id="7b159-163">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7b159-163">Click **Add**.</span></span> <span data-ttu-id="7b159-164">Viene visualizzata la classe `Words`.</span><span class="sxs-lookup"><span data-stu-id="7b159-164">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="7b159-165">Aggiungere il codice seguente alla classe `Words` :</span><span class="sxs-lookup"><span data-stu-id="7b159-165">Add the following code to the `Words` class:</span></span>  
  
    ```csharp  
    public class Words  
    {  
        // Object to store the current state, for passing to the caller.  
        public class CurrentState  
        {  
            public int LinesCounted;  
            public int WordsMatched;  
        }  
  
        public string SourceFile;  
        public string CompareString;  
        private int WordCount;  
        private int LinesCounted;  
  
        public void CountWords(  
            System.ComponentModel.BackgroundWorker worker,  
            System.ComponentModel.DoWorkEventArgs e)  
        {  
            // Initialize the variables.  
            CurrentState state = new CurrentState();  
            string line = "";  
            int elapsedTime = 20;  
            DateTime lastReportDateTime = DateTime.Now;  
  
            if (CompareString == null ||  
                CompareString == System.String.Empty)  
            {  
                throw new Exception("CompareString not specified.");  
            }  
  
            // Open a new stream.  
            using (System.IO.StreamReader myStream = new System.IO.StreamReader(SourceFile))  
            {  
                // Process lines while there are lines remaining in the file.  
                while (!myStream.EndOfStream)  
                {  
                    if (worker.CancellationPending)  
                    {  
                        e.Cancel = true;  
                        break;  
                    }  
                    else  
                    {  
                        line = myStream.ReadLine();  
                        WordCount += CountInString(line, CompareString);  
                        LinesCounted += 1;  
  
                        // Raise an event so the form can monitor progress.  
                        int compare = DateTime.Compare(  
                            DateTime.Now, lastReportDateTime.AddMilliseconds(elapsedTime));  
                        if (compare > 0)  
                        {  
                            state.LinesCounted = LinesCounted;  
                            state.WordsMatched = WordCount;  
                            worker.ReportProgress(0, state);  
                            lastReportDateTime = DateTime.Now;  
                        }  
                    }  
                    // Uncomment for testing.  
                    //System.Threading.Thread.Sleep(5);  
                }  
  
                // Report the final count values.  
                state.LinesCounted = LinesCounted;  
                state.WordsMatched = WordCount;  
                worker.ReportProgress(0, state);  
            }  
        }  
  
        private int CountInString(  
            string SourceString,  
            string CompareString)  
        {  
            // This function counts the number of times  
            // a word is found in a line.  
            if (SourceString == null)  
            {  
                return 0;  
            }  
  
            string EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString);  
  
            System.Text.RegularExpressions.Regex regex;  
            regex = new System.Text.RegularExpressions.Regex(   
                // To count all occurrences of the string, even within words, remove  
                // both instances of @"\b" from the following line.  
                @"\b" + EscapedCompareString + @"\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase);  
  
            System.Text.RegularExpressions.MatchCollection matches;  
            matches = regex.Matches(SourceString);  
            return matches.Count;  
        }  
  
    }  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="7b159-166">Per gestire gli eventi dal thread</span><span class="sxs-lookup"><span data-stu-id="7b159-166">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="7b159-167">Aggiungere i seguenti gestori eventi al form principale:</span><span class="sxs-lookup"><span data-stu-id="7b159-167">Add the following event handlers to your main form:</span></span>  
  
    ```csharp  
    private void backgroundWorker1_RunWorkerCompleted(object sender, RunWorkerCompletedEventArgs e)  
    {  
    // This event handler is called when the background thread finishes.  
    // This method runs on the main thread.  
    if (e.Error != null)  
        MessageBox.Show("Error: " + e.Error.Message);  
    else if (e.Cancelled)  
        MessageBox.Show("Word counting canceled.");  
    else  
        MessageBox.Show("Finished counting words.");  
    }  
  
    private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)  
    {  
        // This method runs on the main thread.  
        Words.CurrentState state =  
            (Words.CurrentState)e.UserState;  
        this.LinesCounted.Text = state.LinesCounted.ToString();  
        this.WordsCounted.Text = state.WordsMatched.ToString();  
    }  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="7b159-168">Per avviare e chiamare un nuovo thread che esegue il metodo WordCount</span><span class="sxs-lookup"><span data-stu-id="7b159-168">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="7b159-169">Aggiungere le procedure seguenti al programma:</span><span class="sxs-lookup"><span data-stu-id="7b159-169">Add the following procedures to your program:</span></span>  
  
    ```csharp  
    private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)  
    {  
        // This event handler is where the actual work is done.  
        // This method runs on the background thread.  
  
        // Get the BackgroundWorker object that raised this event.  
        System.ComponentModel.BackgroundWorker worker;  
        worker = (System.ComponentModel.BackgroundWorker)sender;  
  
        // Get the Words object and call the main method.  
        Words WC = (Words)e.Argument;  
        WC.CountWords(worker, e);  
    }  
  
    private void StartThread()  
    {  
        // This method runs on the main thread.  
        this.WordsCounted.Text = "0";  
  
        // Initialize the object that the background worker calls.  
        Words WC = new Words();  
        WC.CompareString = this.CompareString.Text;  
        WC.SourceFile = this.SourceFile.Text;  
  
        // Start the asynchronous operation.  
        backgroundWorker1.RunWorkerAsync(WC);  
    }  
    ```  
  
2.  <span data-ttu-id="7b159-170">Chiamare il metodo `StartThread` dal pulsante `Start` nel form:</span><span class="sxs-lookup"><span data-stu-id="7b159-170">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="7b159-171">Per implementare un pulsante Annulla che interrompe il thread</span><span class="sxs-lookup"><span data-stu-id="7b159-171">To implement a Cancel button that stops the thread</span></span>  
  
    -   <span data-ttu-id="7b159-172">Chiamare la procedura`StopThread` dal gestore eventi `Click` per il pulsante `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="7b159-172">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
        ```  
  
## <a name="testing"></a><span data-ttu-id="7b159-173">Test</span><span class="sxs-lookup"><span data-stu-id="7b159-173">Testing</span></span>  
 <span data-ttu-id="7b159-174">È ora possibile testare l'applicazione per verificare che funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="7b159-174">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="7b159-175">Per eseguire il test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7b159-175">To test the application</span></span>  
  
1.  <span data-ttu-id="7b159-176">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7b159-176">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="7b159-177">Quando viene visualizzato il form immettere il percorso del file da testare nella casella `sourceFile`.</span><span class="sxs-lookup"><span data-stu-id="7b159-177">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="7b159-178">Ad esempio, se il file di test è denominato Test.txt, immettere C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="7b159-178">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="7b159-179">Nella seconda casella di testo immettere una parola o frase per l'applicazione da cercare nel file di testo.</span><span class="sxs-lookup"><span data-stu-id="7b159-179">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="7b159-180">Fare clic sul pulsante `Start`.</span><span class="sxs-lookup"><span data-stu-id="7b159-180">Click the `Start` button.</span></span> <span data-ttu-id="7b159-181">Il pulsante `LinesCounted` dovrebbe iniziare immediatamente ad aumentare.</span><span class="sxs-lookup"><span data-stu-id="7b159-181">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="7b159-182">Al termine l'applicazione visualizza un messaggio che indica che il conteggio è terminato.</span><span class="sxs-lookup"><span data-stu-id="7b159-182">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="7b159-183">Per testare il pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="7b159-183">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="7b159-184">Premere F5 per avviare l'applicazione e immettere il nome del file e la parola di ricerca come descritto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="7b159-184">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="7b159-185">Verificare che il file che scelto sia abbastanza grande da garantire di avere tempo a sufficienza per annullare la procedura prima che venga completata.</span><span class="sxs-lookup"><span data-stu-id="7b159-185">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="7b159-186">Fare clic sul pulsante `Start` per avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7b159-186">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="7b159-187">Fare clic sul pulsante `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="7b159-187">Click the `Cancel` button.</span></span> <span data-ttu-id="7b159-188">L'applicazione deve interrompere immediatamente il conteggio.</span><span class="sxs-lookup"><span data-stu-id="7b159-188">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7b159-189">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7b159-189">Next Steps</span></span>  
 <span data-ttu-id="7b159-190">Questa applicazione contiene alcune operazioni di base per la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="7b159-190">This application contains some basic error handling.</span></span> <span data-ttu-id="7b159-191">Rileva le stringhe di ricerca vuote.</span><span class="sxs-lookup"><span data-stu-id="7b159-191">It detects blank search strings.</span></span> <span data-ttu-id="7b159-192">È possibile rendere più efficace questo aggiungendo la gestione di altri errori, ad esempio il superamento del numero massimo di parole o righe che possono essere conteggiate.</span><span class="sxs-lookup"><span data-stu-id="7b159-192">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b159-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b159-193">See Also</span></span>  
 [<span data-ttu-id="7b159-194">Threading (C#)</span><span class="sxs-lookup"><span data-stu-id="7b159-194">Threading (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="7b159-195">Procedura: Eseguire e annullare la sottoscrizione a eventi</span><span class="sxs-lookup"><span data-stu-id="7b159-195">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
