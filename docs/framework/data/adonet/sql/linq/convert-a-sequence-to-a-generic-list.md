---
title: Convertire una sequenza un tipo in un elenco generico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 326b4360323f306d07a3b47df506c6427a980a32
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630788"
---
# <a name="convert-a-sequence-to-a-generic-list"></a>Convertire una sequenza un tipo in un elenco generico
Usare <xref:System.Linq.Enumerable.ToList%2A> per creare un elenco generico da una sequenza.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.ToList%2A> per valutare immediatamente una query in un oggetto <xref:System.Collections.Generic.List%601> generico.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>Vedere anche
- [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
