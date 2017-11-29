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
ms.openlocfilehash: 551b6d6feab6829c9a2f6f2e89e1918acf463411
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="variables-entity-sql"></a><span data-ttu-id="0866c-102">Variabili (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0866c-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="0866c-103">Variabile</span><span class="sxs-lookup"><span data-stu-id="0866c-103">Variable</span></span>  
 <span data-ttu-id="0866c-104">Un'espressione variabile è un riferimento a un'espressione denominata definita nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="0866c-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="0866c-105">Riferimento a una variabile deve essere valido [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identificatore, come definito in [identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0866c-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="0866c-106">Nell'esempio seguente viene illustrato l'uso di una variabile nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="0866c-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="0866c-107">Il valore `c` nella clausola FROM è la definizione della variabile.</span><span class="sxs-lookup"><span data-stu-id="0866c-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="0866c-108">L'utilizzo di `c` nella clausola SELECT rappresenta il riferimento alla variabile.</span><span class="sxs-lookup"><span data-stu-id="0866c-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="0866c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0866c-109">See Also</span></span>  
 [<span data-ttu-id="0866c-110">Identificatori</span><span class="sxs-lookup"><span data-stu-id="0866c-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
 [<span data-ttu-id="0866c-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="0866c-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
 [<span data-ttu-id="0866c-112">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0866c-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
