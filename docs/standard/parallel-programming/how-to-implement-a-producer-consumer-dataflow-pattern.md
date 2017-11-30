---
title: 'Procedura: implementare un modello di flusso di dati producer-consumer'
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
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1aba08e8364d8a21f70ab480d58041115a4849e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a>Procedura: implementare un modello di flusso di dati producer-consumer
In questo documento viene descritto come usare la libreria del flusso di dati TPL per implementare un modello producer-consumer. In questo modello, il *producer* invia messaggi a un blocco di messaggi e il *consumer* legge i messaggi dal blocco.  
  
> [!TIP]
>  La libreria del flusso di dati TPL (spazio dei nomi <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) non viene distribuita con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Per installare il <xref:System.Threading.Tasks.Dataflow> dello spazio dei nomi, Apri il progetto in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], scegliere **Gestisci pacchetti NuGet** dal menu progetto e cercare online il `Microsoft.Tpl.Dataflow` pacchetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un modello di base producer-consumer in cui viene utilizzato il flusso di dati. Tramite il metodo `Produce` vengono scritte matrici contenenti byte casuali di dati in un oggetto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> e tramite il metodo `Consume` vengono letti i byte da un oggetto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType>. Agendo sulle interfacce <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> e <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, anziché sui relativi tipi derivati, è possibile scrivere codice riutilizzabile che può agire su diversi tipi di blocchi di flussi di dati. Nell'esempio viene utilizzata la classe <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>. Poiché la classe <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> viene utilizzata sia come blocco di origine sia come blocco di destinazione, il producer e il consumer possono utilizzare un oggetto condiviso per il trasferimento dei dati.  
  
 Tramite il metodo `Produce` viene chiamato il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> in un ciclo per scrivere i dati in modo sincrono nel blocco di destinazione. Dopo che tramite il metodo `Produce` vengono scritti tutti i dati nel blocco di destinazione, viene chiamato il metodo <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> per indicare che nel blocco non saranno mai presenti dati aggiuntivi disponibili. Il `Consume` metodo utilizza il [async](~/docs/csharp/language-reference/keywords/async.md) e [await](~/docs/csharp/language-reference/keywords/await.md) operatori ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) e [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) per calcolare in modo asincrono il numero totale di byte ricevuti dal <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> oggetto. Per agire in modo asincrono, tramite il metodo `Consume` viene chiamato il metodo <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> per ricevere una notifica quando nel blocco di origine vi sono dati disponibili e quando non vi saranno mai dati aggiuntivi disponibili.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` per [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi di Visual Studio.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 In questo esempio viene utilizzato solo un consumer per elaborare i dati di origine. Se si dispone di più consumer nell'applicazione, utilizzare il metodo <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> per leggere i dati dal blocco di origine, come illustrato nell'esempio riportato di seguito.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 Tramite il metodo <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> viene restituito `False` quando non vi sono dati disponibili. Quando più consumer devono accedere al blocco di origine contemporaneamente, questo meccanismo garantisce che i dati sono sempre disponibili dopo la chiamata a <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
