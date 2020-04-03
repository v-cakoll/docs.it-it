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
# <a name="how-to-measure-plinq-query-performance"></a>Procedura: misurare le prestazioni di esecuzione delle query di PLINQ

In questo esempio viene <xref:System.Diagnostics.Stopwatch> illustrato come utilizzare la classe per misurare il tempo necessario per l'esecuzione di una query PLINQ.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa un oggetto vuoto `foreach` ciclo (`For Each` in Visual Basic) per misurare il tempo necessario per eseguire la query. Nel codice del mondo reale, il ciclo in genere contiene passaggi di elaborazione aggiuntivi che si aggiungono al tempo di esecuzione totale della query. Si noti che il cronometro non viene avviato fino a poco prima del ciclo, perché è in quel momento l'esecuzione della query. Se si richiede una misura più precisa, è possibile usare la proprietà `ElapsedTicks` invece di `ElapsedMilliseconds`.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 Il tempo di esecuzione totale è una metrica utile quando si sperimentano le implementazioni di query, ma non sempre racconta l'intera storia. Per ottenere una visualizzazione più approfondita e più approfondita dell'interazione dei thread di query tra loro e con altri processi in esecuzione, utilizzare il [visualizzatore](/visualstudio/profiling/concurrency-visualizer)di concorrenza .  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
