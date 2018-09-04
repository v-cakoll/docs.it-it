---
title: 'Procedura: effettuare chiamate thread-safe a controlli di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: f2716db441380138e6058ec45d9ae9c07f0e21a7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43534487"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Procedura: effettuare chiamate thread-safe a controlli di Windows Form

Se si usa il multithreading per migliorare le prestazioni delle applicazioni Windows Forms, è necessario assicurarsi che sia possibile effettuare chiamate ai controlli in modo thread-safe.

L'accesso ai controlli Windows Form non è intrinsecamente thread-safe. Se si hanno due o più thread che gestiscono lo stato di un controllo, è possibile forzare il controllo in uno stato incoerente. Altri bug relativi ai thread sono possibili, ad esempio race condition e deadlock. È importante assicurarsi che l'accesso ai controlli venga eseguito in modo thread-safe.

Non è sicuro chiamare un controllo da un thread diverso da quello che ha creato il controllo senza usare il metodo <xref:System.Windows.Forms.Control.Invoke%2A> . Di seguito è riportato un esempio di una chiamata non thread-safe.

```csharp
// This event handler creates a thread that calls a
// Windows Forms control in an unsafe way.
private void setTextUnsafeBtn_Click(
    object sender,
    EventArgs e)
{
    this.demoThread =
        new Thread(new ThreadStart(this.ThreadProcUnsafe));

    this.demoThread.Start();
}

// This method is executed on the worker thread and makes
// an unsafe call on the TextBox control.
private void ThreadProcUnsafe()
{
    this.textBox1.Text = "This text was set unsafely.";
}
```

```vb
' This event handler creates a thread that calls a
' Windows Forms control in an unsafe way.
 Private Sub setTextUnsafeBtn_Click( _
 ByVal sender As Object, _
 ByVal e As EventArgs) Handles setTextUnsafeBtn.Click

     Me.demoThread = New Thread( _
     New ThreadStart(AddressOf Me.ThreadProcUnsafe))

     Me.demoThread.Start()
 End Sub

' This method is executed on the worker thread and makes
' an unsafe call on the TextBox control.
Private Sub ThreadProcUnsafe()
   Me.textBox1.Text = "This text was set unsafely."
End Sub
```

```cpp
// This event handler creates a thread that calls a
    // Windows Forms control in an unsafe way.
private:
    void setTextUnsafeBtn_Click(Object^ sender, EventArgs^ e)
    {
        this->demoThread =
            gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcUnsafe));

        this->demoThread->Start();
    }

    // This method is executed on the worker thread and makes
    // an unsafe call on the TextBox control.
private:
    void ThreadProcUnsafe()
    {
        this->textBox1->Text = "This text was set unsafely.";
    }
```

[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] consente di rilevare l'accesso ai controlli in modo non thread-safe. Quando si esegue l'applicazione nel debugger e un thread diverso da quello che ha creato un controllo prova a chiamare il controllo, il debugger genera un' eccezione <xref:System.InvalidOperationException> con il messaggio "È stato eseguito l'accesso al controllo *nome controllo* da un thread diverso da quello da cui è stata eseguita la creazione".

