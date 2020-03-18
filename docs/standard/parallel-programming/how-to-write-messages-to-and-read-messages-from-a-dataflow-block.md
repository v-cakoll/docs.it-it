---
title: 'Procedura: scrivere messaggi in un blocco di flussi di dati e leggere messaggi da un blocco di flussi di dati'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
ms.openlocfilehash: 58927803b741acf6c1964b35f6603e6901f9cbf1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139278"
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a>Procedura: scrivere messaggi in un blocco di flussi di dati e leggere messaggi da un blocco di flussi di dati
In questo documento viene descritto come utilizzare la libreria del flusso di dati TPL per scrivere messaggi in un blocco di flussi di dati e per leggerli da quest'ultimo. La libreria del flusso di dati TPL fornisce sia metodi sincroni sia asincroni per la lettura e scrittura di messaggi da e in un blocco di flussi di dati. In questo documento viene utilizzata la classe <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType>. Mediante la classe <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> i messaggi vengono inseriti nel buffer; inoltre, essa viene utilizzata sia come origine sia come destinazione dei messaggi.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a>Scrittura in e lettura da un blocco di flussi di dati in modo sincrono  
 Nell'esempio seguente vengono utilizzati il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> per scrivere in un blocco di flussi di dati <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> e il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> per leggere dallo stesso oggetto.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 È inoltre possibile utilizzare il metodo <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> per leggere da un blocco di flussi di dati, come mostrato nell'esempio riportato di seguito. Tramite il metodo <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> non viene bloccato il thread corrente ed esso risulta utile quando si esegue occasionalmente il polling dei dati.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 Poiché il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> viene utilizzato in modo sincrono, da parte dell'oggetto <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> negli esempi precedenti vengono ricevuti tutti i dati prima che vengono letti dal secondo ciclo. Nell'esempio seguente viene esteso il primo esempio utilizzando il metodo <xref:System.Threading.Tasks.Parallel.Invoke%2A> per leggere dal blocco di messaggi o per scrivere in quest'ultimo contemporaneamente. Poiché tramite il metodo <xref:System.Threading.Tasks.Parallel.Invoke%2A> vengono eseguite operazioni contemporanee, i valori non vengono scritti nell'oggetto <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> in un ordine specifico.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a>Scrittura in e lettura da un blocco di flussi di dati in modo asincrono  
 Nell'esempio seguente viene utilizzato il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> per scrivere in modo asincrono in un oggetto <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> e il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> per leggere in modo asincrono dallo stesso oggetto. Nell'esempio vengono usati gli operatori [async](../../csharp/language-reference/keywords/async.md) e [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) e [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic) per inviare i dati al blocco di destinazione e per leggerli da quest'ultimo in modo asincrono. Il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> è utile quando è necessario consentire a un blocco di flussi di dati di posticipare i messaggi. Il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> è utile se si desidera agire sui dati quando questi diventano disponibili. Per altre informazioni su come propagare i messaggi tra i relativi blocchi, vedere la sezione Passaggio di messaggi in [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a>Esempio completo  
 Nell'esempio riportato di seguito viene illustrato il codice completo per questo documento.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="next-steps"></a>Passaggi successivi  
 In questo esempio viene mostrato come leggere da un blocco di messaggi e come scrivere in quest'ultimo direttamente. È anche possibile connettere i blocchi di flussi di dati per creare *pipeline*, che sono sequenze lineari di blocchi di flussi di dati, o *reti*, che sono grafici di blocchi di flussi di dati. I dati di origini in una pipeline o in una rete vengono propagati nelle destinazioni in modo asincrono quando i dati in questione diventano disponibili. Per un esempio che crea una pipeline di base del flusso di dati, vedere [Procedura dettagliata: creazione di una pipeline del flusso di dati](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md). Per un esempio che crea una rete del flusso di dati più complessa, vedere [Procedura dettagliata: Uso del flusso di dati in un'applicazione Windows Forms](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
