---
title: 'Procedura: Recuperare più oggetti contemporaneamente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 48cdb47bec35b5315e03629d3a01657136bf7ed2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781679"
---
# <a name="how-to-retrieve-many-objects-at-once"></a>Procedura: Recuperare più oggetti contemporaneamente
È possibile recuperare molti oggetti in una sola query usando <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.  
  
## <a name="example"></a>Esempio  
 Nel codice riportato di seguito viene usato il metodo <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per recuperare gli oggetti `Customer` e `Order`.  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti relativi alle query](query-concepts.md)
