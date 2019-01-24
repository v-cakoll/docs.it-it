---
title: 'Procedura: Recuperare molti oggetti contemporaneamente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 31091b6634c9d95c008929680620fb66d95d473c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653788"
---
# <a name="how-to-retrieve-many-objects-at-once"></a>Procedura: Recuperare molti oggetti contemporaneamente
È possibile recuperare molti oggetti in una sola query usando <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.  
  
## <a name="example"></a>Esempio  
 Nel codice riportato di seguito viene usato il metodo <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per recuperare gli oggetti `Customer` e `Order`.  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche
- [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
