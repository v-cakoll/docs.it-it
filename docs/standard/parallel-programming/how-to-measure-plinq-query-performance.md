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
# <a name="how-to-measure-plinq-query-performance"></a>Procedura: misurare le prestazioni di esecuzione delle query di PLINQ
Questo esempio illustra come usare la classe <xref:System.Diagnostics.Stopwatch> per misurare il tempo necessario per l'esecuzione di una query PLINQ.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa un oggetto vuoto `foreach` ciclo (`For Each` in Visual Basic) per misurare il tempo necessario per eseguire la query. Nel codice del mondo reale, il ciclo in genere contiene passaggi di elaborazione aggiuntivi che si aggiungono al tempo di esecuzione totale della query. Si noti che il cronometro non è avviato fino a poco prima del ciclo, perché è quando inizia l'esecuzione della query. Se si richiede una misura più precisa, è possibile usare la proprietà `ElapsedTicks` invece di `ElapsedMilliseconds`.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 Il tempo di esecuzione totale è una metrica utile quando si sperimentano le implementazioni delle query, ma non è sempre esauriente. Per ottenere una visualizzazione più approfondita e dettagliata dell'interazione tra i thread della query tra loro e con altri processi in esecuzione, usare il Visualizzatore di concorrenza. Per altre informazioni, vedere [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
