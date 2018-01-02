---
title: WHERE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2ad170500770bc370eb67a04ab29d0c9f9dcaabd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="where-entity-sql"></a><span data-ttu-id="87943-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="87943-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="87943-103">La clausola WHERE viene applicata direttamente dopo il [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clausola.</span><span class="sxs-lookup"><span data-stu-id="87943-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87943-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87943-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="87943-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="87943-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="87943-106">Tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="87943-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87943-107">Note</span><span class="sxs-lookup"><span data-stu-id="87943-107">Remarks</span></span>  
 <span data-ttu-id="87943-108">La clausola WHERE dispone della stessa semantica descritta per [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87943-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="87943-109">Questa clausola consente di ridurre gli oggetti prodotti dall'espressione di query limitando gli elementi delle raccolte di origine a quelli che soddisfano la condizione.</span><span class="sxs-lookup"><span data-stu-id="87943-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="87943-110">L'espressione `e` deve essere di tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="87943-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="87943-111">La clausola WHERE viene applicata direttamente dopo la clausola FROM e prima che avvenga qualsiasi operazione di  raggruppamento, ordinamento o proiezione.</span><span class="sxs-lookup"><span data-stu-id="87943-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="87943-112">Tutti i nomi degli elementi definiti nella clausola FROM sono visibili all'espressione della clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="87943-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87943-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87943-113">See Also</span></span>  
 [<span data-ttu-id="87943-114">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="87943-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="87943-115">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="87943-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
