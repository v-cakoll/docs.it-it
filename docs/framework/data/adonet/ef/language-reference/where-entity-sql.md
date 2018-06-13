---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 43c038e9ff0acfdeff88492aa2ca34fbf4ada94a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764314"
---
# <a name="where-entity-sql"></a><span data-ttu-id="66054-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="66054-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="66054-103">La clausola WHERE viene applicata direttamente dopo il [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clausola.</span><span class="sxs-lookup"><span data-stu-id="66054-103">The WHERE clause is applied directly after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66054-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66054-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="66054-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="66054-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="66054-106">Tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="66054-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66054-107">Note</span><span class="sxs-lookup"><span data-stu-id="66054-107">Remarks</span></span>  
 <span data-ttu-id="66054-108">La clausola WHERE dispone della stessa semantica descritta per [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66054-108">The WHERE clause has the same semantics as described for [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="66054-109">Questa clausola consente di ridurre gli oggetti prodotti dall'espressione di query limitando gli elementi delle raccolte di origine a quelli che soddisfano la condizione.</span><span class="sxs-lookup"><span data-stu-id="66054-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="66054-110">L'espressione `e` deve essere di tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="66054-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="66054-111">La clausola WHERE viene applicata direttamente dopo la clausola FROM e prima che avvenga qualsiasi operazione di  raggruppamento, ordinamento o proiezione.</span><span class="sxs-lookup"><span data-stu-id="66054-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="66054-112">Tutti i nomi degli elementi definiti nella clausola FROM sono visibili all'espressione della clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="66054-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66054-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66054-113">See Also</span></span>  
 [<span data-ttu-id="66054-114">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="66054-114">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="66054-115">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="66054-115">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
