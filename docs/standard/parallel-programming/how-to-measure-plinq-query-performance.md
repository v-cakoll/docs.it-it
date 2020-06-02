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
# <a name="how-to-measure-plinq-query-performance"></a>Procedura: Misurare le prestazioni delle query PLINQ

Questo esempio illustra come usare la <xref:System.Diagnostics.Stopwatch> classe per misurare il tempo necessario per l'esecuzione di una query PLINQ.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa un oggetto vuoto `foreach` ciclo (`For Each` in Visual Basic) per misurare il tempo necessario per eseguire la query. Nel codice del mondo reale, il ciclo in genere contiene passaggi di elaborazione aggiuntivi che si aggiungono al tempo di esecuzione totale della query. Si noti che il cronometro non viene avviato fino a poco prima del ciclo, perché questo è il momento in cui viene avviata l'esecuzione della query. Se si richiede una misura più precisa, è possibile usare la proprietà `ElapsedTicks` invece di `ElapsedMilliseconds`.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 Il tempo di esecuzione totale è una metrica utile quando si sperimentano le implementazioni delle query, ma non sempre l'intera storia. Per ottenere una visualizzazione più approfondita e più dettagliata dell'interazione dei thread di query tra loro e con altri processi in esecuzione, usare il [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
