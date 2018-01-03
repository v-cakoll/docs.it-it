---
title: Espressioni non supportate (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d80fc4fa3c0e57cfa10ead494248ae1966e28769
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="unsupported-expressions-entity-sql"></a>Espressioni non supportate (Entity SQL)
In questo argomento vengono descritte le espressioni [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] non supportate in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Per ulteriori informazioni, vedere [Entity SQL differenze di Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).  
  
## <a name="quantified-predicates"></a>Predicati quantificati  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] consente i costrutti con il formato seguente:  
  
```  
sal > all (select salary from employees)  
sal > any (select salary from employees)  
```  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], tuttavia, tali costrutti non sono supportati. È possibile scrivere espressioni equivalenti in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] come indicato di seguito:  
  
```  
not exists(select 0 from employees as e where sal > e.salary)  
exists(select 0 from employees as e where sal > e.salary)  
```  
  
## <a name="-operator"></a>Operatore *  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] supporta l'uso dell'operatore * nella clausola SELECT per indicare che tutte le colonne devono essere proiettate. Questa opzione non è supportata in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Differenze tra Entity SQL e Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
