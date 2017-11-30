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
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="85386-102">Procedura: implementare un partitioner per il partizionamento statico</span><span class="sxs-lookup"><span data-stu-id="85386-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="85386-103">Nell'esempio seguente viene illustrato come implementare un semplice partitioner personalizzati per PLINQ che esegue il partizionamento statico.</span><span class="sxs-lookup"><span data-stu-id="85386-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="85386-104">Poiché il partitioner non supporta partizioni dinamiche, non è utilizzabile da parte di <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="85386-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="85386-105">Questo particolare partitioner potrebbe fornire un aumento di velocità su partitioner dell'intervallo predefinito per le origini dati per cui ogni elemento richiede una quantità sempre maggiore del tempo di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="85386-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85386-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="85386-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="85386-107">Le partizioni in questo esempio sono basate sul presupposto di un aumento lineare nel tempo di elaborazione per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="85386-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="85386-108">Nel mondo reale, potrebbe essere difficile da prevedere tempi di elaborazione in questo modo.</span><span class="sxs-lookup"><span data-stu-id="85386-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="85386-109">Se si utilizza un partitioner statico con un'origine dati specifica, è possibile ottimizzare la formula del partizionamento per l'origine, aggiungere logica di bilanciamento del carico o utilizzare l'approccio di partizionamento, come illustrato in blocchi [procedura: implementare partizioni dinamiche](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="85386-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85386-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85386-110">See Also</span></span>  
 [<span data-ttu-id="85386-111">Partitioner personalizzati per PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="85386-111">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
