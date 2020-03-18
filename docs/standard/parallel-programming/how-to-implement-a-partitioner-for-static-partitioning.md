---
title: 'Procedura: implementare un partitioner per il partizionamento statico'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
ms.openlocfilehash: 94fbb681b20b9c920c20df2a9017f75a9aa9a6ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091527"
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Procedura: implementare un partitioner per il partizionamento statico
L'esempio seguente come implementare un semplice partitioner personalizzato per PLINQ che esegue il partizionamento statico. Poiché il partitioner non supporta partizioni dinamiche, non può essere usato da <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Questo partitioner specifico potrebbe offrire un aumento di velocità rispetto al partitioner dell'intervallo predefinito per origini dati per cui ogni elemento richiede tempi di elaborazione sempre maggiori.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Le partizioni in questo esempio sono basate sul presupposto di un aumento lineare dei tempi di elaborazione per ogni elemento. Nel mondo reale potrebbe essere difficile prevedere i tempi di elaborazione in questo modo. Se si usa un partitioner statico con un'origine dati specifica, è possibile ottimizzare la formula di partizionamento per l'origine, aggiungere logica di bilanciamento del carico o usare un approccio di partizionamento in blocchi, come descritto in [Procedura: Implementare partizioni dinamiche](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>Vedere anche

- [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
