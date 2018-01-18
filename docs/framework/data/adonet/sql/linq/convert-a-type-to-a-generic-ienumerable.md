---
title: Convertire un tipo in un IEnumerable generico
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fa15e1336c31aec47fb2255f224146b9ac7e429d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a>Convertire un tipo in un IEnumerable generico
Usare <xref:System.Linq.Enumerable.AsEnumerable%2A> per restituire l'argomento tipizzato come `IEnumerable` generico.  
  
## <a name="example"></a>Esempio  
 In questo esempio [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tenta di convertire la query in SQL e di eseguirla sul server usando il tipo `Query` generico predefinito. La clausola `where`, tuttavia, fa riferimento a un metodo sul lato client definito dall'utente (`isValidProduct`) che non può essere convertito in SQL.  
  
 La soluzione consiste nello specificare l'implementazione di <xref:System.Collections.Generic.IEnumerable%601> del tipo `where` generico sul lato client per sostituire il tipo <xref:System.Linq.IQueryable%601> generico. Per eseguire questa operazione, richiamare l'operatore <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
