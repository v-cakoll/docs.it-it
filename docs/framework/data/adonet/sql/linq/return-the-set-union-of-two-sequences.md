---
title: Restituire l'unione di set di due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 9ade12c42ac6a307c341bc5be26430fb56e51ee5
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380032"
---
# <a name="return-the-set-union-of-two-sequences"></a>Restituire l'unione di set di due sequenze
Per restituire l'unione di set di due sequenze, usare l'operatore <xref:System.Linq.Queryable.Union%2A>.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato <xref:System.Linq.Queryable.Union%2A> per restituire una sequenza di tutti i paesi/aree geografiche in cui sono presenti `Customers` o `Employees`.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 Nelle [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], il <xref:System.Linq.Queryable.Union%2A> operatore è definito per i tipi multiset come concatenazione non ordinata di multiset, che corrisponde (in effetti al risultato del [ `UNION ALL` ](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) clausola in SQL).

Per altre informazioni ed esempi, vedere <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Vedere anche

- [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [Conversione dell'operatore query standard](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
