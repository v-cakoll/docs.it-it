---
title: WHERE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: b551d15d7de2cf07afc7455b7fd0a0faf6436ccf
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319189"
---
# <a name="where-entity-sql"></a><span data-ttu-id="dde7c-102">WHERE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dde7c-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="dde7c-103">La clausola WHERE viene applicata direttamente dopo la clausola [from](from-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="dde7c-103">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dde7c-104">Syntax</span></span>  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="dde7c-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="dde7c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="dde7c-106">Tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="dde7c-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dde7c-107">Note</span><span class="sxs-lookup"><span data-stu-id="dde7c-107">Remarks</span></span>  
 <span data-ttu-id="dde7c-108">La clausola WHERE ha la stessa semantica descritta per Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="dde7c-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="dde7c-109">Questa clausola consente di ridurre gli oggetti prodotti dall'espressione di query limitando gli elementi delle raccolte di origine a quelli che soddisfano la condizione.</span><span class="sxs-lookup"><span data-stu-id="dde7c-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```sql  
select c from cs as c where e  
```  
  
 <span data-ttu-id="dde7c-110">L'espressione `e` deve essere di tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="dde7c-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="dde7c-111">La clausola WHERE viene applicata direttamente dopo la clausola FROM e prima che avvenga qualsiasi operazione di  raggruppamento, ordinamento o proiezione.</span><span class="sxs-lookup"><span data-stu-id="dde7c-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="dde7c-112">Tutti i nomi degli elementi definiti nella clausola FROM sono visibili all'espressione della clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="dde7c-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde7c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dde7c-113">See also</span></span>

- [<span data-ttu-id="dde7c-114">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="dde7c-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="dde7c-115">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="dde7c-115">Query Expressions</span></span>](query-expressions-entity-sql.md)
