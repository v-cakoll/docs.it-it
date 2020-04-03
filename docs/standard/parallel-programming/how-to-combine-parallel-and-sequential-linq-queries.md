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
ms.openlocfilehash: 074714b1152c8804ee1e747104dbaf47f4645546
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635862"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>Procedura: combinare query LINQ parallele e sequenziali

Questo esempio mostra come usare il metodo <xref:System.Linq.ParallelEnumerable.AsSequential%2A> per indicare a PLINQ di elaborare tutti gli operatori successivi nella query in modo sequenziale. Anche se l'elaborazione sequenziale è spesso più lenta del parallelo, a volte è necessario produrre risultati corretti.  
  
> [!NOTE]
> Questo esempio ha lo scopo di illustrare l'utilizzo e potrebbe non essere eseguito più velocemente della query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra uno scenario in cui è necessario usare <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, in particolare per mantenere l'ordinamento stabilito in una clausola precedente della query.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare ed eseguire questo codice, incollarlo nel progetto [PLINQ Data Sample,](../../../docs/standard/parallel-programming/plinq-data-sample.md) aggiungere una riga per chiamare il metodo da `Main`e premere **F5**.  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
