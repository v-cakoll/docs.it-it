---
title: Contare il numero di elementi in una sequenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 74e24aeb64b0097cba3975e76475034e6bb9544d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247697"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a>Contare il numero di elementi in una sequenza
Usare l'operatore <xref:System.Linq.Enumerable.Count%2A> per conteggiare il numero di elementi in una sequenza.  
  
 L'esecuzione di questa query sul database di esempio Northwind produce un output pari a `91`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene conteggiato il numero di `Customers` nel database.  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene conteggiato il numero di prodotti nel database che non sono stati rimossi.  
  
 L'esecuzione di questo esempio sul database di esempio Northwind produce un output pari a `69`.  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Query di aggregazione](aggregate-queries.md)
- [Download di database di esempio](downloading-sample-databases.md)
