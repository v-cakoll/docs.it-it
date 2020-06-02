---
title: 'Procedura: Annullare un blocco di flussi di dati'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
ms.openlocfilehash: 530c231deeaba007975849ab6dc41f4da6a859ea
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84285547"
---
# <a name="how-to-cancel-a-dataflow-block"></a>Procedura: Annullare un blocco di flussi di dati
In questo documento viene dimostrato come abilitare l'annullamento nell'applicazione. In questo esempio Windows Form viene usato per mostrare dove gli elementi di lavoro sono attivi in una pipeline del flusso di dati, nonché gli effetti dell'annullamento.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="to-create-the-windows-forms-application"></a>Per creare l'applicazione Windows Forms  
  
1. Creare un progetto **Windows Forms Application** di C# o Visual Basic. Nei passaggi seguenti il progetto viene denominato `CancellationWinForms`.  
  
2. Nella finestra di progettazione del form per il form principale, Form1.cs (Form1.vb per Visual Basic), aggiungere un controllo <xref:System.Windows.Forms.ToolStrip>.  
  
3. Aggiungere un controllo <xref:System.Windows.Forms.ToolStripButton> al controllo <xref:System.Windows.Forms.ToolStrip>. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> su <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> e la proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su **Aggiungi elementi di lavoro**.  
  
4. Aggiungere un secondo controllo <xref:System.Windows.Forms.ToolStripButton> al controllo <xref:System.Windows.Forms.ToolStrip>. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> su <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, la proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su **Annulla** e la proprietà <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> su `False`.  
  
5. Aggiungere quattro oggetti <xref:System.Windows.Forms.ToolStripProgressBar> al controllo <xref:System.Windows.Forms.ToolStrip>.  
  
## <a name="creating-the-dataflow-pipeline"></a>Creazione della pipeline del flusso di dati  
 In questa sezione viene descritto come creare la pipeline del flusso di dati che elabora gli elementi di lavoro e aggiorna le barre di stato.  
  
### <a name="to-create-the-dataflow-pipeline"></a>Per creare la pipeline del flusso di dati  
  
1. Nel progetto aggiungere un riferimento a System.Threading.Tasks.Dataflow.dll.  
  
2. Assicurarsi che in Form1.cs (Form1.vb per Visual Basic) siano contenute le seguenti istruzioni `using` (`Imports` in Visual Basic).  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3. Aggiungere la classe `WorkItem` come un tipo interno della classe `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4. Aggiungere i membri dei dati seguenti alla classe `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5. Aggiungere il metodo `CreatePipeline` seguente alla classe `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 Poiché i blocchi di flussi di dati `incrementProgress` e `decrementProgress` vengono usati nell'interfaccia utente, è importante che queste azioni si verifichino nel thread di interfaccia utente. A questo scopo, durante la costruzione ciascuno di questi oggetti fornisce un oggetto <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> la cui proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> è impostata su <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>. Tramite il metodo <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> viene creato un oggetto <xref:System.Threading.Tasks.TaskScheduler> mediante il quale viene eseguito il lavoro nel contesto di sincronizzazione corrente. Poiché il costruttore `Form1` viene chiamato dal thread dell'interfaccia utente, le azioni per i blocchi di flussi di dati `incrementProgress` e `decrementProgress` vengono eseguite anche nel thread dell'interfaccia utente.  
  
 Questo esempio imposta la proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> durante la costruzione dei membri della pipeline. Poiché la proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> annulla definitivamente l'esecuzione del blocco del flusso di dati, l'intera pipeline deve essere ricreata dopo che l'utente annulla l'operazione e quindi vuole aggiungere più elementi di lavoro alla pipeline. Per un esempio che mostra un modo alternativo per annullare un blocco del flusso di dati per poter eseguire un altro lavoro dopo che viene annullata un'operazione, vedere [Walkthrough: Using Dataflow in a Windows Forms Application](walkthrough-using-dataflow-in-a-windows-forms-application.md) (Procedura dettagliata: Uso del flusso di dati in un'applicazione Windows Forms).  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a>Connessione della pipeline del flusso di dati all'interfaccia utente  
 In questa sezione viene descritto come connettere la pipeline del flusso di dati all'interfaccia utente. Sia la creazione della pipeline sia l'aggiunta di elementi di lavoro alla pipeline sono controllate dal gestore eventi tramite il pulsante **Aggiungi elementi di lavoro**. L'annullamento viene avviato dal pulsante **Annulla**. Quando l'utente fa clic su uno di questi pulsanti, l'azione appropriata viene avviata in modo asincrono.  
  
### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a>Per connettere la pipeline del flusso di dati all'interfaccia utente  
  
1. Nella finestra di progettazione del form principale creare un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Aggiungi elementi di lavoro**.  
  
2. Implementare l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Aggiungi elementi di lavoro**.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3. Nella finestra di progettazione del form principale creare un gestore eventi per il gestore eventi <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Annulla**.  
  
4. Implementare l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Annulla**.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra il codice completo per Form1.cs (Form1.vb per Visual Basic).  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 Nell'immagine riportata di seguito viene illustrata l'applicazione in esecuzione.  
  
 ![Applicazione Windows Form](media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")  

## <a name="see-also"></a>Vedere anche

- [Flusso di dati](dataflow-task-parallel-library.md)
