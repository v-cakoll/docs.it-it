---
title: Parallelismo dei dati (Task Parallel Library)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallelism, data
ms.assetid: 3f05f33f-f1da-4b16-81c2-9ceff1bef449
ms.openlocfilehash: f0910ae928e94b487df5a3dfd456ee9d7c0fb7df
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80587602"
---
# <a name="data-parallelism-task-parallel-library"></a>Parallelismo dei dati (Task Parallel Library)
Con l'espressione *parallelismo dei dati* ci si riferisce a scenari in cui la stessa operazione viene eseguita contemporaneamente (ovvero in parallelo) sugli elementi di una matrice o una raccolta di origine. Nelle operazioni in parallelo su dati la raccolta di origine viene suddivisa in partizioni in modo che più thread possano agire simultaneamente su segmenti diversi.  
  
 La libreria Task Parallel Library (TPL) supporta il parallelismo dei dati tramite la classe <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>. Questa classe fornisce le implementazioni in parallelo basate su metodo dei cicli [for](../../csharp/language-reference/keywords/for.md) e [foreach](../../csharp/language-reference/keywords/foreach-in.md) (`For` e `For Each` in Visual Basic). La scrittura della logica di un ciclo <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> è molto simile a quella della logica di un ciclo sequenziale. Non è necessario creare thread o accodare elementi di lavoro. Nei cicli di base non è necessario acquisire blocchi. La libreria TPL gestisce automaticamente tutto il lavoro di basso livello. Per informazioni dettagliate sull'uso di <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>, scaricare il documento [Patterns for Parallel Programming: Understanding and Applying Parallel Patterns with the .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=19222) (Modelli per la programmazione parallela: informazioni sui modelli paralleli con .NET Framework 4 e su come applicarli). L'esempio di codice seguente mostra un ciclo `foreach` semplice e il relativo equivalente parallelo.  
  
> [!NOTE]
> Questa documentazione usa espressioni lambda per definire delegati in TPL. Se non si ha familiarità con le espressioni lambda in Visual Basic o in Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 [!code-csharp[TPL#20](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#20)]
 [!code-vb[TPL#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#20)]  
  
 Quando viene eseguito un ciclo parallelo, la libreria TPL esegue il partizionamento dell'origine dati in modo che il ciclo possa agire simultaneamente su più parti. L'utilità di pianificazione esegue automaticamente il partizionamento dell'attività in base alle risorse di sistema e al carico di lavoro. Quando risulta possibile, se si verifica uno sbilanciamento del carico di lavoro, l'utilità di pianificazione ridistribuisce il lavoro fra più thread e processori.  
  
> [!NOTE]
> È anche possibile fornire un partitioner o un'utilità di pianificazione personalizzata, Per altre informazioni, vedere [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) e [Utilità di pianificazione delle attività](xref:System.Threading.Tasks.TaskScheduler).  
  
 Sia il metodo <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> sia il metodo <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> presentano vari overload che consentono di arrestare o interrompere l'esecuzione del ciclo, monitorare lo stato del ciclo in altri thread, gestire lo stato di thread locale, completare gli oggetti di thread locali, controllare il livello di concorrenza e così via. I tipi di supporto che consentono di utilizzare queste funzionalità prevedono <xref:System.Threading.Tasks.ParallelLoopState>, <xref:System.Threading.Tasks.ParallelOptions>, <xref:System.Threading.Tasks.ParallelLoopResult>, <xref:System.Threading.CancellationToken> e <xref:System.Threading.CancellationTokenSource>.  
  
 Per altre informazioni, vedere il [Documento contenente una panoramica dei modelli per la programmazione parallela, ovvero come comprendere e applicare modelli paralleli con .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=19222).  
  
 Il parallelismo dei dati con sintassi dichiarativa o di tipo query è supportato da PLINQ. Per altre informazioni, vedere [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Procedura: scrivere un ciclo Parallel.For semplice](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)|Descrive come scrivere un ciclo <xref:System.Threading.Tasks.Parallel.For%2A> su qualsiasi matrice o raccolta dell'origine <xref:System.Collections.Generic.IEnumerable%601> indicizzabile.|  
|[Procedura: scrivere un ciclo Parallel.ForEach semplice](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-foreach-loop.md)|Descrive come scrivere un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A> su qualsiasi raccolta di origine <xref:System.Collections.Generic.IEnumerable%601>.|  
|[Procedura: arrestare o interrompere un ciclo Parallel.For](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd460721(v=vs.100))|Descrive come arrestare o interrompere un ciclo parallelo in modo che tutti i thread siano informati dell'azione.|  
|[Procedura: scrivere un ciclo Parallel.For con variabili di thread locali](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)|Descrive come scrivere un ciclo <xref:System.Threading.Tasks.Parallel.For%2A> in cui ogni thread gestisce una variabile privata che non è visibile a qualsiasi altro thread e come sincronizzare i risultati di tutti i thread quando il ciclo viene completato.|  
|[Procedura: scrivere un ciclo Parallel.ForEach con variabili locali di partizioneHow to: Write a Parallel.ForEach Loop with Partition-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-partition-local-variables.md)|Descrive come scrivere un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A> in cui ogni thread gestisce una variabile privata che non è visibile a qualsiasi altro thread e come sincronizzare i risultati di tutti i thread quando il ciclo viene completato.|  
|[Procedura: annullare un ciclo Parallel.For o ForEach](../../../docs/standard/parallel-programming/how-to-cancel-a-parallel-for-or-foreach-loop.md)|Descrive come annullare un ciclo parallelo tramite un oggetto <xref:System.Threading.CancellationToken?displayProperty=nameWithType>.|  
|[Procedura: aumentare la velocità di corpi di ciclo di dimensioni ridotte](../../../docs/standard/parallel-programming/how-to-speed-up-small-loop-bodies.md)|Descrive come aumentare la velocità di esecuzione nel caso di un corpo di ciclo molto piccolo.|  
|[Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Contiene la panoramica di Task Parallel Library.|  
|[Programmazione parallela](../../../docs/standard/parallel-programming/index.md)|Introduce la Programmazione parallela in .NET Framework.|  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)
