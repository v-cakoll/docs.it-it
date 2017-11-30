---
title: 'Procedura: scrivere una funzione di aggregazione PLINQ personalizzata'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, how to create aggregate function
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b098f21e29d0d59cd99ddbb64af6246d9953a3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-custom-plinq-aggregate-function"></a>Procedura: scrivere una funzione di aggregazione PLINQ personalizzata
In questo esempio viene illustrato come utilizzare il <xref:System.Linq.ParallelEnumerable.Aggregate%2A> per applicare una funzione di aggregazione personalizzata a una sequenza di origine.  
  
> [!WARNING]
>  Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente calcola la deviazione standard di una sequenza di numeri interi.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 In questo esempio viene usato un overload dell'operatore di query standard di aggregazione che è univoco in PLINQ. Questo overload accetta un ulteriore <xref:System.Func%603?displayProperty=nameWithType> come terzo parametro di input. Questo delegato combina i risultati di tutti i thread, prima di eseguire il calcolo finale i risultati aggregati. In questo esempio si sommano le somme da tutti i thread.  
  
 Si noti che quando un corpo di espressione lambda è costituito da un'unica espressione, il valore restituito di <xref:System.Func%602?displayProperty=nameWithType> delegato è il valore dell'espressione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
