---
title: Variabili (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bf6fa95e38d1eb5817fd67165b6993cbb0755fd1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153582"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="94f4a-102">Variabili (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="94f4a-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="94f4a-103">Variabile</span><span class="sxs-lookup"><span data-stu-id="94f4a-103">Variable</span></span>  
 <span data-ttu-id="94f4a-104">Un'espressione variabile è un riferimento a un'espressione denominata definita nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="94f4a-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="94f4a-105">Riferimento a una variabile deve essere un valore valido [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificatore, come definito in [identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="94f4a-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="94f4a-106">Nell'esempio seguente viene illustrato l'uso di una variabile nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="94f4a-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="94f4a-107">Il valore `c` nella clausola FROM è la definizione della variabile.</span><span class="sxs-lookup"><span data-stu-id="94f4a-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="94f4a-108">L'utilizzo di `c` nella clausola SELECT rappresenta il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="94f4a-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="94f4a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94f4a-109">See also</span></span>

- [<span data-ttu-id="94f4a-110">Identificatori</span><span class="sxs-lookup"><span data-stu-id="94f4a-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [<span data-ttu-id="94f4a-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="94f4a-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [<span data-ttu-id="94f4a-112">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="94f4a-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
