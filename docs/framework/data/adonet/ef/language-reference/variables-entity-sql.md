---
title: Variabili (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: fff24c4572fab483c701a93167c0f229d5111d61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="variables-entity-sql"></a>Variabili (Entity SQL)
## <a name="variable"></a>Variabile  
 Un'espressione variabile è un riferimento a un'espressione denominata definita nell'ambito corrente. Riferimento a una variabile deve essere valido [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificatore, come definito in [identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 Nell'esempio seguente viene illustrato l'uso di una variabile nell'espressione. Il valore `c` nella clausola FROM è la definizione della variabile. L'utilizzo di `c` nella clausola SELECT rappresenta il riferimento alla variabile.  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
 [Parametri](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
