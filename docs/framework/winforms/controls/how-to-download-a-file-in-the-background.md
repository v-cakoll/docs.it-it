---
title: 'Procedura: Scaricare un file in background'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
ms.openlocfilehash: af5a607b4800635d096e83b55a5bd5a912c8538d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128778"
---
# <a name="how-to-download-a-file-in-the-background"></a>Procedura: Scaricare un file in background
Il download di file è un'attività comune. Spesso è utile eseguire questa operazione potenzialmente dispendiosa in termini di tempo in un thread separato. Usare il componente <xref:System.ComponentModel.BackgroundWorker> per eseguire questa attività con una quantità di codice molto ridotta.   
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come usare un componente <xref:System.ComponentModel.BackgroundWorker> per caricare un file XML da un URL. Quando l'utente fa clic il **scaricare** pulsante, il <xref:System.Windows.Forms.Control.Click> chiamate del gestore eventi il <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> metodo di un <xref:System.ComponentModel.BackgroundWorker> componente per avviare l'operazione di download. Il pulsante è disattivato per la durata del download e quindi abilitato una volta che il download è completato. Un oggetto <xref:System.Windows.Forms.MessageBox> visualizza i contenuti del file.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 **Download del file**  
  
 Il file viene scaricato nel thread di lavoro <xref:System.ComponentModel.BackgroundWorker> del componente, che esegue il gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>. Questo thread inizia nel momento in cui il codice chiama il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 **Attesa della fine di un BackgroundWorker**  
  
 Il gestore eventi `downloadButton_Click` illustra come attendere il completamento di un'attività asincrona da parte di un componente <xref:System.ComponentModel.BackgroundWorker>.  
  
 Se si vuole solo che l'applicazione risponda ad eventi e non si vuole eseguire lavoro nel thread principale durante l'attesa del completamento del thread in background, è sufficiente uscire dal gestore.  
  
 Se si vuole continuare a lavorare nel thread principale, usare la proprietà <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> per determinare se il thread <xref:System.ComponentModel.BackgroundWorker> è ancora in esecuzione. In questo esempio viene aggiornato un indicatore di stato durante l'elaborazione del download. Assicurarsi di chiamare il metodo <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> per mantenere reattiva l'interfaccia utente.   
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 **Visualizzazione del risultato**  
  
 Il metodo `backgroundWorker1_RunWorkerCompleted` gestisce l'evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> e viene chiamato quando l'operazione in background viene completata. Questo metodo verifica prima di tutto la proprietà <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>. Se <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> è `null`, il metodo visualizza il contenuto del file, quindi abilita il pulsante di download, disabilitato all'inizio del download, e reimposta l'indicatore di stato.  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System.Drawing, System.Windows.Forms e System.Xml.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Verificare sempre la presenza della proprietà <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> nel gestore eventi <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> prima di tentare di accedere alla proprietà <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> o ad eventuali altri oggetti che possano essere influenzati dal gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker>
- [Procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)
- [Procedura: Implementare un modulo che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)
