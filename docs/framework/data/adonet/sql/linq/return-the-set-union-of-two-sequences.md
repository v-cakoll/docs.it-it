---
title: Restituire l'unione di set di due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 13e5e821f68e839039569b4ac8a993a20c45ab27
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403947"
---
# <a name="return-the-set-union-of-two-sequences"></a>Restituire l'unione di set di due sequenze
Per restituire l'unione di set di due sequenze, usare l'operatore <xref:System.Linq.Queryable.Union%2A>.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato <xref:System.Linq.Queryable.Union%2A> per restituire una sequenza di tutti i paesi in cui sono presenti `Customers` o `Employees`.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 Nelle [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], il <xref:System.Linq.Queryable.Union%2A> operatore è definito per i tipi multiset come concatenazione non ordinata di multiset, che corrisponde (in effetti al risultato del [ `UNION ALL` ](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) clausola in SQL).  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [Conversione dell'operatore query standard](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
