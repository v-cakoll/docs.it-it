---
title: "Procedura: specificare un'utilità di pianificazione in un blocco di flussi di dati"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, linking to task scheduler in TPL
- Task Parallel Library, dataflows
- task scheduler, linking from TPL
ms.assetid: 27ece374-ed5b-49ef-9cec-b20db34a65e8
ms.openlocfilehash: 2abac1ccf45fc9c9c28e27c132e72fe483a24d75
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73122226"
---
# <a name="how-to-specify-a-task-scheduler-in-a-dataflow-block"></a>Procedura: specificare un'utilità di pianificazione in un blocco di flussi di dati
In questo documento viene illustrato come associare una specifica utilità di pianificazione delle attività quando si utilizza il flusso di dati nell'applicazione. Nell'esempio viene usata la classe <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair?displayProperty=nameWithType> in un'applicazione Windows Forms per visualizzare quando le attività del lettore sono attive e quando invece lo è una del writer. Viene inoltre utilizzato il metodo <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> per consentire a un blocco di flussi di dati l'esecuzione nel thread dell'interfaccia utente.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="to-create-the-windows-forms-application"></a>Per creare l'applicazione Windows Forms  
  
1. Creare un progetto **Windows Forms Application** Visual C# o Visual Basic. Nei passaggi seguenti il progetto viene denominato `WriterReadersWinForms`.  
  
2. Nella finestra di progettazione del form per il form principale, Form1.cs (Form1.vb per Visual Basic), aggiungere quattro controlli <xref:System.Windows.Forms.CheckBox>. Impostare la proprietà <xref:System.Windows.Forms.Control.Text%2A> su **Reader 1** per `checkBox1`, **Reader 2** per `checkBox2`, **Reader 3** per `checkBox3` e **Writer** per `checkBox4`. Impostare la proprietà <xref:System.Windows.Forms.Control.Enabled%2A> per ogni controllo su `False`.  
  
3. Aggiungere un controllo <xref:System.Windows.Forms.Timer> al form. Impostare la proprietà <xref:System.Windows.Forms.Timer.Interval%2A> su `2500`.  
  
## <a name="adding-dataflow-functionality"></a>Aggiunta di funzionalità del flusso di dati  
 In questa sezione viene descritto come creare i blocchi di flussi di dati che fanno parte dell'applicazione e come associare ognuno di essi a un'utilità di pianificazione delle attività.  
  
### <a name="to-add-dataflow-functionality-to-the-application"></a>Per aggiungere funzionalità del flusso di dati all'applicazione  
  
1. Nel progetto aggiungere un riferimento a System.Threading.Tasks.Dataflow.dll.  
  
2. Assicurarsi che in Form1.cs (Form1.vb per Visual Basic) siano contenute le seguenti istruzioni `using` (`Imports` in Visual Basic).  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#1)]  
  
3. Aggiungere un membro dati <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> alla classe `Form1`.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#2)]  
  
4. Nel costruttore `Form1`, dopo la chiamata a `InitializeComponent`, creare un oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> tramite cui viene alternato lo stato degli oggetti <xref:System.Windows.Forms.CheckBox>.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#3)]  
  
5. Nel costruttore `Form1` creare un oggetto <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> e quattro oggetti <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, un oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> per ogni oggetto <xref:System.Windows.Forms.CheckBox>. Per ogni oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, specificare un oggetto <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> con la proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> impostata sulla proprietà <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ConcurrentScheduler%2A> per i lettori e la proprietà <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ExclusiveScheduler%2A> per il writer.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#4)]  
  
6. Nel costruttore `Form1` avviare l'oggetto <xref:System.Windows.Forms.Timer>.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#5)]  
  
7. Nella finestra di progettazione del form per il form principale creare un gestore eventi per l'evento <xref:System.Windows.Forms.Timer.Tick> per il timer.  
  
8. Implementare l'evento <xref:System.Windows.Forms.Timer.Tick> per il timer.  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#6)]  
  
 Poiché il blocco di flussi di dati `toggleCheckBox` viene utilizzato nell'interfaccia utente, è importante che questa azione si verifichi nel thread dell'interfaccia utente. A tale scopo, durante la costruzione questo oggetto fornisce un oggetto <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> con la proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> impostata su <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>. Tramite il metodo <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A> viene creato un oggetto <xref:System.Threading.Tasks.TaskScheduler> mediante il quale viene eseguito il lavoro nel contesto di sincronizzazione corrente. Poiché il costruttore `Form1` viene chiamato dal thread dell'interfaccia utente, l'azione per il blocco di flussi di dati `toggleCheckBox` viene eseguita anche nel thread dell'interfaccia utente.  
  
 In questo esempio viene inoltre utilizzata la classe <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> per consentire ad alcuni blocchi di flussi di dati di agire simultaneamente e a un altro blocco di flussi di dati di agire in modo esclusivo rispetto a tutti gli altri blocchi di flussi di dati in esecuzione nello stesso oggetto <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair>. Questa tecnica è utile quando da parte di più blocchi di flussi di dati viene condivisa una risorsa mentre altri richiedono l'accesso esclusivo a quest'ultima, poiché viene eliminata la necessità di sincronizzare manualmente l'accesso alla risorsa in questione. L'eliminazione della sincronizzazione manuale può rendere il codice più efficiente.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra il codice completo per Form1.cs (Form1.vb per Visual Basic).  
  
 [!code-csharp[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#100)]  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
