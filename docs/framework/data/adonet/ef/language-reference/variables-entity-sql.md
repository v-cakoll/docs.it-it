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
# <a name="variables-entity-sql"></a><span data-ttu-id="9e21d-102">Variabili (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9e21d-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="9e21d-103">Variabile</span><span class="sxs-lookup"><span data-stu-id="9e21d-103">Variable</span></span>  
 <span data-ttu-id="9e21d-104">Un'espressione variabile è un riferimento a un'espressione denominata definita nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="9e21d-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="9e21d-105">Riferimento a una variabile deve essere un valore valido [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificatore, come definito in [identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9e21d-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="9e21d-106">Nell'esempio seguente viene illustrato l'uso di una variabile nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="9e21d-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="9e21d-107">Il valore `c` nella clausola FROM è la definizione della variabile.</span><span class="sxs-lookup"><span data-stu-id="9e21d-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="9e21d-108">L'utilizzo di `c` nella clausola SELECT rappresenta il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="9e21d-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e21d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e21d-109">See also</span></span>
- [<span data-ttu-id="9e21d-110">Identificatori</span><span class="sxs-lookup"><span data-stu-id="9e21d-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [<span data-ttu-id="9e21d-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="9e21d-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [<span data-ttu-id="9e21d-112">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9e21d-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
