---
title: "Procedura: eseguire un'azione alla ricezione di dati in un blocco di flussi di dati"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, receiving data
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
ms.openlocfilehash: 647e77f0c5e182cea90f6e90063826b705de354b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288173"
---
# <a name="how-to-perform-action-when-a-dataflow-block-receives-data"></a>Procedura: eseguire un'azione alla ricezione di dati in un blocco di flussi di dati
Tramite i tipi di *blocchi di flussi di esecuzione* viene chiamato un delegato fornito dall'utente alla ricezione dei dati. Le classi <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> sono tipi di blocchi di flussi di dati di esecuzione. È possibile utilizzare la parola chiave `delegate` (`Sub` in Visual Basic), <xref:System.Action%601>, <xref:System.Func%602> o un'espressione lambda, quando viene fornita una funzione lavoro a un blocco di flussi di dati di esecuzione. In questo documento viene descritto come utilizzare <xref:System.Func%602> e le espressioni lambda per eseguire l'azione nei blocchi di esecuzione.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un flusso di dati per leggere un file da un disco e viene calcolato il numero di byte del file in questione che corrisponde a zero. Vengono utilizzati <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> per leggere il file e calcolare il numero di byte zero e <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> per stampare il numero di byte zero sulla console. Tramite l'oggetto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> viene specificato un oggetto <xref:System.Func%602> per eseguire il lavoro quando vengono ricevuti i dati da parte dei blocchi. Nell'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> viene utilizzata un'espressione lambda per stampare sulla console il numero di byte zero che vengono letti.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 Sebbene sia possibile fornire un'espressione lambda a un oggetto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, in questo esempio viene utilizzato l'oggetto <xref:System.Func%602> per consentire l'utilizzo del metodo `CountBytes` ad altro codice. Nell'oggetto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> viene utilizzata un'espressione lambda in quanto il lavoro da eseguire è specifico per questa attività e probabilmente non è utile per altro codice. Per altre informazioni sull'uso di espressioni lambda nella libreria TPL, vedere [Espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md).  
  
 La sezione Riepilogo dei tipi delegati nel documento del [flusso di flussi](dataflow-task-parallel-library.md) riepiloga i tipi di delegati che è possibile fornire agli <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> oggetti, e <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> . Nella tabella viene inoltre specificato se il tipo delegato viene eseguito in modo sincrono o asincrono.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 In questo esempio viene fornito un delegato di tipo <xref:System.Func%602> all'oggetto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> per eseguire l'attività del blocco di flussi di dati in modo sincrono. Per abilitare un comportamento asincrono del blocco di flussi di dati, fornire un delegato di tipo <xref:System.Func%601> a questo tipo di blocco. Quando il comportamento di un blocco di flussi di dati è asincrono, l'attività del blocco di flussi di dati viene completata solo quando termina l'oggetto <xref:System.Threading.Tasks.Task%601> restituito. Nell'esempio seguente viene modificato il metodo `CountBytes` e vengono usati gli operatori [async](../../csharp/language-reference/keywords/async.md) e [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) e [Await](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic) per calcolare in modo asincrono il numero totale di byte che è pari a zero nel file specificato. Tramite il metodo <xref:System.IO.FileStream.ReadAsync%2A> vengono eseguite operazioni di lettura da file in modo asincrono.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 È inoltre possibile utilizzare le espressioni lambda asincrone per eseguire azioni in un blocco di flussi di dati di esecuzione. Nell'esempio seguente viene modificato l'oggetto <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> utilizzato nell'esempio precedente in modo da utilizzare un'espressione lambda per eseguire il lavoro in modo asincrono.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di dati](dataflow-task-parallel-library.md)