Questa eccezione si verifica in modo affidabile durante il debug e, in alcune circostanze, in fase di esecuzione. Questa eccezione potrebbe verificarsi quando si esegue il debug di applicazioni scritte con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] prima di [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. È consigliabile risolvere questo problema non appena si presenta, ma è possibile prevenirlo impostando la proprietà <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A> su `false`. In questo modo il controllo viene eseguito come in Visual Studio .NET 2003 e [!INCLUDE[net_v11_short](../../../../includes/net-v11-short-md.md)].

> [!NOTE]
> Se si usano controlli ActiveX in un form, è possibile che venga visualizzato il <xref:System.InvalidOperationException> cross-thread quando si esegue il debugger. In questo caso, il controllo ActiveX non supporta operazioni multithread. Per altre informazioni sull'uso dei controlli ActiveX con Windows Form, vedere [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md).

## <a name="making-thread-safe-calls-to-windows-forms-controls"></a>Effettuare chiamate thread-safe a controlli di Windows Form

### <a name="to-make-a-thread-safe-call-to-a-windows-forms-control"></a>Per effettuare chiamate thread-safe a un controllo di Windows Form

1.  Eseguire una query sulla proprietà <xref:System.Windows.Forms.Control.InvokeRequired%2A> del controllo.

2.  Se <xref:System.Windows.Forms.Control.InvokeRequired%2A> restituisce `true`, chiamare <xref:System.Windows.Forms.Control.Invoke%2A> con un delegato che effettui la chiamata effettiva al controllo.

3.  Se <xref:System.Windows.Forms.Control.InvokeRequired%2A> restituisce `false`, chiamare direttamente il controllo.

Nell'esempio di codice seguente, una chiamata thread-safe è implementata nel metodo `ThreadProcSafe` , che viene eseguito dal thread in background. Se la proprietà <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.Control.InvokeRequired%2A> restituisce `true`, il metodo `ThreadProcSafe` crea un'istanza di `StringArgReturningVoidDelegate` e la passa al metodo <xref:System.Windows.Forms.Control.Invoke%2A> del form. In questo modo la chiamata al metodo `SetText` viene eseguita sul thread che ha creato il controllo <xref:System.Windows.Forms.TextBox> e la proprietà <xref:System.Windows.Forms.Control.Text%2A> viene impostata direttamente in questo contesto di thread.

```csharp
// This event handler creates a thread that calls a
// Windows Forms control in a thread-safe way.
private void setTextSafeBtn_Click(
    object sender,
    EventArgs e)
{
    this.demoThread =
        new Thread(new ThreadStart(this.ThreadProcSafe));

    this.demoThread.Start();
}

// This method is executed on the worker thread and makes
// a thread-safe call on the TextBox control.
private void ThreadProcSafe()
{
    this.SetText("This text was set safely.");
}
```

```vb
' This event handler creates a thread that calls a
' Windows Forms control in a thread-safe way.
 Private Sub setTextSafeBtn_Click( _
 ByVal sender As Object, _
 ByVal e As EventArgs) Handles setTextSafeBtn.Click

     Me.demoThread = New Thread( _
     New ThreadStart(AddressOf Me.ThreadProcSafe))

     Me.demoThread.Start()
 End Sub

' This method is executed on the worker thread and makes
' a thread-safe call on the TextBox control.
Private Sub ThreadProcSafe()
   Me.SetText("This text was set safely.")
 End Sub
```

```cpp
// This event handler creates a thread that calls a
    // Windows Forms control in a thread-safe way.
private:
    void setTextSafeBtn_Click(Object^ sender, EventArgs^ e)
    {
        this->demoThread =
            gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcSafe));

        this->demoThread->Start();
    }

    // This method is executed on the worker thread and makes
    // a thread-safe call on the TextBox control.
private:
    void ThreadProcSafe()
    {
        this->SetText("This text was set safely.");
    }
```

```csharp
// This delegate enables asynchronous calls for setting
// the text property on a TextBox control.
delegate void StringArgReturningVoidDelegate(string text);
```

```vb
' This delegate enables asynchronous calls for setting
' the text property on a TextBox control.
Delegate Sub StringArgReturningVoidDelegate([text] As String)
```

```cpp
// This delegate enables asynchronous calls for setting
// the text property on a TextBox control.
delegate void StringArgReturningVoidDelegate(String^ text);
```

```csharp
// This method demonstrates a pattern for making thread-safe
// calls on a Windows Forms control.
//
// If the calling thread is different from the thread that
// created the TextBox control, this method creates a
// StringArgReturningVoidDelegate and calls itself asynchronously using the
// Invoke method.
//
// If the calling thread is the same as the thread that created
// the TextBox control, the Text property is set directly.

private void SetText(string text)
{
    // InvokeRequired required compares the thread ID of the
    // calling thread to the thread ID of the creating thread.
    // If these threads are different, it returns true.
    if (this.textBox1.InvokeRequired)
    {
        StringArgReturningVoidDelegate d = new StringArgReturningVoidDelegate(SetText);
        this.Invoke(d, new object[] { text });
    }
    else
    {
        this.textBox1.Text = text;
    }
}
```

```vb
' This method demonstrates a pattern for making thread-safe
' calls on a Windows Forms control.
'
' If the calling thread is different from the thread that
' created the TextBox control, this method creates a
' StringArgReturningVoidDelegate and calls itself asynchronously using the
' Invoke method.
'
' If the calling thread is the same as the thread that created
 ' the TextBox control, the Text property is set directly.

 Private Sub SetText(ByVal [text] As String)

     ' InvokeRequired required compares the thread ID of the
     ' calling thread to the thread ID of the creating thread.
     ' If these threads are different, it returns true.
     If Me.textBox1.InvokeRequired Then
         Dim d As New StringArgReturningVoidDelegate(AddressOf SetText)
         Me.Invoke(d, New Object() {[text]})
     Else
         Me.textBox1.Text = [text]
     End If
 End Sub
```

```cpp
// This method demonstrates a pattern for making thread-safe
    // calls on a Windows Forms control.
    //
    // If the calling thread is different from the thread that
    // created the TextBox control, this method creates a
    // StringArgReturningVoidDelegate and calls itself asynchronously using the
    // Invoke method.
    //
    // If the calling thread is the same as the thread that created
    // the TextBox control, the Text property is set directly.

private:
    void SetText(String^ text)
    {
        // InvokeRequired required compares the thread ID of the
        // calling thread to the thread ID of the creating thread.
        // If these threads are different, it returns true.
        if (this->textBox1->InvokeRequired)
        {
            StringArgReturningVoidDelegate^ d =
                gcnew StringArgReturningVoidDelegate(this, &Form1::SetText);
            this->Invoke(d, gcnew array<Object^> { text });
        }
        else
        {
            this->textBox1->Text = text;
        }
    }
```

## <a name="making-thread-safe-calls-by-using-backgroundworker"></a>Chiamate Thread-Safe con BackgroundWorker
 Il metodo migliore per implementare il multithreading nell'applicazione è usare il componente <xref:System.ComponentModel.BackgroundWorker> , Il componente <xref:System.ComponentModel.BackgroundWorker> usa un modello basato sugli eventi per il multithreading. Il thread in background esegue il gestore dell'evento <xref:System.ComponentModel.BackgroundWorker.DoWork> e il thread che crea i controlli esegue i gestori degli eventi <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> e <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> . È possibile chiamare i controlli dai gestore degli eventi <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> e <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> .

#### <a name="to-make-thread-safe-calls-by-using-backgroundworker"></a>Per effettuare chiamate thread-safe con BackgroundWorker

1.  Creare un metodo che esegua le operazioni desiderate nel thread in background. Non chiamare controlli creati dal thread principale in questo metodo.

2.  Creare un metodo che riporti i risultati delle operazioni in background dopo il loro completamento. È possibile chiamare controlli creati dal thread principale in questo metodo.

3.  Associare il metodo creato nel passaggio 1 all'evento <xref:System.ComponentModel.BackgroundWorker.DoWork> di un'istanza di <xref:System.ComponentModel.BackgroundWorker>e associare il metodo creato nel passaggio 2 all'evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> della stessa istanza.

4.  Per avviare il thread in background, chiamare il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> dell'istanza <xref:System.ComponentModel.BackgroundWorker> .

Nell'esempio di codice seguente, il gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> usa <xref:System.Threading.Thread.Sleep%2A> per simulare operazioni che richiedono un certo tempo. Non chiama il controllo <xref:System.Windows.Forms.TextBox> del form. La proprietà <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.Control.Text%2A> viene impostata direttamente nel gestore dell'evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> .

```csharp
// This BackgroundWorker is used to demonstrate the
// preferred way of performing asynchronous operations.
private BackgroundWorker backgroundWorker1;
```

```vb
' This BackgroundWorker is used to demonstrate the
' preferred way of performing asynchronous operations.
Private WithEvents backgroundWorker1 As BackgroundWorker
```

```cpp
// This BackgroundWorker is used to demonstrate the
    // preferred way of performing asynchronous operations.
private:
    BackgroundWorker^ backgroundWorker1;
```

```csharp
// This event handler starts the form's
// BackgroundWorker by calling RunWorkerAsync.
//
// The Text property of the TextBox control is set
// when the BackgroundWorker raises the RunWorkerCompleted
// event.
private void setTextBackgroundWorkerBtn_Click(
    object sender,
    EventArgs e)
{
    this.backgroundWorker1.RunWorkerAsync();
}

// This event handler sets the Text property of the TextBox
// control. It is called on the thread that created the
// TextBox control, so the call is thread-safe.
//
// BackgroundWorker is the preferred way to perform asynchronous
// operations.

private void backgroundWorker1_RunWorkerCompleted(
    object sender,
    RunWorkerCompletedEventArgs e)
{
    this.textBox1.Text =
        "This text was set safely by BackgroundWorker.";
}
```

```vb
' This event handler starts the form's
' BackgroundWorker by calling RunWorkerAsync.
'
' The Text property of the TextBox control is set
' when the BackgroundWorker raises the RunWorkerCompleted
' event.
 Private Sub setTextBackgroundWorkerBtn_Click( _
 ByVal sender As Object, _
 ByVal e As EventArgs) Handles setTextBackgroundWorkerBtn.Click
     Me.backgroundWorker1.RunWorkerAsync()
 End Sub

' This event handler sets the Text property of the TextBox
' control. It is called on the thread that created the
' TextBox control, so the call is thread-safe.
'
' BackgroundWorker is the preferred way to perform asynchronous
' operations.
 Private Sub backgroundWorker1_RunWorkerCompleted( _
 ByVal sender As Object, _
 ByVal e As RunWorkerCompletedEventArgs) _
 Handles backgroundWorker1.RunWorkerCompleted
     Me.textBox1.Text = _
     "This text was set safely by BackgroundWorker."
 End Sub
```

```cpp
// This event handler starts the form's
    // BackgroundWorker by calling RunWorkerAsync.
    //
    // The Text property of the TextBox control is set
    // when the BackgroundWorker raises the RunWorkerCompleted
    // event.
private:
    void setTextBackgroundWorkerBtn_Click(Object^ sender, EventArgs^ e)
    {
        this->backgroundWorker1->RunWorkerAsync();
    }

    // This event handler sets the Text property of the TextBox
    // control. It is called on the thread that created the
    // TextBox control, so the call is thread-safe.
    //
    // BackgroundWorker is the preferred way to perform asynchronous
    // operations.

private:
    void backgroundWorker1_RunWorkerCompleted(
        Object^ sender,
        RunWorkerCompletedEventArgs^ e)
    {
        this->textBox1->Text =
            "This text was set safely by BackgroundWorker.";
    }
```

 È possibile segnalare anche lo stato di avanzamento di un'attività in background con l'evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> . Per un esempio che incorpori questo evento, vedere <xref:System.ComponentModel.BackgroundWorker>.

## <a name="example"></a>Esempio
 L'esempio di codice seguente è un'applicazione Windows Form completa, costituita da un form con tre pulsanti e una casella di testo. Il primo pulsante dimostra un accesso cross-thread non sicuro, il secondo pulsante dimostra un accesso sicuro con <xref:System.Windows.Forms.Control.Invoke%2A>e il terzo pulsante dimostra un accesso sicuro con <xref:System.ComponentModel.BackgroundWorker>.

> [!NOTE]
> Per istruzioni su come eseguire l'esempio, vedere [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/cc447f7e-4c3b-4397-9d05-aeba3ca49416). Questo esempio richiede riferimenti agli assembly System.Drawing e System.Windows.Forms.

```csharp
using System;
using System.ComponentModel;
using System.Threading;
using System.Windows.Forms;

namespace CrossThreadDemo
{
    public class Form1 : Form
    {
        // This delegate enables asynchronous calls for setting
        // the text property on a TextBox control.
        delegate void StringArgReturningVoidDelegate(string text);

        // This thread is used to demonstrate both thread-safe and
        // unsafe ways to call a Windows Forms control.
        private Thread demoThread = null;

        // This BackgroundWorker is used to demonstrate the
        // preferred way of performing asynchronous operations.
        private BackgroundWorker backgroundWorker1;

        private TextBox textBox1;
        private Button setTextUnsafeBtn;
        private Button setTextSafeBtn;
        private Button setTextBackgroundWorkerBtn;

        private System.ComponentModel.IContainer components = null;

        public Form1()
        {
            InitializeComponent();
        }

        protected override void Dispose(bool disposing)
        {
            if (disposing && (components != null))
            {
                components.Dispose();
            }
            base.Dispose(disposing);
        }

        // This event handler creates a thread that calls a
        // Windows Forms control in an unsafe way.
        private void setTextUnsafeBtn_Click(
            object sender,
            EventArgs e)
        {
            this.demoThread =
                new Thread(new ThreadStart(this.ThreadProcUnsafe));

            this.demoThread.Start();
        }

        // This method is executed on the worker thread and makes
        // an unsafe call on the TextBox control.
        private void ThreadProcUnsafe()
        {
            this.textBox1.Text = "This text was set unsafely.";
        }

        // This event handler creates a thread that calls a
        // Windows Forms control in a thread-safe way.
        private void setTextSafeBtn_Click(
            object sender,
            EventArgs e)
        {
            this.demoThread =
                new Thread(new ThreadStart(this.ThreadProcSafe));

            this.demoThread.Start();
        }

        // This method is executed on the worker thread and makes
        // a thread-safe call on the TextBox control.
        private void ThreadProcSafe()
        {
            this.SetText("This text was set safely.");
        }

        // This method demonstrates a pattern for making thread-safe
        // calls on a Windows Forms control.
        //
        // If the calling thread is different from the thread that
        // created the TextBox control, this method creates a
        // StringArgReturningVoidDelegate and calls itself asynchronously using the
        // Invoke method.
        //
        // If the calling thread is the same as the thread that created
        // the TextBox control, the Text property is set directly.

        private void SetText(string text)
        {
            // InvokeRequired required compares the thread ID of the
            // calling thread to the thread ID of the creating thread.
            // If these threads are different, it returns true.
            if (this.textBox1.InvokeRequired)
            {
                StringArgReturningVoidDelegate d = new StringArgReturningVoidDelegate(SetText);
                this.Invoke(d, new object[] { text });
            }
            else
            {
                this.textBox1.Text = text;
            }
        }

        // This event handler starts the form's
        // BackgroundWorker by calling RunWorkerAsync.
        //
        // The Text property of the TextBox control is set
        // when the BackgroundWorker raises the RunWorkerCompleted
        // event.
        private void setTextBackgroundWorkerBtn_Click(
            object sender,
            EventArgs e)
        {
            this.backgroundWorker1.RunWorkerAsync();
        }

        // This event handler sets the Text property of the TextBox
        // control. It is called on the thread that created the
        // TextBox control, so the call is thread-safe.
        //
        // BackgroundWorker is the preferred way to perform asynchronous
        // operations.

        private void backgroundWorker1_RunWorkerCompleted(
            object sender,
            RunWorkerCompletedEventArgs e)
        {
            this.textBox1.Text =
                "This text was set safely by BackgroundWorker.";
        }

        #region Windows Form Designer generated code

        private void InitializeComponent()
        {
            this.textBox1 = new System.Windows.Forms.TextBox();
            this.setTextUnsafeBtn = new System.Windows.Forms.Button();
            this.setTextSafeBtn = new System.Windows.Forms.Button();
            this.setTextBackgroundWorkerBtn = new System.Windows.Forms.Button();
            this.backgroundWorker1 = new System.ComponentModel.BackgroundWorker();
            this.SuspendLayout();
            //
            // textBox1
            //
            this.textBox1.Location = new System.Drawing.Point(12, 12);
            this.textBox1.Name = "textBox1";
            this.textBox1.Size = new System.Drawing.Size(240, 20);
            this.textBox1.TabIndex = 0;
            //
            // setTextUnsafeBtn
            //
            this.setTextUnsafeBtn.Location = new System.Drawing.Point(15, 55);
            this.setTextUnsafeBtn.Name = "setTextUnsafeBtn";
            this.setTextUnsafeBtn.TabIndex = 1;
            this.setTextUnsafeBtn.Text = "Unsafe Call";
            this.setTextUnsafeBtn.Click += new System.EventHandler(this.setTextUnsafeBtn_Click);
            //
            // setTextSafeBtn
            //
            this.setTextSafeBtn.Location = new System.Drawing.Point(96, 55);
            this.setTextSafeBtn.Name = "setTextSafeBtn";
            this.setTextSafeBtn.TabIndex = 2;
            this.setTextSafeBtn.Text = "Safe Call";
            this.setTextSafeBtn.Click += new System.EventHandler(this.setTextSafeBtn_Click);
            //
            // setTextBackgroundWorkerBtn
            //
            this.setTextBackgroundWorkerBtn.Location = new System.Drawing.Point(177, 55);
            this.setTextBackgroundWorkerBtn.Name = "setTextBackgroundWorkerBtn";
            this.setTextBackgroundWorkerBtn.TabIndex = 3;
            this.setTextBackgroundWorkerBtn.Text = "Safe BW Call";
            this.setTextBackgroundWorkerBtn.Click += new System.EventHandler(this.setTextBackgroundWorkerBtn_Click);
            //
            // backgroundWorker1
            //
            this.backgroundWorker1.RunWorkerCompleted += new System.ComponentModel.RunWorkerCompletedEventHandler(this.backgroundWorker1_RunWorkerCompleted);
            //
            // Form1
            //
            this.ClientSize = new System.Drawing.Size(268, 96);
            this.Controls.Add(this.setTextBackgroundWorkerBtn);
            this.Controls.Add(this.setTextSafeBtn);
            this.Controls.Add(this.setTextUnsafeBtn);
            this.Controls.Add(this.textBox1);
            this.Name = "Form1";
            this.Text = "Form1";
            this.ResumeLayout(false);
            this.PerformLayout();

        }

        #endregion

        [STAThread]
        static void Main()
        {
            Application.EnableVisualStyles();
            Application.Run(new Form1());
        }

    }
}
```

```vb
Imports System
Imports System.ComponentModel
Imports System.Threading
Imports System.Windows.Forms

Public Class Form1
   Inherits Form

   ' This delegate enables asynchronous calls for setting
   ' the text property on a TextBox control.
   Delegate Sub StringArgReturningVoidDelegate([text] As String)

   ' This thread is used to demonstrate both thread-safe and
   ' unsafe ways to call a Windows Forms control.
   Private demoThread As Thread = Nothing

   ' This BackgroundWorker is used to demonstrate the
   ' preferred way of performing asynchronous operations.
   Private WithEvents backgroundWorker1 As BackgroundWorker

   Private textBox1 As TextBox
   Private WithEvents setTextUnsafeBtn As Button
   Private WithEvents setTextSafeBtn As Button
   Private WithEvents setTextBackgroundWorkerBtn As Button

   Private components As System.ComponentModel.IContainer = Nothing

   Public Sub New()
      InitializeComponent()
    End Sub

   Protected Overrides Sub Dispose(disposing As Boolean)
      If disposing AndAlso (components IsNot Nothing) Then
         components.Dispose()
      End If
      MyBase.Dispose(disposing)
    End Sub

   ' This event handler creates a thread that calls a
   ' Windows Forms control in an unsafe way.
    Private Sub setTextUnsafeBtn_Click( _
    ByVal sender As Object, _
    ByVal e As EventArgs) Handles setTextUnsafeBtn.Click

        Me.demoThread = New Thread( _
        New ThreadStart(AddressOf Me.ThreadProcUnsafe))

        Me.demoThread.Start()
    End Sub

   ' This method is executed on the worker thread and makes
   ' an unsafe call on the TextBox control.
   Private Sub ThreadProcUnsafe()
      Me.textBox1.Text = "This text was set unsafely."
   End Sub

   ' This event handler creates a thread that calls a
   ' Windows Forms control in a thread-safe way.
    Private Sub setTextSafeBtn_Click( _
    ByVal sender As Object, _
    ByVal e As EventArgs) Handles setTextSafeBtn.Click

        Me.demoThread = New Thread( _
        New ThreadStart(AddressOf Me.ThreadProcSafe))

        Me.demoThread.Start()
    End Sub

   ' This method is executed on the worker thread and makes
   ' a thread-safe call on the TextBox control.
   Private Sub ThreadProcSafe()
      Me.SetText("This text was set safely.")
    End Sub

   ' This method demonstrates a pattern for making thread-safe
   ' calls on a Windows Forms control.
   '
   ' If the calling thread is different from the thread that
   ' created the TextBox control, this method creates a
   ' StringArgReturningVoidDelegate and calls itself asynchronously using the
   ' Invoke method.
   '
   ' If the calling thread is the same as the thread that created
    ' the TextBox control, the Text property is set directly.

    Private Sub SetText(ByVal [text] As String)

        ' InvokeRequired required compares the thread ID of the
        ' calling thread to the thread ID of the creating thread.
        ' If these threads are different, it returns true.
        If Me.textBox1.InvokeRequired Then
            Dim d As New StringArgReturningVoidDelegate(AddressOf SetText)
            Me.Invoke(d, New Object() {[text]})
        Else
            Me.textBox1.Text = [text]
        End If
    End Sub

   ' This event handler starts the form's
   ' BackgroundWorker by calling RunWorkerAsync.
   '
   ' The Text property of the TextBox control is set
   ' when the BackgroundWorker raises the RunWorkerCompleted
   ' event.
    Private Sub setTextBackgroundWorkerBtn_Click( _
    ByVal sender As Object, _
    ByVal e As EventArgs) Handles setTextBackgroundWorkerBtn.Click
        Me.backgroundWorker1.RunWorkerAsync()
    End Sub

   ' This event handler sets the Text property of the TextBox
   ' control. It is called on the thread that created the
   ' TextBox control, so the call is thread-safe.
   '
   ' BackgroundWorker is the preferred way to perform asynchronous
   ' operations.
    Private Sub backgroundWorker1_RunWorkerCompleted( _
    ByVal sender As Object, _
    ByVal e As RunWorkerCompletedEventArgs) _
    Handles backgroundWorker1.RunWorkerCompleted
        Me.textBox1.Text = _
        "This text was set safely by BackgroundWorker."
    End Sub

   #Region "Windows Form Designer generated code"

   Private Sub InitializeComponent()
      Me.textBox1 = New System.Windows.Forms.TextBox()
      Me.setTextUnsafeBtn = New System.Windows.Forms.Button()
      Me.setTextSafeBtn = New System.Windows.Forms.Button()
      Me.setTextBackgroundWorkerBtn = New System.Windows.Forms.Button()
      Me.backgroundWorker1 = New System.ComponentModel.BackgroundWorker()
      Me.SuspendLayout()
      '
      ' textBox1
      '
      Me.textBox1.Location = New System.Drawing.Point(12, 12)
      Me.textBox1.Name = "textBox1"
      Me.textBox1.Size = New System.Drawing.Size(240, 20)
      Me.textBox1.TabIndex = 0
      '
      ' setTextUnsafeBtn
      '
      Me.setTextUnsafeBtn.Location = New System.Drawing.Point(15, 55)
      Me.setTextUnsafeBtn.Name = "setTextUnsafeBtn"
      Me.setTextUnsafeBtn.TabIndex = 1
      Me.setTextUnsafeBtn.Text = "Unsafe Call"
      '
      ' setTextSafeBtn
      '
      Me.setTextSafeBtn.Location = New System.Drawing.Point(96, 55)
      Me.setTextSafeBtn.Name = "setTextSafeBtn"
      Me.setTextSafeBtn.TabIndex = 2
      Me.setTextSafeBtn.Text = "Safe Call"
      '
      ' setTextBackgroundWorkerBtn
      '
      Me.setTextBackgroundWorkerBtn.Location = New System.Drawing.Point(177, 55)
      Me.setTextBackgroundWorkerBtn.Name = "setTextBackgroundWorkerBtn"
      Me.setTextBackgroundWorkerBtn.TabIndex = 3
      Me.setTextBackgroundWorkerBtn.Text = "Safe BW Call"
      '
      ' backgroundWorker1
      '
      '
      ' Form1
      '
      Me.ClientSize = New System.Drawing.Size(268, 96)
      Me.Controls.Add(setTextBackgroundWorkerBtn)
      Me.Controls.Add(setTextSafeBtn)
      Me.Controls.Add(setTextUnsafeBtn)
      Me.Controls.Add(textBox1)
      Me.Name = "Form1"
      Me.Text = "Form1"
      Me.ResumeLayout(False)
      Me.PerformLayout()
   End Sub 'InitializeComponent

   #End Region

   <STAThread()>  _
   Shared Sub Main()
      Application.EnableVisualStyles()
      Application.Run(New Form1())
    End Sub
End Class
```

```cpp
#using <System.dll>
#using <System.Windows.Forms.dll>
#using <System.Drawing.dll>

using namespace System;
using namespace System::ComponentModel;
using namespace System::Threading;
using namespace System::Windows::Forms;

namespace CrossThreadDemo
{
    public ref class Form1 : public Form
    {
        // This delegate enables asynchronous calls for setting
        // the text property on a TextBox control.
        delegate void StringArgReturningVoidDelegate(String^ text);

        // This thread is used to demonstrate both thread-safe and
        // unsafe ways to call a Windows Forms control.
    private:
        Thread^ demoThread;

        // This BackgroundWorker is used to demonstrate the
        // preferred way of performing asynchronous operations.
    private:
        BackgroundWorker^ backgroundWorker1;

    private:
        TextBox^ textBox1;
    private:
        Button^ setTextUnsafeBtn;
    private:
        Button^ setTextSafeBtn;
    private:
        Button^ setTextBackgroundWorkerBtn;

    private:
        System::ComponentModel::IContainer^ components;

    public:
        Form1()
        {
            components = nullptr;
            InitializeComponent();
        }

    protected:
        ~Form1()
        {
            if (components != nullptr)
            {
                delete components;
            }
        }

        // This event handler creates a thread that calls a
        // Windows Forms control in an unsafe way.
    private:
        void setTextUnsafeBtn_Click(Object^ sender, EventArgs^ e)
        {
            this->demoThread =
                gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcUnsafe));

            this->demoThread->Start();
        }

        // This method is executed on the worker thread and makes
        // an unsafe call on the TextBox control.
    private:
        void ThreadProcUnsafe()
        {
            this->textBox1->Text = "This text was set unsafely.";
        }

        // This event handler creates a thread that calls a
        // Windows Forms control in a thread-safe way.
    private:
        void setTextSafeBtn_Click(Object^ sender, EventArgs^ e)
        {
            this->demoThread =
                gcnew Thread(gcnew ThreadStart(this,&Form1::ThreadProcSafe));

            this->demoThread->Start();
        }

        // This method is executed on the worker thread and makes
        // a thread-safe call on the TextBox control.
    private:
        void ThreadProcSafe()
        {
            this->SetText("This text was set safely.");
        }

        // This method demonstrates a pattern for making thread-safe
        // calls on a Windows Forms control.
        //
        // If the calling thread is different from the thread that
        // created the TextBox control, this method creates a
        // StringArgReturningVoidDelegate and calls itself asynchronously using the
        // Invoke method.
        //
        // If the calling thread is the same as the thread that created
        // the TextBox control, the Text property is set directly.

    private:
        void SetText(String^ text)
        {
            // InvokeRequired required compares the thread ID of the
            // calling thread to the thread ID of the creating thread.
            // If these threads are different, it returns true.
            if (this->textBox1->InvokeRequired)
            {
                StringArgReturningVoidDelegate^ d =
                    gcnew StringArgReturningVoidDelegate(this, &Form1::SetText);
                this->Invoke(d, gcnew array<Object^> { text });
            }
            else
            {
                this->textBox1->Text = text;
            }
        }

        // This event handler starts the form's
        // BackgroundWorker by calling RunWorkerAsync.
        //
        // The Text property of the TextBox control is set
        // when the BackgroundWorker raises the RunWorkerCompleted
        // event.
    private:
        void setTextBackgroundWorkerBtn_Click(Object^ sender, EventArgs^ e)
        {
            this->backgroundWorker1->RunWorkerAsync();
        }

        // This event handler sets the Text property of the TextBox
        // control. It is called on the thread that created the
        // TextBox control, so the call is thread-safe.
        //
        // BackgroundWorker is the preferred way to perform asynchronous
        // operations.

    private:
        void backgroundWorker1_RunWorkerCompleted(
            Object^ sender,
            RunWorkerCompletedEventArgs^ e)
        {
            this->textBox1->Text =
                "This text was set safely by BackgroundWorker.";
        }

        #pragma region Windows Form Designer generated code

    private:
        void InitializeComponent()
        {
            this->textBox1 = gcnew System::Windows::Forms::TextBox();
            this->setTextUnsafeBtn = gcnew System::Windows::Forms::Button();
            this->setTextSafeBtn = gcnew System::Windows::Forms::Button();
            this->setTextBackgroundWorkerBtn =
                gcnew System::Windows::Forms::Button();
            this->backgroundWorker1 =
                gcnew System::ComponentModel::BackgroundWorker();
            this->SuspendLayout();
            //
            // textBox1
            //
            this->textBox1->Location = System::Drawing::Point(12, 12);
            this->textBox1->Name = "textBox1";
            this->textBox1->Size = System::Drawing::Size(240, 20);
            this->textBox1->TabIndex = 0;
            //
            // setTextUnsafeBtn
            //
            this->setTextUnsafeBtn->Location = System::Drawing::Point(15, 55);
            this->setTextUnsafeBtn->Name = "setTextUnsafeBtn";
            this->setTextUnsafeBtn->TabIndex = 1;
            this->setTextUnsafeBtn->Text = "Unsafe Call";
            this->setTextUnsafeBtn->Click +=
                gcnew System::EventHandler(
                this,&Form1::setTextUnsafeBtn_Click);
            //
            // setTextSafeBtn
            //
            this->setTextSafeBtn->Location = System::Drawing::Point(96, 55);
            this->setTextSafeBtn->Name = "setTextSafeBtn";
            this->setTextSafeBtn->TabIndex = 2;
            this->setTextSafeBtn->Text = "Safe Call";
            this->setTextSafeBtn->Click +=
                gcnew System::EventHandler(this,&Form1::setTextSafeBtn_Click);
            //
            // setTextBackgroundWorkerBtn
            //
            this->setTextBackgroundWorkerBtn->Location =
                System::Drawing::Point(177, 55);
            this->setTextBackgroundWorkerBtn->Name =
                "setTextBackgroundWorkerBtn";
            this->setTextBackgroundWorkerBtn->TabIndex = 3;
            this->setTextBackgroundWorkerBtn->Text = "Safe BW Call";
            this->setTextBackgroundWorkerBtn->Click +=
                gcnew System::EventHandler(
                this,&Form1::setTextBackgroundWorkerBtn_Click);
            //
            // backgroundWorker1
            //
            this->backgroundWorker1->RunWorkerCompleted +=
                gcnew System::ComponentModel::RunWorkerCompletedEventHandler(
                this,&Form1::backgroundWorker1_RunWorkerCompleted);
            //
            // Form1
            //
            this->ClientSize = System::Drawing::Size(268, 96);
            this->Controls->Add(this->setTextBackgroundWorkerBtn);
            this->Controls->Add(this->setTextSafeBtn);
            this->Controls->Add(this->setTextUnsafeBtn);
            this->Controls->Add(this->textBox1);
            this->Name = "Form1";
            this->Text = "Form1";
            this->ResumeLayout(false);
            this->PerformLayout();

        }

        #pragma endregion
    };
}

[STAThread]
int main()
{
    Application::EnableVisualStyles();
    Application::Run(gcnew CrossThreadDemo::Form1());
}
```

Quando si esegue l'applicazione e si fa clic sul pulsante **Unsafe Call** , viene immediatamente visualizzato "Written by the main thread" nella casella di testo. Due secondi dopo, quando viene tentata la chiamata non sicura, il debugger di Visual Studio indica che si è verificata un'eccezione. Il debugger si arresta alla riga nel thread in background che ha provato a scrivere direttamente nella casella di testo. Sarà necessario riavviare l'applicazione per testare gli altri due pulsanti. Quando si fa clic sul pulsante **Safe Call** , viene visualizzato "Written by the main thread" nella casella di testo. Due secondi dopo, la casella di testo viene impostata su "Written by the background thread (Invoke)", che indica che è stato chiamato il metodo <xref:System.Windows.Forms.Control.Invoke%2A> . Quando si fa clic sul pulsante **Safe BW Call**, viene visualizzato "Written by the main thread" nella casella di testo. Due secondi dopo, la casella di testo viene impostata su "Written by the main thread after the background thread completed", a indicare che è stato chiamato il gestore per l'evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> di <xref:System.ComponentModel.BackgroundWorker> .

## <a name="robust-programming"></a>Programmazione efficiente

> [!CAUTION]
> Quando si usa qualsiasi tipo di multithreading, è possibile che il codice venga esposto al rischio di bug gravi e complessi. Per altre informazioni, vedere [Procedure consigliate per il threading gestito](../../../../docs/standard/threading/managed-threading-best-practices.md) prima di implementare soluzioni che usano il multithreading.

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker>
- [Procedura: Eseguire un'operazione in background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Procedura: Implementare un form che esegue un'operazione in background](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
- [Windows Form e applicazioni non gestite](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)
