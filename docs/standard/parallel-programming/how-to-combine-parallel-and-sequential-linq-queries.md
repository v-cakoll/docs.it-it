---
title: 'Procedura: combinare query LINQ parallele e sequenziali'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: 99c86e17c57a90d2268acb2a32c69bc4a693338a
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80587993"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>Procedura: combinare query LINQ parallele e sequenziali
Questo esempio mostra come usare il metodo <xref:System.Linq.ParallelEnumerable.AsSequential%2A> per indicare a PLINQ di elaborare tutti gli operatori successivi nella query in modo sequenziale. Anche se l'elaborazione sequenziale è generalmente più lenta di quella parallela, a volte è necessaria per produrre risultati corretti.  
  
> [!WARNING]
> Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra uno scenario in cui è necessario usare <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, in particolare per mantenere l'ordinamento stabilito in una clausola precedente della query.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare ed eseguire il codice, incollarlo nel progetto [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md), aggiungere una riga per chiamare il metodo da `Main` e quindi premere F5.  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
