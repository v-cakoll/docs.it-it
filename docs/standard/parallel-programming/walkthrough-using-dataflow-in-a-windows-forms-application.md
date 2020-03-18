---
title: "Procedura dettagliata: Uso del flusso di dati in un'applicazione Windows Forms"
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- TPL dataflow library, in Windows Forms
- Task Parallel Library, dataflows
- Windows Forms, and TPL
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
ms.openlocfilehash: 794253514edf63f02276e1ece21c60a85c534390
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159767"
---
# <a name="walkthrough-using-dataflow-in-a-windows-forms-application"></a>Procedura dettagliata: Uso del flusso di dati in un'applicazione Windows Forms
Questo documento illustra come creare una rete di blocchi di flussi di dati tramite cui viene eseguita l'elaborazione di immagini in una Windows Forms Application.  
  
 Questo esempio carica i file di immagine dalla cartella specificata, crea un'immagine composita e visualizza il risultato. L'esempio utilizza il modello di flusso di dati per instradare le immagini tramite la rete. Nel modello del flusso di dati, i componenti indipendenti di un programma di comunicano tra loro mediante l'invio di messaggi. Quando un componente riceve un messaggio, esegue una determinata azione e quindi passa il risultato a un altro componente. Confrontare questo modello con il modello di flusso di controllo, in cui un'applicazione utilizza le strutture di controllo, ad esempio le istruzioni condizionali, i cicli e così via, per controllare l'ordine delle operazioni in un programma.  
  
