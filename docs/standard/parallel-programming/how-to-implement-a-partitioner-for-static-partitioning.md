---
title: 'Procedura: implementare un partitioner per il partizionamento statico'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b28ff0bb8436fefc4956918889435e258ae98b12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Procedura: implementare un partitioner per il partizionamento statico
Nell'esempio seguente viene illustrato come implementare un semplice partitioner personalizzati per PLINQ che esegue il partizionamento statico. Poiché il partitioner non supporta partizioni dinamiche, non è utilizzabile da parte di <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Questo particolare partitioner potrebbe fornire un aumento di velocità su partitioner dell'intervallo predefinito per le origini dati per cui ogni elemento richiede una quantità sempre maggiore del tempo di elaborazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Le partizioni in questo esempio sono basate sul presupposto di un aumento lineare nel tempo di elaborazione per ogni elemento. Nel mondo reale, potrebbe essere difficile da prevedere tempi di elaborazione in questo modo. Se si utilizza un partitioner statico con un'origine dati specifica, è possibile ottimizzare la formula del partizionamento per l'origine, aggiungere logica di bilanciamento del carico o utilizzare l'approccio di partizionamento, come illustrato in blocchi [procedura: implementare partizioni dinamiche](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
