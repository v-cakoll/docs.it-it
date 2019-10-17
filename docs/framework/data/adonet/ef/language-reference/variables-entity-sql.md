---
title: Variabili (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bb8e6ebe81dacc7ec0f45fdde65b9c18cfd76789
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319193"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="05bd6-102">Variabili (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="05bd6-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="05bd6-103">Variabile</span><span class="sxs-lookup"><span data-stu-id="05bd6-103">Variable</span></span>  
 <span data-ttu-id="05bd6-104">Un'espressione variabile è un riferimento a un'espressione denominata definita nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="05bd6-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="05bd6-105">Un riferimento a una variabile deve essere un identificatore di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] valido, come definito negli [identificatori](identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="05bd6-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="05bd6-106">Nell'esempio seguente viene illustrato l'uso di una variabile nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="05bd6-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="05bd6-107">Il valore `c` nella clausola FROM è la definizione della variabile.</span><span class="sxs-lookup"><span data-stu-id="05bd6-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="05bd6-108">L'utilizzo di `c` nella clausola SELECT rappresenta il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="05bd6-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="05bd6-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05bd6-109">See also</span></span>

- [<span data-ttu-id="05bd6-110">Identificatori</span><span class="sxs-lookup"><span data-stu-id="05bd6-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="05bd6-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="05bd6-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="05bd6-112">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="05bd6-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
