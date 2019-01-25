---
title: 'Procedura: Filtrare a livello di DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 66bbfe19c73f116b8f85cae829bb61bb2da3d4c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644218"
---
# <a name="how-to-filter-at-the-datacontext-level"></a>Procedura: Filtrare a livello di DataContext
È possibile filtrare `EntitySets` al livello `DataContext`. Tali filtri si applicano a tutte le query eseguite con quell'istanza di <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> per filtrare gli ordini precaricati per i clienti in base a `ShippedDate`.  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche
- [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
