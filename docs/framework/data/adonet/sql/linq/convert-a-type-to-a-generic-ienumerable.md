---
title: Convertire un tipo in un IEnumerable generico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: d75c9b9123b52b3e241bea1bbd1d302c406715e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190379"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a>Convertire un tipo in un IEnumerable generico
Usare <xref:System.Linq.Enumerable.AsEnumerable%2A> per restituire l'argomento tipizzato come `IEnumerable` generico.  
  
## <a name="example"></a>Esempio  
 In questo esempio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tenta di convertire la query in SQL e di eseguirla sul server usando il tipo `Query` generico predefinito. La clausola `where`, tuttavia, fa riferimento a un metodo sul lato client definito dall'utente (`isValidProduct`) che non può essere convertito in SQL.  
  
 La soluzione consiste nello specificare l'implementazione di <xref:System.Collections.Generic.IEnumerable%601> del tipo `where` generico sul lato client per sostituire il tipo <xref:System.Linq.IQueryable%601> generico. Per eseguire questa operazione, richiamare l'operatore <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
