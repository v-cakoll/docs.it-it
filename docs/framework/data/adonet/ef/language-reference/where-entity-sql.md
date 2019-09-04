---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 8dd0e34a6669b2147052befb17b8f4ff8395aabc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248477"
---
# <a name="where-entity-sql"></a><span data-ttu-id="6f911-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6f911-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="6f911-103">La clausola WHERE viene applicata direttamente dopo la clausola [from](from-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="6f911-103">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f911-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f911-104">Syntax</span></span>  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6f911-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6f911-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6f911-106">Tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="6f911-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f911-107">Note</span><span class="sxs-lookup"><span data-stu-id="6f911-107">Remarks</span></span>  
 <span data-ttu-id="6f911-108">La clausola WHERE ha la stessa semantica descritta per Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="6f911-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="6f911-109">Questa clausola consente di ridurre gli oggetti prodotti dall'espressione di query limitando gli elementi delle raccolte di origine a quelli che soddisfano la condizione.</span><span class="sxs-lookup"><span data-stu-id="6f911-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```  
select c from cs as c where e  
```  
  
 <span data-ttu-id="6f911-110">L'espressione `e` deve essere di tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="6f911-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="6f911-111">La clausola WHERE viene applicata direttamente dopo la clausola FROM e prima che avvenga qualsiasi operazione di  raggruppamento, ordinamento o proiezione.</span><span class="sxs-lookup"><span data-stu-id="6f911-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="6f911-112">Tutti i nomi degli elementi definiti nella clausola FROM sono visibili all'espressione della clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="6f911-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f911-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f911-113">See also</span></span>

- [<span data-ttu-id="6f911-114">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6f911-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="6f911-115">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="6f911-115">Query Expressions</span></span>](query-expressions-entity-sql.md)
