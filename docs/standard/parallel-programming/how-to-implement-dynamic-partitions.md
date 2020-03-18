---
title: 'Procedura: implementare partizioni dinamiche'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
ms.openlocfilehash: 3970566b4e3f51ce538c328d4e69b20ec22ec09b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091412"
---
# <a name="how-to-implement-dynamic-partitions"></a>Procedura: implementare partizioni dinamiche

L'esempio seguente mostra come implementare un oggetto <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> personalizzato che implementa il partizionamento dinamico e che può essere usato da determinati overload <xref:System.Threading.Tasks.Parallel.ForEach%2A> e da PLINQ.  
  
## <a name="example"></a>Esempio

Ogni volta che una partizione chiama <xref:System.Collections.IEnumerator.MoveNext%2A> nell'enumeratore, l'enumeratore fornisce la partizione con un elemento dell'elenco. Nel caso di PLINQ e di <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partizione è un'istanza <xref:System.Threading.Tasks.Task>. Poiché le richieste vengono eseguite contemporaneamente su più thread, l'accesso all'indice corrente è sincronizzato.  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

Questo è un esempio di partizionamento in blocchi, con ogni blocco costituito da un elemento. Fornendo più elementi per volta, è possibile ridurre il conflitto sul blocco e ottenere in teoria prestazioni più veloci. A un certo punto, tuttavia, blocchi più grandi potrebbero richiedere logica di bilanciamento del carico aggiuntiva per mantenere occupati tutti i thread fino al completamento del lavoro.  
  
## <a name="see-also"></a>Vedere anche

* [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
* [Procedura: implementare un partitioner per il partizionamento statico](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
