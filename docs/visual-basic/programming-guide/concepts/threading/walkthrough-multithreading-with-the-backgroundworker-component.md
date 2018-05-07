---
title: Multithreading con il componente BackgroundWorker (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
ms.openlocfilehash: 07700aa526866729f1ba1a8d846f22ce333c356d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>Procedura dettagliata: Multithreading con il componente BackgroundWorker (Visual Basic)
Questa procedura dettagliata spiega come creare un'applicazione Windows Form multithreading che cerca le occorrenze di una parola in un file di testo. Illustra quanto segue:  
  
-   Definizione di una classe con un metodo che può essere chiamato dal componente <xref:System.ComponentModel.BackgroundWorker>.  
  
-   Gestione degli eventi generati dal componente <xref:System.ComponentModel.BackgroundWorker>.  
  
-   Avvio di un componente <xref:System.ComponentModel.BackgroundWorker> per l'esecuzione di un metodo.  
  
-   Implementazione di un pulsante `Cancel` che arresta il componente <xref:System.ComponentModel.BackgroundWorker>.  
  
### <a name="to-create-the-user-interface"></a>Per creare l'interfaccia utente  
  
1.  Aprire un nuovo progetto applicazione Windows Form di Visual Basic e creare un form denominato `Form1`.  
  
2.  Aggiungere due pulsanti e quattro caselle di testo a `Form1`.  
  
3.  Assegnare i nomi agli oggetti come illustrato nella tabella seguente.  
  
    |Oggetto|Proprietà|Impostazione|  
    |------------|--------------|-------------|  
    |Primo pulsante|`Name`, `Text`|Start, Start|  
    |Secondo pulsante|`Name`, `Text`|Cancel, Cancel|  
    |Prima casella di testo|`Name`, `Text`|SourceFile, ""|  
    |Seconda casella di testo|`Name`, `Text`|CompareString, ""|  
    |Terza casella di testo|`Name`, `Text`|WordsCounted, "0"|  
    |Quarta casella di testo|`Name`, `Text`|LinesCounted, "0"|  
  
4.  Aggiungere un'etichetta accanto a ogni casella di testo. Impostare la proprietà `Text` per ogni etichetta come illustrato nella tabella seguente.  
  
    |Object|Proprietà|Impostazione|  
    |------------|--------------|-------------|  
    |Prima etichetta|`Text`|File di origine|  
    |Seconda etichetta|`Text`|Stringa di confronto|  
    |Terza etichetta|`Text`|Parole corrispondenti|  
    |Quarta etichetta|`Text`|Righe conteggiate|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>Per creare un componente BackgroundWorker e sottoscrivere i relativi eventi  
  
1.  Aggiungere al form un componente <xref:System.ComponentModel.BackgroundWorker> dalla sezione **Componenti** della **casella degli strumenti**. Verrà visualizzato nella barra dei componenti del form.  
  
2.  Impostare le proprietà seguenti per l'oggetto BackgroundWorker1.  
  
    |Proprietà|Impostazione|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>Per definire il metodo che verrà eseguito in un thread separato  
  
1.  Scegliere **Aggiungi classe** dal menu **Progetto** per aggiungere una classe al progetto. Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.  
  
2.  Selezionare **Classe** nella finestra dei modelli e immettere `Words.vb` nel campo del nome.  
  
3.  Fare clic su **Aggiungi**. Viene visualizzata la classe `Words`.  
  
4.  Aggiungere il codice seguente alla classe `Words` :  
  
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
  
### <a name="to-handle-events-from-the-thread"></a>Per gestire gli eventi dal thread  
  
-   Aggiungere i seguenti gestori eventi al form principale:  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>Per avviare e chiamare un nuovo thread che esegue il metodo WordCount  
  
1.  Aggiungere le procedure seguenti al programma:  
  
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
  
2.  Chiamare il metodo `StartThread` dal pulsante `Start` nel form:  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>Per implementare un pulsante Annulla che interrompe il thread  
  
-   Chiamare la procedura`StopThread` dal gestore eventi `Click` per il pulsante `Cancel`.  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a>Test  
 È ora possibile testare l'applicazione per verificare che funzioni correttamente.  
  
#### <a name="to-test-the-application"></a>Per eseguire il test dell'applicazione  
  
1.  Premere F5 per eseguire l'applicazione.  
  
2.  Quando viene visualizzato il form immettere il percorso del file da testare nella casella `sourceFile`. Ad esempio, se il file di test è denominato Test.txt, immettere C:\Test.txt.  
  
3.  Nella seconda casella di testo immettere una parola o frase per l'applicazione da cercare nel file di testo.  
  
4.  Fare clic sul pulsante `Start`. Il pulsante `LinesCounted` dovrebbe iniziare immediatamente ad aumentare. Al termine l'applicazione visualizza un messaggio che indica che il conteggio è terminato.  
  
#### <a name="to-test-the-cancel-button"></a>Per testare il pulsante Annulla  
  
1.  Premere F5 per avviare l'applicazione e immettere il nome del file e la parola di ricerca come descritto nella procedura precedente. Verificare che il file che scelto sia abbastanza grande da garantire di avere tempo a sufficienza per annullare la procedura prima che venga completata.  
  
2.  Fare clic sul pulsante `Start` per avviare l'applicazione.  
  
3.  Fare clic sul pulsante `Cancel`. L'applicazione deve interrompere immediatamente il conteggio.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione contiene alcune operazioni di base per la gestione degli errori. Rileva le stringhe di ricerca vuote. È possibile rendere più efficace questo aggiungendo la gestione di altri errori, ad esempio il superamento del numero massimo di parole o righe che possono essere conteggiate.  
  
## <a name="see-also"></a>Vedere anche  
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [Procedura dettagliata: Creazione di un componente con multithreading semplice con Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [Procedura: Eseguire e annullare la sottoscrizione a eventi](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
