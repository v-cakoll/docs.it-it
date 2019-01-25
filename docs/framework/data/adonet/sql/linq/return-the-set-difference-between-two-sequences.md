---
title: Restituire la differenza dei set tra due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 282ec36a2ad489e77db9fb5b338d3189c3001f03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609031"
---
# <a name="return-the-set-difference-between-two-sequences"></a>Restituire la differenza dei set tra due sequenze
Per restituire la differenza dei set tra due sequenze, usare l'operatore <xref:System.Linq.Queryable.Except%2A>.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato <xref:System.Linq.Queryable.Except%2A> per restituire una sequenza di tutti i paesi in cui sono presenti `Customers` ma non `Employees`.  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] l'operazione <xref:System.Linq.Queryable.Except%2A> è definita correttamente solo sui set, mentre la semantica per i tipi multiset non è definita.  
  
## <a name="see-also"></a>Vedere anche
- [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Conversione dell'operatore query standard](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
