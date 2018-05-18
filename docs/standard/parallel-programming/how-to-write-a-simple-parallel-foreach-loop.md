---
title: 'Procedura: scrivere un ciclo Parallel.ForEach semplice'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e3fb5fd807971aed014ba98cbb207c4483b93f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Procedura: scrivere un ciclo Parallel.ForEach semplice
Questo esempio mostra come usare un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> per abilitare il parallelismo dei dati in un'origine dati <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ. Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 Un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A> funziona come un ciclo <xref:System.Threading.Tasks.Parallel.For%2A>. La raccolta di origine è partizionata e il lavoro è pianificato in più thread in base all'ambiente di sistema. Più processori ci sono nel sistema, più velocemente viene eseguito il metodo parallelo. Per alcune raccolte di origine, un ciclo sequenziale può risultare più veloce, a seconda delle dimensioni dell'origine e del tipo di attività svolta. Per altre informazioni sulle prestazioni, vedere [Problemi potenziali nel parallelismo di dati e attività](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)  
  
 Per altre informazioni sui cicli paralleli, vedere [Procedura: scrivere un ciclo Parallel.For semplice](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).  
  
 Per usare <xref:System.Threading.Tasks.Parallel.ForEach%2A> con una raccolta non generica, è possibile usare il metodo di estensione <xref:System.Linq.Enumerable.Cast%2A> per convertire la raccolta in una generica, come illustrato nell'esempio seguente:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 È anche possibile usare Parallel LINQ (PLINQ) per parallelizzare l'elaborazione di origini dati <xref:System.Collections.Generic.IEnumerable%601>. PLINQ consente di usare la sintassi di query dichiarativa per esprimere il comportamento di ciclo. Per altre informazioni, vedere [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Copiare e incollare questo codice in un progetto di applicazione console di Visual Studio 2010.  
  
-   Aggiungere un riferimento a System.Drawing.dll  
  
-   Premere F5  
  
## <a name="see-also"></a>Vedere anche  
 [Parallelismo dei dati](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
