---
title: Variabili (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 5be9c80c2fce877f179d79f6b2c22f11e31e65a0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248696"
---
# <a name="variables-entity-sql"></a>Variabili (Entity SQL)
## <a name="variable"></a>Variabile  
 Un'espressione variabile è un riferimento a un'espressione denominata definita nell'ambito corrente. Un riferimento a una variabile deve essere [!INCLUDE[esql](../../../../../../includes/esql-md.md)] un identificatore valido, come definito negli [identificatori](identifiers-entity-sql.md).  
  
 Nell'esempio seguente viene illustrato l'uso di una variabile nell'espressione. Il valore `c` nella clausola FROM è la definizione della variabile. L'utilizzo di `c` nella clausola SELECT rappresenta il riferimento alla variabile.  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>Vedere anche

- [Identificatori](identifiers-entity-sql.md)
- [Parametri](parameters-entity-sql.md)
- [Panoramica di Entity SQL](entity-sql-overview.md)
