---
title: Restituire l'intersezione tra set di due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 944d0b2efe1e74f901a493d1c3202d0f180d599d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792709"
---
# <a name="return-the-set-intersection-of-two-sequences"></a>Restituire l'intersezione tra set di due sequenze
Per restituire l'intersezione di due sequenze, usare l'operatore <xref:System.Linq.Queryable.Intersect%2A>.  
  
## <a name="example"></a>Esempio  
 In questo esempio <xref:System.Linq.Queryable.Intersect%2A> viene usato per restituire una sequenza di tutti i paesi/aree `Customers` in `Employees` cui sono presenti sia che Live.  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] l'operazione <xref:System.Linq.Queryable.Intersect%2A> è definita correttamente solo sui set, mentre la semantica per i tipi multiset non è definita.  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di query](query-examples.md)
- [Conversione dell'operatore query standard](standard-query-operator-translation.md)
