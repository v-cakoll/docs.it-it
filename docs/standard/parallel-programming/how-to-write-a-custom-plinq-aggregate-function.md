---
title: 'Procedura: scrivere una funzione di aggregazione PLINQ personalizzata'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
ms.openlocfilehash: 7bb4cc1b69f0b6b97c1cf6255ded5341304f3ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106761"
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>Procedura: scrivere una funzione di aggregazione PLINQ personalizzata
Questo esempio mostra come usare il metodo <xref:System.Linq.ParallelEnumerable.Aggregate%2A> per applicare una funzione di aggregazione personalizzata a una sequenza di origine.  
  
> [!WARNING]
> Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente calcola la deviazione standard di una sequenza di numeri interi.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 L'esempio usa un overload dell'operatore query standard Aggregate specifico di PLINQ. Questo overload accetta un oggetto <xref:System.Func%603?displayProperty=nameWithType> aggiuntivo come terzo parametro di input. Questo delegato combina i risultati di tutti i thread prima di eseguire il calcolo finale sui risultati aggregati. In questo esempio si sommano i totali di tutti i thread.  
  
 Si noti che quando il corpo di un'espressione lambda è costituito da una singola espressione, il valore restituito dal delegato <xref:System.Func%602?displayProperty=nameWithType> è il valore dell'espressione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
