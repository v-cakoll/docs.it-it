---
title: 'Procedura: implementare un modello di flusso di dati producer-consumer'
description: Informazioni su come implementare un modello di flusso di data producer-consumer usando la libreria del flusso di flussi di flussi di documentazione in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
ms.openlocfilehash: e9ed8f84f1daca64fa60d8aed18aa2d9be1380e0
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768924"
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a>Procedura: implementare un modello di flusso di dati producer-consumer
In questo documento viene descritto come usare la libreria del flusso di dati TPL per implementare un modello producer-consumer. In questo modello, il *producer* invia messaggi a un blocco di messaggi e il *consumer* legge i messaggi dal blocco.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un modello di base producer-consumer in cui viene utilizzato il flusso di dati. Tramite il metodo `Produce` vengono scritte matrici contenenti byte casuali di dati in un oggetto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> e tramite il metodo `Consume` vengono letti i byte da un oggetto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType>. Agendo sulle interfacce <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> e <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, anziché sui relativi tipi derivati, è possibile scrivere codice riutilizzabile che può agire su diversi tipi di blocchi di flussi di dati. Nell'esempio viene utilizzata la classe <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>. Poiché la classe <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> viene utilizzata sia come blocco di origine sia come blocco di destinazione, il producer e il consumer possono utilizzare un oggetto condiviso per il trasferimento dei dati.  
  
 Tramite il metodo `Produce` viene chiamato il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> in un ciclo per scrivere i dati in modo sincrono nel blocco di destinazione. Dopo che tramite il metodo `Produce` vengono scritti tutti i dati nel blocco di destinazione, viene chiamato il metodo <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> per indicare che nel blocco non saranno mai presenti dati aggiuntivi disponibili. Il metodo `Consume` usa gli operatori [async](../../csharp/language-reference/keywords/async.md) e [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) e [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic) per calcolare in modo asincrono il numero totale di byte ricevuti dall'oggetto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>. Per agire in modo asincrono, tramite il metodo `Consume` viene chiamato il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> per ricevere una notifica quando nel blocco di origine vi sono dati disponibili e quando non vi saranno mai dati aggiuntivi disponibili.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 L'esempio precedente usa solo un consumer per elaborare i dati di origine. Se si dispone di più consumer nell'applicazione, utilizzare il metodo <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> per leggere i dati dal blocco di origine, come illustrato nell'esempio riportato di seguito.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 Tramite il metodo <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> viene restituito `False` quando non vi sono dati disponibili. Quando più consumer devono accedere al blocco di origine contemporaneamente, questo meccanismo garantisce che i dati sono sempre disponibili dopo la chiamata a <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di dati](dataflow-task-parallel-library.md)
