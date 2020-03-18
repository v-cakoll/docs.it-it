---
title: 'Procedura: specificare il grado di parallelismo in un blocco di flussi di dati'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
ms.openlocfilehash: 50399d6cd32fe310089395ac8c660b08151ba808
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141661"
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a>Procedura: specificare il grado di parallelismo in un blocco di flussi di dati
In questo documento viene descritto come impostare la proprietà <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> per consentire a un blocco di flussi di dati di esecuzione di elaborare più messaggi alla volta. Questa operazione è utile quando è presente un blocco di flussi di dati in cui viene eseguito un calcolo di lunga durata ed è possibile trarre vantaggio dall'elaborazione di messaggi in parallelo. Nell'esempio viene usata la classe <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> per eseguire più operazioni di flussi di dati contemporaneamente; tuttavia, è possibile specificare il massimo grado di parallelismo in uno dei tipi di blocchi di esecuzione predefiniti forniti dalla libreria del flusso di dati TPL, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono eseguiti due calcoli del flusso di dati e viene stampato il tempo trascorso richiesto per ogni calcolo. Nel primo calcolo viene specificato un grado massimo di parallelismo pari a 1, vale a dire l'impostazione predefinita. Un grado massimo di parallelismo pari a 1 determina un'elaborazione seriale dei messaggi da parte del blocco di flussi di dati. Il secondo calcolo è simile al primo, con la differenza che specifica un massimo grado di parallelismo uguale al numero di processori disponibili. Ciò consente al blocco di flusso di dati di eseguire più operazioni in parallelo.  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Per impostazione predefinita, tramite ogni blocco di flussi di dati predefinito i messaggi vengono propagati all'esterno nell'ordine in cui vengono ricevuti.  Anche se vengono elaborati più messaggi contemporaneamente quando si specifica un grado massimo di parallelismo maggiore di 1, questi vengono comunque propagati all'esterno nell'ordine in cui vengono ricevuti.  
  
 Poiché la proprietà <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> rappresenta il grado massimo di parallelismo, il blocco di flussi di dati può essere eseguito con un grado di parallelismo minore rispetto a quello specificato. Con il blocco di flussi di dati è possibile usare un minore grado di parallelismo per soddisfare i relativi requisiti funzionali o per tener conto della mancanza di risorse di sistema disponibili. Da parte di un blocco di flussi di dati non viene mai scelto un parallelismo maggiore di quello specificato.  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di dati](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
