---
title: 'Procedura: aumentare la velocità di corpi di ciclo di dimensioni ridotte'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
ms.openlocfilehash: 29d7fa8200ddd972c1a5c98ea6f30a7c8ff732e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139757"
---
# <a name="how-to-speed-up-small-loop-bodies"></a>Procedura: aumentare la velocità di corpi di ciclo di dimensioni ridotte
La velocità dei cicli <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> con un corpo di dimensioni ridotte può risultare minore rispetto alla velocità dei cicli sequenziali equivalenti, come il ciclo [for](../../csharp/language-reference/keywords/for.md) in C# e il ciclo [For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) in Visual Basic. La minore velocità è dovuta all'overhead necessario per eseguire il partizionamento dei dati e al costo associato alla chiamata di un delegato a ogni iterazione del ciclo. Per gestire tali scenari, la classe <xref:System.Collections.Concurrent.Partitioner> fornisce il metodo <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> che consente di fornire un ciclo sequenziale per il corpo del delegato in modo che il delegato venga richiamato soltanto una volta per partizione, anziché una volta per iterazione. Per altre informazioni, vedere [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 L'approccio descritto in questo esempio è utile quando il ciclo esegue una quantità minima di lavoro. Quando il lavoro diventa più dispendioso in termini di calcolo, l'uso di un ciclo <xref:System.Threading.Tasks.Parallel.For%2A> o <xref:System.Threading.Tasks.Parallel.ForEach%2A> con il partitioner predefinito offrirà probabilmente prestazioni simili o migliori.  
  
## <a name="see-also"></a>Vedere anche

- [Parallelismo dei dati](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
- [Iteratori (C#)](../../csharp/programming-guide/concepts/iterators.md)
- [Iteratori [Visual Basic]](../../visual-basic/programming-guide/concepts/iterators.md)
- [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
