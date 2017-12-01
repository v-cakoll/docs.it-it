---
title: 'Procedura: annullare un blocco di flussi di dati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d6fbde31cd4b4b5d0c6404b8baf23230f2bda77
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-cancel-a-dataflow-block"></a>Procedura: annullare un blocco di flussi di dati
In questo documento viene dimostrato come abilitare l'annullamento nell'applicazione. In questo esempio Windows Form viene usato per mostrare dove gli elementi di lavoro sono attivi in una pipeline del flusso di dati, nonché gli effetti dell'annullamento.  
  
> [!TIP]
>  La libreria del flusso di dati TPL (spazio dei nomi <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) non viene distribuita con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Per installare il <xref:System.Threading.Tasks.Dataflow> dello spazio dei nomi, Apri il progetto in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], scegliere **Gestisci pacchetti NuGet** dal menu progetto e cercare online il `Microsoft.Tpl.Dataflow` pacchetto.  
  
### <a name="to-create-the-windows-forms-application"></a>Per creare l'applicazione Windows Forms  
  
1.  Creare un progetto **Windows Forms Application** di C# o Visual Basic. Nei passaggi seguenti il progetto viene denominato `CancellationWinForms`.  
  
2.  Nella finestra di progettazione di form per il form principale, Form1.cs (Form1. vb per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), aggiungere un <xref:System.Windows.Forms.ToolStrip> controllo.  
  
3.  Aggiungere un <xref:System.Windows.Forms.ToolStripButton> controllo il <xref:System.Windows.Forms.ToolStrip> controllo. Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> e <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà **aggiungere elementi di lavoro**.  
  
4.  Aggiungere un secondo <xref:System.Windows.Forms.ToolStripButton> controllo il <xref:System.Windows.Forms.ToolStrip> controllo. Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, il <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà **Annulla**e <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> proprietà `False`.  
  
5.  Aggiungere quattro <xref:System.Windows.Forms.ToolStripProgressBar> oggetti per il <xref:System.Windows.Forms.ToolStrip> controllo.  
  
## <a name="creating-the-dataflow-pipeline"></a>Creazione della pipeline del flusso di dati  
 In questa sezione viene descritto come creare la pipeline del flusso di dati che elabora gli elementi di lavoro e aggiorna le barre di stato.  
  
#### <a name="to-create-the-dataflow-pipeline"></a>Per creare la pipeline del flusso di dati  
  
1.  Nel progetto aggiungere un riferimento a System.Threading.Tasks.Dataflow.dll.  
  
2.  Assicurarsi che in Form1.cs (Form1.vb per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) siano contenute le seguenti istruzioni `using` (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  Aggiungere la classe `WorkItem` come un tipo interno della classe `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  Aggiungere i membri dei dati seguenti alla classe `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  Aggiungere il metodo `CreatePipeline` seguente alla classe `Form1`.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 Poiché i blocchi di flussi di dati `incrementProgress` e `decrementProgress` vengono usati nell'interfaccia utente, è importante che queste azioni si verifichino nel thread di interfaccia utente. A tale scopo, durante la costruzione di questi oggetti forniscono ciascuna un <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> oggetto che ha il <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> proprietà impostata su <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>. Tramite il metodo <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> viene creato un oggetto <xref:System.Threading.Tasks.TaskScheduler> mediante il quale viene eseguito il lavoro nel contesto di sincronizzazione corrente. Poiché il costruttore `Form1` viene chiamato dal thread dell'interfaccia utente, le azioni per i blocchi di flussi di dati `incrementProgress` e `decrementProgress` vengono eseguite anche nel thread dell'interfaccia utente.  
  
 In questo esempio il <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> proprietà quando costruisce i membri della pipeline. Poiché il <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> proprietà Annulla definitivamente bloccare l'esecuzione del flusso di dati, è necessario ricreare l'intera pipeline dopo che l'utente annulla l'operazione e quindi si desidera aggiungere più elementi di lavoro per la pipeline. Per un esempio che mostra un modo alternativo per annullare un blocco del flusso di dati per poter eseguire un altro lavoro dopo che viene annullata un'operazione, vedere [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md) (Procedura dettagliata: Uso del flusso di dati in un'applicazione Windows Forms).  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a>Connessione della pipeline del flusso di dati all'interfaccia utente  
 In questa sezione viene descritto come connettere la pipeline del flusso di dati all'interfaccia utente. Sia la creazione della pipeline sia l'aggiunta di elementi di lavoro alla pipeline sono controllate dal gestore eventi tramite il pulsante **Aggiungi elementi di lavoro**. L'annullamento viene avviato dal pulsante **Annulla**. Quando l'utente fa clic su uno di questi pulsanti, l'azione appropriata viene avviata in modo asincrono.  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a>Per connettere la pipeline del flusso di dati all'interfaccia utente  
  
1.  Nella finestra di progettazione di form per il form principale, creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento per il **aggiungere elementi di lavoro** pulsante.  
  
2.  Implementare il <xref:System.Windows.Forms.ToolStripItem.Click> evento per il **aggiungere elementi di lavoro** pulsante.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  Nella finestra di progettazione di form per il form principale, creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per il **Annulla** pulsante.  
  
4.  Implementare il <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per il **Annulla** pulsante.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il codice completo per Form1.cs (Form1.vb per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 Nell'immagine riportata di seguito viene illustrata l'applicazione in esecuzione.  
  
 ![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")  
  
## <a name="robust-programming"></a>Programmazione efficiente  
  
## <a name="see-also"></a>Vedere anche  
 [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
