---
title: 'Procedura: misurare le prestazioni di esecuzione delle query di PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
ms.openlocfilehash: 37bd3bc464f719876b2fe13ee1a11ebca4339988
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635822"
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="d5de2-102">Procedura: misurare le prestazioni di esecuzione delle query di PLINQ</span><span class="sxs-lookup"><span data-stu-id="d5de2-102">How to: Measure PLINQ Query Performance</span></span>

<span data-ttu-id="d5de2-103">In questo esempio viene <xref:System.Diagnostics.Stopwatch> illustrato come utilizzare la classe per misurare il tempo necessario per l'esecuzione di una query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="d5de2-103">This example shows how to use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5de2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5de2-104">Example</span></span>  
 <span data-ttu-id="d5de2-105">Questo esempio usa un oggetto vuoto `foreach` ciclo (`For Each` in Visual Basic) per misurare il tempo necessario per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="d5de2-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="d5de2-106">Nel codice del mondo reale, il ciclo in genere contiene passaggi di elaborazione aggiuntivi che si aggiungono al tempo di esecuzione totale della query.</span><span class="sxs-lookup"><span data-stu-id="d5de2-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="d5de2-107">Si noti che il cronometro non viene avviato fino a poco prima del ciclo, perché è in quel momento l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="d5de2-107">Notice that the stopwatch is not started until just before the loop, because that's when the query execution begins.</span></span> <span data-ttu-id="d5de2-108">Se si richiede una misura più precisa, è possibile usare la proprietà `ElapsedTicks` invece di `ElapsedMilliseconds`.</span><span class="sxs-lookup"><span data-stu-id="d5de2-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="d5de2-109">Il tempo di esecuzione totale è una metrica utile quando si sperimentano le implementazioni di query, ma non sempre racconta l'intera storia.</span><span class="sxs-lookup"><span data-stu-id="d5de2-109">The total execution time is a useful metric when you are experimenting with query implementations, but it doesn't always tell the whole story.</span></span> <span data-ttu-id="d5de2-110">Per ottenere una visualizzazione più approfondita e più approfondita dell'interazione dei thread di query tra loro e con altri processi in esecuzione, utilizzare il [visualizzatore](/visualstudio/profiling/concurrency-visualizer)di concorrenza .</span><span class="sxs-lookup"><span data-stu-id="d5de2-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5de2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5de2-111">See also</span></span>

- [<span data-ttu-id="d5de2-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="d5de2-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
