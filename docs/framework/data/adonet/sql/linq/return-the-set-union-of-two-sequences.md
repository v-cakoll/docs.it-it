---
title: Restituire l'unione di set di due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 1b981d3002cf4a23897ce98927aebe96086f8a4a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781224"
---
# <a name="return-the-set-union-of-two-sequences"></a>Restituire l'unione di set di due sequenze
Per restituire l'unione di set di due sequenze, usare l'operatore <xref:System.Linq.Queryable.Union%2A>.  
  
## <a name="example"></a>Esempio  
 In questo esempio <xref:System.Linq.Queryable.Union%2A> viene usato per restituire una sequenza di tutti i paesi/aree in cui `Customers` sono `Employees`presenti o.  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]l' [`UNION ALL`](https://docs.microsoft.com/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) operatore viene definito per i set di impostazioni come concatenazione non ordinata dei set di impostazioni (in effetti il risultato della clausola in SQL). <xref:System.Linq.Queryable.Union%2A>

Per ulteriori informazioni ed esempi, vedere <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Vedere anche

- [Esempi di query](query-examples.md)
- [Conversione dell'operatore query standard](standard-query-operator-translation.md)
