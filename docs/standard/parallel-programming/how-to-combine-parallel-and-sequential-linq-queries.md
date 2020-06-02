---
title: 'Procedura: Combinare query LINQ parallele e sequenziali'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: 2bdf074bc2977dc501e0726a52e825c89828565f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289538"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>Procedura: Combinare query LINQ parallele e sequenziali

Questo esempio mostra come usare il metodo <xref:System.Linq.ParallelEnumerable.AsSequential%2A> per indicare a PLINQ di elaborare tutti gli operatori successivi nella query in modo sequenziale. Anche se l'elaborazione sequenziale è spesso più lenta di quella parallela, a volte è necessario produrre risultati corretti.  
  
> [!NOTE]
> Questo esempio ha lo scopo di illustrare l'utilizzo e potrebbe non essere eseguito più velocemente rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra uno scenario in cui è necessario usare <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, in particolare per mantenere l'ordinamento stabilito in una clausola precedente della query.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare ed eseguire il codice, incollarlo nel progetto [PLINQ Data Sample](plinq-data-sample.md) , aggiungere una riga per chiamare il metodo da `Main` e premere **F5**.  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
