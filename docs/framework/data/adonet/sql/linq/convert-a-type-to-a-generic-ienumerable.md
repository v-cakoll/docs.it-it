---
title: Convertire un tipo in un IEnumerable generico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: c92f65c22fe4b4128a171c757bb9e9c0ccbc3fee
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247724"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a>Convertire un tipo in un IEnumerable generico
Usare <xref:System.Linq.Enumerable.AsEnumerable%2A> per restituire l'argomento tipizzato come `IEnumerable` generico.  
  
## <a name="example"></a>Esempio  
 In questo esempio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tenta di convertire la query in SQL e di eseguirla sul server usando il tipo `Query` generico predefinito. La clausola `where`, tuttavia, fa riferimento a un metodo sul lato client definito dall'utente (`isValidProduct`) che non può essere convertito in SQL.  
  
 La soluzione consiste nello specificare l'implementazione di <xref:System.Collections.Generic.IEnumerable%601> del tipo `where` generico sul lato client per sostituire il tipo <xref:System.Linq.IQueryable%601> generico. Per eseguire questa operazione, richiamare l'operatore <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di query](query-examples.md)
