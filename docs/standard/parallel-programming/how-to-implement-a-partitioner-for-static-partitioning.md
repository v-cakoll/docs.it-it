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
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 125bef8d43e16c120e88250a4d9d5a4ff3f63dba
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Procedura: implementare un partitioner per il partizionamento statico
L'esempio seguente come implementare un semplice partitioner personalizzato per PLINQ che esegue il partizionamento statico. Poiché il partitioner non supporta partizioni dinamiche, non può essere usato da <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Questo partitioner specifico potrebbe offrire un aumento di velocità rispetto al partitioner dell'intervallo predefinito per origini dati per cui ogni elemento richiede tempi di elaborazione sempre maggiori.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Le partizioni in questo esempio sono basate sul presupposto di un aumento lineare dei tempi di elaborazione per ogni elemento. Nel mondo reale potrebbe essere difficile prevedere i tempi di elaborazione in questo modo. Se si usa un partitioner statico con un'origine dati specifica, è possibile ottimizzare la formula di partizionamento per l'origine, aggiungere logica di bilanciamento del carico o usare un approccio di partizionamento in blocchi, come descritto in [Procedura: Implementare partizioni dinamiche](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
