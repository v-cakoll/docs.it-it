---
title: 'Procedura: Misurare le prestazioni delle query PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
ms.openlocfilehash: f240b2c275305aec5699eb42406e0689925490a8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288186"
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="83039-102">Procedura: Misurare le prestazioni delle query PLINQ</span><span class="sxs-lookup"><span data-stu-id="83039-102">How to: Measure PLINQ Query Performance</span></span>

<span data-ttu-id="83039-103">Questo esempio illustra come usare la <xref:System.Diagnostics.Stopwatch> classe per misurare il tempo necessario per l'esecuzione di una query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="83039-103">This example shows how to use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83039-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="83039-104">Example</span></span>  
 <span data-ttu-id="83039-105">Questo esempio usa un oggetto vuoto `foreach` ciclo (`For Each` in Visual Basic) per misurare il tempo necessario per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="83039-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="83039-106">Nel codice del mondo reale, il ciclo in genere contiene passaggi di elaborazione aggiuntivi che si aggiungono al tempo di esecuzione totale della query.</span><span class="sxs-lookup"><span data-stu-id="83039-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="83039-107">Si noti che il cronometro non viene avviato fino a poco prima del ciclo, perché questo è il momento in cui viene avviata l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="83039-107">Notice that the stopwatch is not started until just before the loop, because that's when the query execution begins.</span></span> <span data-ttu-id="83039-108">Se si richiede una misura più precisa, è possibile usare la proprietà `ElapsedTicks` invece di `ElapsedMilliseconds`.</span><span class="sxs-lookup"><span data-stu-id="83039-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="83039-109">Il tempo di esecuzione totale è una metrica utile quando si sperimentano le implementazioni delle query, ma non sempre l'intera storia.</span><span class="sxs-lookup"><span data-stu-id="83039-109">The total execution time is a useful metric when you are experimenting with query implementations, but it doesn't always tell the whole story.</span></span> <span data-ttu-id="83039-110">Per ottenere una visualizzazione più approfondita e più dettagliata dell'interazione dei thread di query tra loro e con altri processi in esecuzione, usare il [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="83039-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83039-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83039-111">See also</span></span>

- [<span data-ttu-id="83039-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="83039-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
