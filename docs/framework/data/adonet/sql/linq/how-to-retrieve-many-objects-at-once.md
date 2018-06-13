---
title: 'Procedura: recuperare molti oggetti contemporaneamente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: fbe1632abf56beca5abfa209bdf269c6757f9c7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359904"
---
# <a name="how-to-retrieve-many-objects-at-once"></a>Procedura: recuperare molti oggetti contemporaneamente
È possibile recuperare molti oggetti in una sola query usando <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.  
  
## <a name="example"></a>Esempio  
 Nel codice riportato di seguito viene usato il metodo <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per recuperare gli oggetti `Customer` e `Order`.  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche  
 [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
