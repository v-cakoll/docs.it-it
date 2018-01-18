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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d035f8d5616f2eb4c5a4db31857da2be0cd3d930
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="variables-entity-sql"></a><span data-ttu-id="edb8d-102">Variabili (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="edb8d-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="edb8d-103">Variabile</span><span class="sxs-lookup"><span data-stu-id="edb8d-103">Variable</span></span>  
 <span data-ttu-id="edb8d-104">Un'espressione variabile è un riferimento a un'espressione denominata definita nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="edb8d-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="edb8d-105">Riferimento a una variabile deve essere valido [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificatore, come definito in [identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="edb8d-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="edb8d-106">Nell'esempio seguente viene illustrato l'uso di una variabile nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="edb8d-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="edb8d-107">Il valore `c` nella clausola FROM è la definizione della variabile.</span><span class="sxs-lookup"><span data-stu-id="edb8d-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="edb8d-108">L'utilizzo di `c` nella clausola SELECT rappresenta il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="edb8d-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="edb8d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edb8d-109">See Also</span></span>  
 [<span data-ttu-id="edb8d-110">Identificatori</span><span class="sxs-lookup"><span data-stu-id="edb8d-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
 [<span data-ttu-id="edb8d-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="edb8d-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
 [<span data-ttu-id="edb8d-112">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="edb8d-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