## <a name="prerequisites"></a>Prerequisites  
 Prima di iniziare questa procedura dettagliata, leggere [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="sections"></a>Sezioni  
 Questa procedura dettagliata contiene le sezioni seguenti:  
  
- [Creazione di Windows Forms Application](#winforms)  
  
- [Creazione della rete del flusso di dati](#network)  
  
- [Connessione della rete del flusso dati all'interfaccia utente](#ui)  
  
- [Esempio completo](#complete)  
  
<a name="winforms"></a>
## <a name="creating-the-windows-forms-application"></a>Creazione di Windows Forms Application  
 In questa sezione viene descritto come creare la Windows Forms Application di base e aggiungere i controlli al modulo principale.  
  
### <a name="to-create-the-windows-forms-application"></a>Per creare l'applicazione Windows Forms  
  
1. In Visual Studio creare un progetto **Applicazione Windows Form** di Visual C# o Visual Basic. In questo documento, il progetto viene denominato `CompositeImages`.  
  
2. Nella finestra di progettazione del form per il form principale, Form1.cs (Form1.vb per Visual Basic), aggiungere un controllo <xref:System.Windows.Forms.ToolStrip>.  
  
3. Aggiungere un controllo <xref:System.Windows.Forms.ToolStripButton> al controllo <xref:System.Windows.Forms.ToolStrip>. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> su <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> e la proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su **Scegli cartella**.  
  
4. Aggiungere un secondo controllo <xref:System.Windows.Forms.ToolStripButton> al controllo <xref:System.Windows.Forms.ToolStrip>. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> su <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, la proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> su **Annulla** e la proprietà <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> su `False`.  
  
5. Aggiungere un oggetto <xref:System.Windows.Forms.PictureBox> al form principale. Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
<a name="network"></a>
## <a name="creating-the-dataflow-network"></a>Creazione della rete del flusso di dati  
 In questa sezione viene descritto come creare la rete del flusso di dati che esegue l'elaborazione delle immagini.  
  
### <a name="to-create-the-dataflow-network"></a>Per creare la rete del flusso di dati  
  
1. Nel progetto aggiungere un riferimento a System.Threading.Tasks.Dataflow.dll.  
  
2. Assicurarsi che in Form1.cs (Form1.vb per Visual Basic) siano contenute le seguenti istruzioni `using` (`Using` in Visual Basic):  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3. Aggiungere i membri dei dati seguenti alla classe `Form1`:  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4. Aggiungere il metodo `CreateImageProcessingNetwork` seguente alla classe `Form1`. Questo metodo crea una rete di elaborazione delle immagini.  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5. Implementare il metodo `LoadBitmaps`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6. Implementare il metodo `CreateCompositeBitmap`.  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    > La versione C# del metodo `CreateCompositeBitmap` usa puntatori per abilitare l'elaborazione efficiente degli oggetti <xref:System.Drawing.Bitmap?displayProperty=nameWithType>. Pertanto, è necessario abilitare l'opzione **Consenti codice di tipo unsafe** nel progetto per utilizzare la parola chiave [unsafe](../../csharp/language-reference/keywords/unsafe.md). Per altre informazioni su come abilitare il codice unsafe in un progetto Visual C#, vedere [Pagina Compilazione, Creazione progetti (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
 Nella tabella seguente vengono descritti i membri della rete.  
  
|Membro|Type|Descrizione|  
|------------|----------|-----------------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Accetta il percorso di una cartella come input e genera una raccolta di oggetti <xref:System.Drawing.Bitmap> come output.|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Accetta una raccolta di oggetti <xref:System.Drawing.Bitmap> come input e genera una bitmap composita come output.|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Visualizza il bitmap composito nel modulo.|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Visualizza un'immagine per indicare che l'operazione è annullata e consente all'utente di selezionare un'altra cartella.|  
  
 Per connettere i blocchi di flussi di dati per formare una rete, questo esempio usa il metodo <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A>. Il metodo <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> contiene una versione di overload che accetta un oggetto <xref:System.Predicate%601> che determina se il blocco di destinazione accetta o rifiuta un messaggio. Questo processo di filtraggio consente ai blocchi di messaggi di ricevere solo certi valori. In questo esempio, la rete può creare un ramo in due modi. Il ramo principale carica le immagini dal disco, crea un'immagine composita e visualizza tale immagine nel modulo. Il ramo alternativo annulla l'operazione in corso. Gli oggetti <xref:System.Predicate%601> consentono ai blocchi di flussi di dati lungo il ramo principale di passare al ramo alternativo rifiutando determinati messaggi. Ad esempio, se l'utente annulla l'operazione, il blocco del flusso di dati `createCompositeBitmap` genera `null` (`Nothing` in Visual Basic) come output. Il blocco del flusso di dati `displayCompositeBitmap` rifiuta i valori di input `null` e pertanto, il messaggio viene offerto a `operationCancelled`. Il blocco del flusso di dati `operationCancelled` accetta tutti i messaggi e visualizza quindi un'immagine per indicare che l'operazione viene annullata.  
  
 Nella figura seguente viene illustrata la rete di elaborazione delle immagini:  
  
 ![Figura che illustra la rete di elaborazione delle immagini.](./media/walkthrough-using-dataflow-in-a-windows-forms-application/dataflow-winforms-image-processing.png)  
  
 Poiché i blocchi di flussi di dati `displayCompositeBitmap` e `operationCancelled` vengono usati nell'interfaccia utente, è importante che queste azioni si verifichino nel thread di interfaccia utente. A questo scopo, durante la costruzione ognuno di questi oggetti fornisce un oggetto <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> la cui proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> è impostata su <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>. Tramite il metodo <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> viene creato un oggetto <xref:System.Threading.Tasks.TaskScheduler> mediante il quale viene eseguito il lavoro nel contesto di sincronizzazione corrente. Poiché il metodo `CreateImageProcessingNetwork` viene chiamato dal gestore del pulsante **Scegli cartella**, che viene eseguito nel thread di interfaccia utente, anche le azioni per i blocchi di flussi di dati `displayCompositeBitmap` e `operationCancelled` vengono eseguite nel thread di interfaccia utente.  
  
 Questo esempio usa un token di annullamento condiviso anziché impostare la proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>, perché la proprietà <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> annulla in modo permanente l'esecuzione dei blocchi di flussi di dati. Un token di annullamento consente in questo esempio di riutilizzare la stessa rete del flusso di dati più volte, anche quando l'utente annulla una o più operazioni. Per un esempio che usa <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> per annullare in modo permanente l'esecuzione di un blocco di flussi di dati, vedere [Procedura: Annullare un blocco di flussi di dati](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md).  
  
<a name="ui"></a>
## <a name="connecting-the-dataflow-network-to-the-user-interface"></a>Connessione della rete del flusso dati all'interfaccia utente  
 In questa sezione viene descritto come connettere la rete del flusso di dati all'interfaccia utente. La creazione dell'immagine composita e l'annullamento dell'operazione vengono avviate dai pulsanti **Scegli cartella** e **Annulla**. Quando l'utente sceglie uno di questi pulsanti, l'azione appropriata viene avviata in modo asincrono.  
  
### <a name="to-connect-the-dataflow-network-to-the-user-interface"></a>Per connettere la rete del flusso dati all'interfaccia utente  
  
1. Nella finestra di progettazione del form principale creare un gestore per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Scegli cartella**.  
  
2. Implementare l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Scegli cartella**.  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3. Nella finestra di progettazione del form principale creare un gestore per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Annulla**.  
  
4. Implementare l'evento <xref:System.Windows.Forms.ToolStripItem.Click> per il pulsante **Annulla**.  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>
## <a name="the-complete-example"></a>Esempio completo  
 Nell'esempio riportato di seguito viene illustrato il codice completo per questa procedura guidata.  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 La figura seguente mostra un output tipico per la cartella common\Sample Pictures\.  
  
 ![Applicazione Windows Form](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow_CompositeImages")  

## <a name="see-also"></a>Vedere anche

- [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
