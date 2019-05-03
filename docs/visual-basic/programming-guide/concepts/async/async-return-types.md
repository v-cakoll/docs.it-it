---
title: Tipi restituiti asincroni (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
ms.openlocfilehash: 227a187f7046d128a7170b272f90f77cfaac61c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022103"
---
# <a name="async-return-types-visual-basic"></a>Tipi restituiti asincroni (Visual Basic)
I metodi asincroni hanno tre possibili tipi restituiti: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> e void. In Visual Basic il tipo restituito void è scritto come routine [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md). Per altre informazioni sui metodi asincroni, vedere [programmazione asincrona con Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Ogni tipo restituito viene esaminato in una delle sezioni seguenti e alla fine dell'argomento è disponibile un esempio completo che usa tutti i tre tipi.  
  
> [!NOTE]
>  Per eseguire l'esempio, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.  
  
## <a name="BKMK_TaskTReturnType"></a> Tipo restituito task(T)  
 Il <xref:System.Threading.Tasks.Task%601> tipo restituito viene utilizzato per un metodo asincrono che contiene un [restituire](../../../../visual-basic/language-reference/statements/return-statement.md) istruzione in cui l'operando è di tipo `TResult`.  
  
 Nell'esempio seguente il metodo asincrono `TaskOfT_MethodAsync` contiene un'istruzione return che restituisce un valore intero. La dichiarazione del metodo deve quindi specificare un tipo restituito di `Task(Of Integer)`.  
  
```vb  
' TASK(OF T) EXAMPLE  
Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.FromResult is a placeholder for actual work that returns a string.  
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
    ' The method then can process the result in some way.  
    Dim leisureHours As Integer  
    If today.First() = "S" Then  
        leisureHours = 16  
    Else  
        leisureHours = 5  
    End If  
  
    ' Because the return statement specifies an operand of type Integer, the   
    ' method must have a return type of Task(Of Integer).   
    Return leisureHours  
End Function  
```  
  
 Quando `TaskOfT_MethodAsync` viene chiamato da un'espressione await, l'espressione recupera il valore intero (valore di `leisureHours`) archiviato nell'attività restituita da `TaskOfT_MethodAsync`. Per altre informazioni sulle espressioni await, vedere [operatore Await](../../../../visual-basic/language-reference/operators/await-operator.md).  
  
 Il codice seguente chiama e attende il metodo `TaskOfT_MethodAsync`. Il risultato viene assegnato alla variabile `result1`.  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 È possibile capire meglio il modo in cui ciò avviene separando la chiamata a `TaskOfT_MethodAsync` dall'applicazione di `Await`, come illustrato dal codice seguente. Una chiamata al metodo `TaskOfT_MethodAsync` che non viene immediatamente attesa restituisce un tipo `Task(Of Integer)`, come ci si aspetterebbe dalla dichiarazione del metodo. Nell'esempio, l'attività viene assegnata alla variabile `integerTask`. Poiché `integerTask` è un <xref:System.Threading.Tasks.Task%601>, contiene una proprietà <xref:System.Threading.Tasks.Task%601.Result> di tipo `TResult`. In questo caso, TResult rappresenta un tipo Integer. Quando si applica `Await` a `integerTask`, l'espressione await restituisce il contenuto della proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> di `integerTask`. Il valore viene assegnato alla variabile `result2`.  
  
> [!WARNING]
>  La proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> è una proprietà di blocco. Se si prova ad accedervi prima del completamento dell'attività, il thread attualmente attivo viene bloccato fino a quando l'attività non viene completata e il valore non è disponibile. Nella maggior parte dei casi, è consigliabile accedere al valore usando `Await` invece di accedere direttamente alla proprietà.  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 Le istruzioni di visualizzazione nel codice seguente verificano che i valori della variabile `result1`, della variabile `result2` e della proprietà `Result` siano identici. Si noti che la proprietà `Result` è una proprietà di blocco e non ci si deve accedere prima che la sua attività sia stata completata.  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
## <a name="BKMK_TaskReturnType"></a> Tipo restituito Task  
 I metodi asincroni che non contengono un'istruzione return o che contengono un'istruzione return che non restituisce un operando hanno in genere il tipo restituito <xref:System.Threading.Tasks.Task>. Tali metodi sarebbero [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure se fossero scritti per l'esecuzione sincrona. Se si usa un tipo restituito `Task` per un metodo asincrono, un metodo chiamante può usare un operatore `Await` per sospendere il completamento del chiamante fino a quando il metodo asincrono chiamato non abbia terminato l'operazione.  
  
 Nell'esempio seguente il metodo asincrono `Task_MethodAsync` non contiene un'istruzione return. Di conseguenza, si specifica un tipo restituito `Task` per il metodo, che consente a `Task_MethodAsync` di essere atteso. La definizione del tipo `Task` non include una proprietà `Result` per archiviare un valore restituito.  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 `Task_MethodAsync` viene chiamato e atteso usando un'istruzione await invece di un'espressione await, simile all'istruzione chiamante per un metodo sincrono `Sub` o che restituisce void. L'applicazione di un `Await` operatore in questo caso non produce alcun valore.  
  
 Il codice seguente chiama e attende il metodo `Task_MethodAsync`.  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 Come nel precedente <xref:System.Threading.Tasks.Task%601> esempio, è possibile separare la chiamata a `Task_MethodAsync` dall'applicazione di un `Await` operatore, come illustrato nel codice seguente. Tuttavia, si noti che un tipo `Task` non ha una proprietà `Result` e che quando viene applicato un operatore await a un tipo `Task` non viene prodotto alcun valore.  
  
 Il codice seguente separa la chiamata di `Task_MethodAsync` dall'attesa dell'attività restituita da `Task_MethodAsync`.  
  
```vb  
' Call and await in separate statements.  
Dim simpleTask As Task = Task_MethodAsync()  
  
' You can do other work that does not rely on simpleTask before awaiting.  
textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
Await simpleTask  
```  
  
## <a name="BKMK_VoidReturnType"></a> Tipo restituito void  
 L'uso primario di `Sub` procedure sia nei gestori eventi, in cui è presente alcun tipo restituito (definito come tipo restituito void in altri linguaggi). Un tipo restituito void può essere usato anche per eseguire l'override di metodi che restituiscono void o per metodi che eseguono attività che possono essere categorizzate come "Fire and Forget". È consigliabile tuttavia restituire un tipo `Task` ogni volta che è possibile, perché un metodo asincrono che restituisce void non può essere atteso. Qualsiasi chiamante di questo metodo deve poter continuare fino al completamento senza attendere il completamento del metodo asincrono chiamato e il chiamante deve essere indipendente da qualsiasi eccezione o valore generato dal metodo asincrono.  
  
 Il chiamante di un metodo asincrono che restituisce void non può intercettare le eccezioni generate dal metodo ed è probabile che queste eccezioni non gestite provochino un errore dell'applicazione. Se si verifica un'eccezione in un metodo asincrono che restituisce <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, l'eccezione viene archiviata nell'attività restituita e rigenerata durante l'attesa dell'attività. Di conseguenza, verificare che qualsiasi metodo asincrono in grado di produrre un'eccezione abbia un tipo restituito <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> e che sia impostata l'attesa per le chiamate al metodo.  
  
 Per altre informazioni su come intercettare eccezioni nei metodi asincroni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Il codice seguente definisce un gestore eventi asincroni.  
  
```vb  
' SUB EXAMPLE  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
    textBox1.Clear()  
  
    ' Start the process and await its completion. DriverAsync is a   
    ' Task-returning async method.  
    Await DriverAsync()  
  
    ' Say goodbye.  
    textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
End Sub  
```  
  
## <a name="BKMK_Example"></a> Esempio completo  
 Il progetto Windows Presentation Foundation (WPF) seguente contiene gli esempi di codice di questo argomento.  
  
 Per eseguire il progetto, effettuare i passaggi seguenti:  
  
1. Avviare Visual Studio.  
  
2. Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.  
  
     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
3. Nel **Installed**, **modelli** categoria, scegliere **Visual Basic**e quindi scegliere **Windows**. Dall'elenco dei tipi di progetto scegliere **Applicazione WPF**.  
  
4. Immettere `AsyncReturnTypes` come nome del progetto e scegliere **OK**.  
  
     Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.  
  
5. Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .  
  
     Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow.xaml in **Esplora soluzioni** e quindi scegliere **Apri**.  
  
6. Nella finestra **XAML** di MainWindow.xaml sostituire il codice con quello seguente.  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
    ```  
  
     Nella finestra di **progettazione**di MainWindow.xaml verrà visualizzata una finestra contenente una casella di testo e un pulsante.  
  
7. Nelle **Esplora soluzioni**, aprire il menu di scelta rapida per XAML. vb e quindi scegliere **Visualizza codice**.  
  
8. Sostituire il codice in MainWindow.xaml.vb con quello riportato di seguito.  
  
    ```vb  
    Class MainWindow  
  
        ' SUB EXAMPLE  
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
            textBox1.Clear()  
  
            ' Start the process and await its completion. DriverAsync is a   
            ' Task-returning async method.  
            Await DriverAsync()  
  
            ' Say goodbye.  
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
        End Sub  
  
        Async Function DriverAsync() As Task  
  
            ' Task(Of T)   
            ' Call and await the Task(Of T)-returning async method in the same statement.  
            Dim result1 As Integer = Await TaskOfT_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
            ' You can do other work that does not rely on resultTask before awaiting.  
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
            Await simpleTask  
        End Function  
  
        ' TASK(OF T) EXAMPLE  
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.FromResult is a placeholder for actual work that returns a string.  
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
            ' The method then can process the result in some way.  
            Dim leisureHours As Integer  
            If today.First() = "S" Then  
                leisureHours = 16  
            Else  
                leisureHours = 5  
            End If  
  
            ' Because the return statement specifies an operand of type Integer, the   
            ' method must have a return type of Task(Of Integer).   
            Return leisureHours  
        End Function  
  
        ' TASK EXAMPLE  
        Async Function Task_MethodAsync() As Task  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.Delay is a placeholder for actual work.  
            Await Task.Delay(2000)  
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
    ```  
  
9. Premere il tasto F5 per eseguire il programma e quindi scegliere il pulsante **Start** .  
  
     Dovrebbe venire visualizzato l'output seguente.  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Procedura dettagliata: Accesso al Web tramite Async e Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Flusso di controllo in programmi asincroni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)
- [Async](../../../../visual-basic/language-reference/modifiers/async.md)
- [Operatore Await](../../../../visual-basic/language-reference/operators/await-operator.md)
