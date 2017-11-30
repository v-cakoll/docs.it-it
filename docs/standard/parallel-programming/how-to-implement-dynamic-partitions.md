---
title: 'Procedura: implementare partizioni dinamiche'
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
helpviewer_keywords: tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1e5dc93997918e0f7da29fa1f94c434a556f19f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-dynamic-partitions"></a>Procedura: implementare partizioni dinamiche
Nell'esempio seguente viene illustrato come implementare un oggetto personalizzato <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> che implementa il partizionamento dinamico e può essere utilizzato da determinati overload <xref:System.Threading.Tasks.Parallel.ForEach%2A> e da PLINQ.  
  
## <a name="example"></a>Esempio  
 Ogni volta che una partizione chiama <xref:System.Collections.IEnumerator.MoveNext%2A> sull'enumeratore, l'enumeratore fornisce la partizione di un elemento dell'elenco. Nel caso di PLINQ e <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partizione è un <xref:System.Threading.Tasks.Task> istanza. Poiché le richieste vengono eseguite contemporaneamente su più thread, l'accesso all'indice corrente è sincronizzato.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 Questo è un esempio di partizionamento, con ogni blocco costituito da un elemento di blocco. Fornendo più elementi alla volta, è possibile ridurre la contesa sul blocco e realizzare teoricamente prestazioni più veloci. A un certo punto blocchi più grandi potrebbero tuttavia richiedere logica aggiuntiva di bilanciamento del carico per mantenere tutti i thread occupato fino al completamento di tutto il lavoro.  
  
## <a name="see-also"></a>Vedere anche  
 [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [Procedura: Implementare un partitioner per il partizionamento statico](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
