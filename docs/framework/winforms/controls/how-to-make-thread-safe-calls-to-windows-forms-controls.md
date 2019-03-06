---
title: 'Procedura: Effettuare chiamate thread-safe a controlli Windows Form'
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
ms.openlocfilehash: ef7836721df6c090a4d09c38c176641331c3e8a4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362565"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a>Procedura: Effettuare chiamate thread-safe a controlli Windows Form

Il multithreading può migliorare le prestazioni delle app di Windows Form, ma l'accesso ai controlli Windows Form non è intrinsecamente thread-safe. Il multithreading può esporre il codice a bug seri e complessi. Due o più thread, la modifica di un controllo può forzare il controllo in uno stato incoerente e causare condizioni di competizione, deadlock e si blocca o si blocca. Se si implementa il multithreading nell'app, assicurarsi di chiamare i controlli di cross-thread in modo thread-safe. Per altre informazioni, vedere [procedure consigliate di threading gestito](../../../../docs/standard/threading/managed-threading-best-practices.md). 

Esistono due modi per chiamare in modo sicuro un controllo Windows Form da un thread che non sono stati creati tale controllo. È possibile usare il <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> metodo da chiamare un delegato creato nel thread principale, che a sua volta chiama il controllo. In alternativa, è possibile implementare un <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, che usa un modello basato su eventi per separare attività nel thread in background dal servizio di report sui risultati. 

## <a name="unsafe-cross-thread-calls"></a>Chiamate cross-thread non sicure

Non è sicuro chiamare un controllo direttamente da un thread che non è stato creato. Il frammento di codice seguente viene illustrata una chiamata non sicura per la <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> controllo. Il `Button1_Click` crea un nuovo gestore eventi `WriteTextUnsafe` thread, che imposta il thread principale <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> proprietà direttamente. 

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

Il debugger di Visual Studio rileva queste chiamate di thread non sicuro mediante la generazione di un' <xref:System.InvalidOperationException> con il messaggio, **operazione Cross-thread non è valido. Controllo "" accedere da un thread diverso da quello in cui è stato creato.** Il <xref:System.InvalidOperationException> sempre si verifica per chiamate cross-thread non sicure durante il debug di Visual Studio e possono verificarsi in fase di esecuzione di app. È consigliabile risolvere il problema, ma è possibile disabilitare l'eccezione impostando il <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> proprietà `false`.

## <a name="safe-cross-thread-calls"></a>Chiamate cross-thread-safe 

Gli esempi di codice seguenti illustrano due modi per chiamare in modo sicuro un controllo Windows Form da un thread che non è stato creato: 
1. Il <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> metodo, che chiama un delegato dal thread principale per chiamare il controllo. 
2. Oggetto <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, che offre un modello basato sugli eventi. 

In entrambi gli esempi, la disattiva di thread in background per un secondo simulare di lavoro viene eseguita in tale thread. 

È possibile compilare ed eseguire questi esempi di come le app .NET Framework dal C# o riga di comando di Visual Basic. Per altre informazioni, vedere [della riga di comando edificio con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oppure [compilazione dalla riga di comando (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md). 

A partire da .NET Core 3.0, è possibile anche creare ed eseguire gli esempi come le app .NET Core di Windows da una cartella che dispone di un form di Windows di .NET Core  *\<nome cartella > csproj* file di progetto. 

## <a name="example-use-the-invoke-method-with-a-delegate"></a>Esempio: Usare il metodo Invoke con un delegato

Nell'esempio seguente illustra un modello per garantire chiamate thread-safe a un controllo Windows Form. Viene eseguita una query di <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> proprietà, che confronta il controllo della creazione di ID del thread per l'ID del thread chiamante. Se gli ID di thread sono uguali, viene chiamato direttamente il controllo. Se l'ID del thread sono diversi, chiama il <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> metodo con un delegato dal thread principale, che semplifica la chiamata effettiva al controllo.

Il `SafeCallDelegate` attiva un'impostazione di <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.TextBox.Text%2A> proprietà. Il `WriteTextSafe` query di metodo <xref:System.Windows.Forms.Control.InvokeRequired%2A>. Se <xref:System.Windows.Forms.Control.InvokeRequired%2A> restituisce `true`, `WriteTextSafe` passa il `SafeCallDelegate` per il <xref:System.Windows.Forms.Control.Invoke%2A> metodo per eseguire la chiamata effettiva al controllo. Se <xref:System.Windows.Forms.Control.InvokeRequired%2A> restituisce `false`, `WriteTextSafe` imposta la <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> direttamente. Il `Button1_Click` gestore dell'evento viene creato il nuovo thread e viene eseguito il `WriteTextSafe` (metodo). 

 [!code-csharp[ThreadSafeCalls#1](../../../../samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](../../../../samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a>Esempio: Usare un gestore dell'evento BackgroundWorker

Un modo semplice per implementare il multithreading è con il <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> componente, che usa un modello basato su eventi. Il thread in background viene eseguito il <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> evento, che non interagisce con il thread principale. Il thread principale viene eseguito il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> e <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> gestori eventi, che è possono chiamare i controlli del thread principale.

Per effettuare una chiamata thread-safe utilizzando <xref:System.ComponentModel.BackgroundWorker>, creare un metodo nel thread in background per svolgere il lavoro e associarlo al <xref:System.ComponentModel.BackgroundWorker.DoWork> evento. Creare un altro metodo nel thread principale per riportare i risultati delle attività in background e associarlo al <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> o <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> evento. Per avviare il thread in background, chiamare <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>. 

L'esempio Usa la <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore dell'evento per impostare il <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.TextBox.Text%2A> proprietà. Per indicazioni su come usare il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi, vedere <xref:System.ComponentModel.BackgroundWorker>. 

 [!code-csharp[ThreadSafeCalls#2](../../../../samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](../../../../samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker>
- [Procedura: Eseguire un'operazione in background](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Procedura: Implementare un form che usa un'operazione in background](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [Sviluppare controlli Windows Form personalizzati con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
