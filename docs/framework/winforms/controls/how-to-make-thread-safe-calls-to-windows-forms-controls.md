---
title: Effettuare chiamate thread-safe ai controlli
ms.date: 02/19/2019
dev_langs:
- csharp
- vb
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
ms.openlocfilehash: 365b1acb693b9ff2be603a3e659ed8d846a7696a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142004"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Procedura: effettuare chiamate thread-safe ai controlli Windows FormHow to: Make thread-safe calls to Windows Forms controls

Il multithreading può migliorare le prestazioni delle app Windows Form, ma l'accesso ai controlli Windows Form non è intrinsecamente thread-safe. Il multithreading può esporre il codice a bug molto gravi e complessi. Due o più thread che modificano un controllo possono forzare il controllo in uno stato incoerente e portare a race condition, deadlock e blocchi o blocchi. Se implementi il multithreading nella tua app, assicurati di chiamare i controlli cross-thread in modo thread-safe. Per ulteriori informazioni, vedere Procedure consigliate per il [threading gestito](../../../standard/threading/managed-threading-best-practices.md).

Esistono due modi per chiamare in modo sicuro un controllo Windows Form da un thread che non ha creato tale controllo. È possibile <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> utilizzare il metodo per chiamare un delegato creato nel thread principale, che a sua volta chiama il controllo. In alternativa, è <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>possibile implementare un oggetto , che utilizza un modello basato su eventi per separare il lavoro eseguito nel thread in background dal reporting dei risultati.

## <a name="unsafe-cross-thread-calls"></a>Chiamate cross-thread non sicureUnsafe cross-thread calls

Non è sicuro chiamare un controllo direttamente da un thread che non lo ha creato. Il frammento di codice seguente illustra <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> una chiamata unsafe al controllo. Il `Button1_Click` gestore eventi `WriteTextUnsafe` crea un nuovo thread, <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> che imposta direttamente la proprietà del thread principale.

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    thread2 = new Thread(new ThreadStart(WriteTextUnsafe));
    thread2.Start();
}
private void WriteTextUnsafe()
{
    textBox1.Text = "This text was set unsafely.";
}
```

```vb
Private Sub Button1_Click(ByVal sender As Object, e As EventArgs) Handles Button1.Click
    Thread2 = New Thread(New ThreadStart(AddressOf WriteTextUnsafe))
    Thread2.Start()
End Sub

Private Sub WriteTextUnsafe()
    TextBox1.Text = "This text was set unsafely."
End Sub
```

Il debugger di Visual Studio rileva queste <xref:System.InvalidOperationException> chiamate thread non sicure generando un messaggio, **operazione cross-thread non valida. Controllo "" a cui si accede da un thread diverso dal thread in cui è stato creato.** Il <xref:System.InvalidOperationException> si verifica sempre per le chiamate cross-thread non sicure durante il debug di Visual Studio e può verificarsi in fase di esecuzione dell'app. È necessario risolvere il problema, ma è <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> possibile `false`disabilitare l'eccezione impostando la proprietà su .

## <a name="safe-cross-thread-calls"></a>Chiamate cross-thread sicure

Negli esempi di codice seguenti vengono illustrati due modi per chiamare in modo sicuro un controllo Windows Form da un thread che non lo ha creato:The following code examples demonstrate two ways to safely call a Windows Forms control from a thread that didn't create it:

1. Il <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> metodo , che chiama un delegato dal thread principale per chiamare il controllo.
2. Componente, <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> che offre un modello basato su eventi.

In entrambi gli esempi, il thread in background viene inattivo per un secondo per simulare il lavoro in corso in tale thread.

È possibile compilare ed eseguire questi esempi come app .NET Framework dalla riga di comando di C o Visual Basic. Per ulteriori informazioni, vedere [Compilazione da riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [Compilazione dalla riga di comando (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

A partire da .NET Core 3.0, è anche possibile compilare ed eseguire gli esempi come app Windows .NET Core da una cartella con un nome di * \<cartella* Windows Form .NET Core> file di progetto csproj.

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Esempio: utilizzare il metodo Invoke con un delegatoExample: Use the Invoke method with a delegate

Nell'esempio seguente viene illustrato un modello per garantire chiamate thread-safe a un controllo Windows Form.The following example demonstrates a pattern for ensuring thread-safe calls to a Windows Forms control. Esegue una <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> query sulla proprietà , che confronta l'ID del thread di creazione del controllo con l'ID del thread chiamante. Se gli ID del thread sono uguali, chiama direttamente il controllo. Se gli ID del thread sono <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> diversi, chiama il metodo con un delegato dal thread principale, che effettua la chiamata effettiva al controllo.

Consente `SafeCallDelegate` di <xref:System.Windows.Forms.TextBox> impostare <xref:System.Windows.Forms.TextBox.Text%2A> la proprietà del controllo. Il `WriteTextSafe` metodo <xref:System.Windows.Forms.Control.InvokeRequired%2A>esegue una query su . Se <xref:System.Windows.Forms.Control.InvokeRequired%2A> `true`restituisce `WriteTextSafe` `SafeCallDelegate` , <xref:System.Windows.Forms.Control.Invoke%2A> passa l'oggetto al metodo per effettuare la chiamata effettiva al controllo. Se <xref:System.Windows.Forms.Control.InvokeRequired%2A> `false`restituisce `WriteTextSafe` <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> , imposta direttamente l'oggetto . Il `Button1_Click` gestore eventi crea il `WriteTextSafe` nuovo thread ed esegue il metodo .

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Esempio: usare un gestore eventi BackgroundWorkerExample: Use a BackgroundWorker event handler

Un modo semplice per implementare <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> il multithreading è con il componente, che utilizza un modello basato su eventi. Il thread in <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> background esegue l'evento, che non interagisce con il thread principale. Il thread principale <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> esegue i gestori eventi e , che possono chiamare i controlli del thread principale.

Per effettuare una chiamata <xref:System.ComponentModel.BackgroundWorker>thread-safe utilizzando , creare un metodo nel thread <xref:System.ComponentModel.BackgroundWorker.DoWork> in background per eseguire il lavoro e associarlo all'evento. Creare un altro metodo nel thread principale per segnalare i <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> risultati <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> del lavoro in background e associarlo all'evento o . Per avviare il <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>thread in background, chiamare .

Nell'esempio <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> viene utilizzato il <xref:System.Windows.Forms.TextBox> gestore <xref:System.Windows.Forms.TextBox.Text%2A> eventi per impostare la proprietà del controllo. Per un esempio <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> di <xref:System.ComponentModel.BackgroundWorker>utilizzo dell'evento, vedere .

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker>
- [Procedura: eseguire un'operazione in backgroundHow to: Run an operation in the background](how-to-run-an-operation-in-the-background.md)
- [Procedura: Implementare un modulo che utilizza un'operazione in backgroundHow to: Implement a form that uses a background operation](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Sviluppare controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
