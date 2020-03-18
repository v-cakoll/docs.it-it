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
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="27ef2-102">Procedura: implementare un partitioner per il partizionamento statico</span><span class="sxs-lookup"><span data-stu-id="27ef2-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="27ef2-103">L'esempio seguente come implementare un semplice partitioner personalizzato per PLINQ che esegue il partizionamento statico.</span><span class="sxs-lookup"><span data-stu-id="27ef2-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="27ef2-104">Poiché il partitioner non supporta partizioni dinamiche, non può essere usato da <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27ef2-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="27ef2-105">Questo partitioner specifico potrebbe offrire un aumento di velocità rispetto al partitioner dell'intervallo predefinito per origini dati per cui ogni elemento richiede tempi di elaborazione sempre maggiori.</span><span class="sxs-lookup"><span data-stu-id="27ef2-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27ef2-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="27ef2-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="27ef2-107">Le partizioni in questo esempio sono basate sul presupposto di un aumento lineare dei tempi di elaborazione per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="27ef2-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="27ef2-108">Nel mondo reale potrebbe essere difficile prevedere i tempi di elaborazione in questo modo.</span><span class="sxs-lookup"><span data-stu-id="27ef2-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="27ef2-109">Se si usa un partitioner statico con un'origine dati specifica, è possibile ottimizzare la formula di partizionamento per l'origine, aggiungere logica di bilanciamento del carico o usare un approccio di partizionamento in blocchi, come descritto in [Procedura: Implementare partizioni dinamiche](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="27ef2-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ef2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27ef2-110">See also</span></span>

- [<span data-ttu-id="27ef2-111">Partitioner personalizzati per PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="27ef2-111">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
