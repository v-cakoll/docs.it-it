---
title: Trovare il valore massimo in una sequenza numerica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
ms.openlocfilehash: c93b322c755036c8bf7150bb5c96b9c32b6dc9b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353817"
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a>Trovare il valore massimo in una sequenza numerica
Per trovare il valore massimo in una sequenza di valori numerici, usare l'operatore <xref:System.Linq.Enumerable.Max%2A>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene cercata l'ultima data di assunzione di qualsiasi dipendente.  
  
 Se si esegue questa query sul database di esempio Northwind, l'output sarà: `11/15/1994 12:00:00 AM`.  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene cercato il maggior numero di unità in magazzino per qualsiasi prodotto.  
  
 Se si esegue questa query sul database di esempio Northwind, l'output sarà: `125`.  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato Max per cercare in `Products` gli elementi con il prezzo unitario più elevato di ogni categoria. Nell'output vengono quindi elencati i risultati per categoria.  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 Se si esegue la query precedente sul database di esempio Northwind, i risultati saranno simili ai seguenti:  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a>Vedere anche  
 [Query di aggregazione](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
