---
title: Variabili (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: a16c450401eee1021aeef885fba129c943a87fd7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742271"
---
# <a name="variables-entity-sql"></a>Variabili (Entity SQL)
## <a name="variable"></a>Variabile  
 Un'espressione variabile è un riferimento a un'espressione denominata definita nell'ambito corrente. Riferimento a una variabile deve essere un valore valido [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificatore, come definito in [identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 Nell'esempio seguente viene illustrato l'uso di una variabile nell'espressione. Il valore `c` nella clausola FROM è la definizione della variabile. L'utilizzo di `c` nella clausola SELECT rappresenta il riferimento alla variabile.  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Vedere anche
- [Identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [Parametri](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
