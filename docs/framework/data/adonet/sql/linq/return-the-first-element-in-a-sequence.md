---
title: Restituire il primo elemento di una sequenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 9faeed754942d7b176872484ac776c1df592bbd8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792718"
---
# <a name="return-the-first-element-in-a-sequence"></a>Restituire il primo elemento di una sequenza
Usare l'operatore <xref:System.Linq.Enumerable.First%2A> per restituire il primo elemento in una sequenza. Le query che usano <xref:System.Linq.Enumerable.First%2A> vengono eseguite immediatamente.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta l'operatore <xref:System.Linq.Enumerable.Last%2A>.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene cercato il primo `Shipper` in una tabella:  
  
 Se si esegue questa query sul database di esempio Northwind, i risultati saranno  
  
 [https://login.microsoftonline.com/consumers/](`ID = 1, Company = Speedy Express`).  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene cercato il singolo `Customer` con `CustomerID` BONAP.  
  
 Se si esegue questa query sul database di esempio Northwind, i risultati saranno `ID = BONAP, Contact = Laurence Lebihan`.  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di query](query-examples.md)
- [Download di database di esempio](downloading-sample-databases.md)
