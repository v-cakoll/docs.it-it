---
title: Variabili (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 88ee41bc08711cf84b8b2e273c9ac0f4267d1d34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149817"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="de836-102">Variabili (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="de836-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="de836-103">Variabile</span><span class="sxs-lookup"><span data-stu-id="de836-103">Variable</span></span>  
 <span data-ttu-id="de836-104">Un'espressione variabile è un riferimento a un'espressione denominata definita nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="de836-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="de836-105">Un riferimento a una [!INCLUDE[esql](../../../../../../includes/esql-md.md)] variabile deve essere un identificatore valido, come definito in [Identificatori](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="de836-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="de836-106">Nell'esempio seguente viene illustrato l'uso di una variabile nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="de836-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="de836-107">Il valore `c` nella clausola FROM è la definizione della variabile.</span><span class="sxs-lookup"><span data-stu-id="de836-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="de836-108">L'utilizzo di `c` nella clausola SELECT rappresenta il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="de836-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="de836-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de836-109">See also</span></span>

- [<span data-ttu-id="de836-110">Identificatori</span><span class="sxs-lookup"><span data-stu-id="de836-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="de836-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="de836-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="de836-112">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="de836-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
