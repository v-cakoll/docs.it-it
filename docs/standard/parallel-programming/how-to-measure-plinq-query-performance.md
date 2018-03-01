---
title: 'Procedura: misurare le prestazioni di esecuzione delle query di PLINQ'
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
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fe19fd6ae7730a30a9ccc8a39b99a31981f838fa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="d9533-102">Procedura: misurare le prestazioni di esecuzione delle query di PLINQ</span><span class="sxs-lookup"><span data-stu-id="d9533-102">How to: Measure PLINQ Query Performance</span></span>
<span data-ttu-id="d9533-103">Questo esempio illustra come usare la classe <xref:System.Diagnostics.Stopwatch> per misurare il tempo necessario per l'esecuzione di una query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="d9533-103">This example shows how use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9533-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9533-104">Example</span></span>  
 <span data-ttu-id="d9533-105">Questo esempio usa un oggetto vuoto `foreach` ciclo (`For Each` in Visual Basic) per misurare il tempo necessario per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="d9533-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="d9533-106">Nel codice del mondo reale, il ciclo in genere contiene passaggi di elaborazione aggiuntivi che si aggiungono al tempo di esecuzione totale della query.</span><span class="sxs-lookup"><span data-stu-id="d9533-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="d9533-107">Si noti che il cronometro non è avviato fino a poco prima del ciclo, perché è quando inizia l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="d9533-107">Notice that the stopwatch is not started until just before the loop, because that is when the query execution begins.</span></span> <span data-ttu-id="d9533-108">Se si richiede una misura più precisa, è possibile usare la proprietà `ElapsedTicks` invece di `ElapsedMilliseconds`.</span><span class="sxs-lookup"><span data-stu-id="d9533-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="d9533-109">Il tempo di esecuzione totale è una metrica utile quando si sperimentano le implementazioni delle query, ma non è sempre esauriente.</span><span class="sxs-lookup"><span data-stu-id="d9533-109">The total execution time is a useful metric when you are experimenting with query implementations, but it does not always tell the whole story.</span></span> <span data-ttu-id="d9533-110">Per ottenere una visualizzazione più approfondita e dettagliata dell'interazione tra i thread della query tra loro e con altri processi in esecuzione, usare il Visualizzatore di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="d9533-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the Concurrency Visualizer.</span></span> <span data-ttu-id="d9533-111">Per altre informazioni, vedere [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="d9533-111">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9533-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9533-112">See Also</span></span>  
 [<span data-ttu-id="d9533-113">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="d9533-113">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
