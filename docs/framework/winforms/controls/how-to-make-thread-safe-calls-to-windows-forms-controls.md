---
title: Eseguire chiamate thread-safe a controlli
ms.date: 02/19/2019
description: Informazioni su come implementare il multithreading nell'app chiamando controlli tra thread in modo thread-safe.
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
ms.openlocfilehash: b5f4de7bd3d8d89de98dbe27e2dbf360763670d0
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904182"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Procedura: effettuare chiamate thread-safe a controlli Windows Forms

Il multithreading può migliorare le prestazioni delle app Windows Forms, ma l'accesso ai controlli Windows Forms non è intrinsecamente thread-safe. Il multithreading può esporre il codice a bug molto gravi e complessi. Due o più thread che modificano un controllo possono forzare il controllo in uno stato incoerente e causare race condition, deadlock e blocchi o blocchi. Se si implementa il multithreading nell'app, assicurarsi di chiamare i controlli tra thread in modo thread-safe. Per altre informazioni, vedere [procedure consigliate per il threading gestito](../../../standard/threading/managed-threading-best-practices.md).

Esistono due modi per chiamare in modo sicuro un controllo Windows Forms da un thread che non ha creato il controllo. È possibile usare il <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> metodo per chiamare un delegato creato nel thread principale, che a sua volta chiama il controllo. In alternativa, è possibile implementare un oggetto <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> , che usa un modello basato sugli eventi per separare il lavoro svolto nel thread in background dalla creazione di report sui risultati.

## <a name="unsafe-cross-thread-calls"></a>Chiamate cross-thread non sicure

Non è sicuro chiamare un controllo direttamente da un thread che non lo ha creato. Nel frammento di codice seguente viene illustrata una chiamata unsafe al <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> controllo. Il `Button1_Click` gestore eventi crea un nuovo `WriteTextUnsafe` thread che imposta direttamente la proprietà del thread principale <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> .

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

Il debugger di Visual Studio rileva queste chiamate di thread non sicure generando un oggetto <xref:System.InvalidOperationException> con il messaggio, **operazione cross-thread non valida. Controllo "" a cui è stato eseguito l'accesso da un thread diverso dal thread in cui è stato creato.** Il <xref:System.InvalidOperationException> si verifica sempre per le chiamate cross-thread non sicure durante il debug di Visual Studio e può verificarsi in fase di esecuzione dell'app. È necessario risolvere il problema, ma è possibile disabilitare l'eccezione impostando la <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> proprietà su `false` .

## <a name="safe-cross-thread-calls"></a>Chiamate cross-thread sicure

Gli esempi di codice seguenti illustrano due modi per chiamare in modo sicuro un controllo Windows Forms da un thread che non lo ha creato:

1. Il <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> metodo, che chiama un delegato dal thread principale per chiamare il controllo.
2. <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>Componente, che offre un modello basato sugli eventi.

In entrambi gli esempi, il thread in background dorme per un secondo per simulare il lavoro eseguito in tale thread.

È possibile compilare ed eseguire questi esempi come app .NET Framework dalla riga di comando C# o Visual Basic. Per ulteriori informazioni, vedere compilazione dalla [riga di comando con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) o [compilazione dalla riga di comando (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

A partire da .NET Core 3,0, è anche possibile compilare ed eseguire gli esempi come app di Windows .NET Core da una cartella che contiene un file di progetto .NET Core Windows Forms * \<folder name> . csproj* .

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Esempio: usare il metodo Invoke con un delegato

Nell'esempio seguente viene illustrato un modello per garantire chiamate thread-safe a un controllo Windows Forms. Esegue una query sulla <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> proprietà, che confronta l'ID del thread di creazione del controllo con l'ID del thread chiamante. Se gli ID del thread sono gli stessi, viene chiamato direttamente il controllo. Se gli ID del thread sono diversi, viene chiamato il <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> metodo con un delegato dal thread principale, che effettua la chiamata effettiva al controllo.

`SafeCallDelegate`Consente di impostare la <xref:System.Windows.Forms.TextBox> proprietà del controllo <xref:System.Windows.Forms.TextBox.Text%2A> . Il `WriteTextSafe` metodo esegue una query <xref:System.Windows.Forms.Control.InvokeRequired%2A> . Se <xref:System.Windows.Forms.Control.InvokeRequired%2A> restituisce `true` , `WriteTextSafe` passa al `SafeCallDelegate` <xref:System.Windows.Forms.Control.Invoke%2A> metodo per effettuare la chiamata effettiva al controllo. Se <xref:System.Windows.Forms.Control.InvokeRequired%2A> restituisce `false` , `WriteTextSafe` imposta <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> direttamente il. Il `Button1_Click` gestore eventi crea il nuovo thread ed esegue il `WriteTextSafe` metodo.

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Esempio: usare un gestore eventi BackgroundWorker

Un modo semplice per implementare il multithreading consiste nel <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, che usa un modello basato sugli eventi. Il thread in background esegue l' <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> evento, che non interagisce con il thread principale. Il thread principale esegue i <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> gestori eventi e, che possono chiamare i controlli del thread principale.

Per eseguire una chiamata thread-safe usando <xref:System.ComponentModel.BackgroundWorker> , creare un metodo nel thread in background per eseguire il lavoro e associarlo all' <xref:System.ComponentModel.BackgroundWorker.DoWork> evento. Creare un altro metodo nel thread principale per segnalare i risultati delle operazioni in background e associarlo all' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento o. Per avviare il thread in background, chiamare <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType> .

Nell'esempio viene utilizzato il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore eventi per impostare la <xref:System.Windows.Forms.TextBox> proprietà del controllo <xref:System.Windows.Forms.TextBox.Text%2A> . Per un esempio di utilizzo dell' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, vedere <xref:System.ComponentModel.BackgroundWorker> .

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker>
- [Procedura: eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)
- [Procedura: implementare un form che utilizza un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Sviluppare controlli Windows Forms personalizzati con la .NET Framework](developing-custom-windows-forms-controls.md)
