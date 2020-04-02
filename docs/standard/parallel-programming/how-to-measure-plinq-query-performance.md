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
ms.openlocfilehash: 4cb0d408798d66c8491654c90f33255c700690a3
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80587786"
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="5f11c-102">Procedura: misurare le prestazioni di esecuzione delle query di PLINQ</span><span class="sxs-lookup"><span data-stu-id="5f11c-102">How to: Measure PLINQ Query Performance</span></span>
<span data-ttu-id="5f11c-103">Questo esempio illustra come usare la classe <xref:System.Diagnostics.Stopwatch> per misurare il tempo necessario per l'esecuzione di una query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="5f11c-103">This example shows how use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f11c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f11c-104">Example</span></span>  
 <span data-ttu-id="5f11c-105">Questo esempio usa un oggetto vuoto `foreach` ciclo (`For Each` in Visual Basic) per misurare il tempo necessario per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="5f11c-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="5f11c-106">Nel codice del mondo reale, il ciclo in genere contiene passaggi di elaborazione aggiuntivi che si aggiungono al tempo di esecuzione totale della query.</span><span class="sxs-lookup"><span data-stu-id="5f11c-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="5f11c-107">Si noti che il cronometro non è avviato fino a poco prima del ciclo, perché è quando inizia l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="5f11c-107">Notice that the stopwatch is not started until just before the loop, because that is when the query execution begins.</span></span> <span data-ttu-id="5f11c-108">Se si richiede una misura più precisa, è possibile usare la proprietà `ElapsedTicks` invece di `ElapsedMilliseconds`.</span><span class="sxs-lookup"><span data-stu-id="5f11c-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="5f11c-109">Il tempo di esecuzione totale è una metrica utile quando si sperimentano le implementazioni delle query, ma non è sempre esauriente.</span><span class="sxs-lookup"><span data-stu-id="5f11c-109">The total execution time is a useful metric when you are experimenting with query implementations, but it does not always tell the whole story.</span></span> <span data-ttu-id="5f11c-110">Per ottenere una visualizzazione più approfondita e dettagliata dell'interazione tra i thread della query tra loro e con altri processi in esecuzione, usare il Visualizzatore di concorrenza.</span><span class="sxs-lookup"><span data-stu-id="5f11c-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the Concurrency Visualizer.</span></span> <span data-ttu-id="5f11c-111">Per altre informazioni, vedere [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="5f11c-111">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f11c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f11c-112">See also</span></span>

- [<span data-ttu-id="5f11c-113">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="5f11c-113">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
