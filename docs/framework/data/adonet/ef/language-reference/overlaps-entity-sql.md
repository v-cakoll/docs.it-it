---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: bdee9281fd406a3d029d3a10536cbdd48d2f7a58
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319419"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="d1c8b-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d1c8b-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="d1c8b-103">Determina se due raccolte includono elementi comuni.</span><span class="sxs-lookup"><span data-stu-id="d1c8b-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1c8b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1c8b-104">Syntax</span></span>  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d1c8b-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="d1c8b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d1c8b-106">Qualsiasi espressione di query valida che restituisce una raccolta da confrontare con la raccolta restituita da un'altra espressione di query.</span><span class="sxs-lookup"><span data-stu-id="d1c8b-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="d1c8b-107">Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="d1c8b-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1c8b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d1c8b-108">Return Value</span></span>  
 <span data-ttu-id="d1c8b-109">`true` se le due raccolte includono elementi comuni; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d1c8b-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1c8b-110">Note</span><span class="sxs-lookup"><span data-stu-id="d1c8b-110">Remarks</span></span>  
 <span data-ttu-id="d1c8b-111">SOVRAPPOSIZIONI fornisce un equivalente dal punto di vista funzionale a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="d1c8b-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="d1c8b-112">OVERLAPS è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1c8b-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="d1c8b-113">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="d1c8b-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="d1c8b-114">Per informazioni sulla precedenza per gli operatori set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vedere [except](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d1c8b-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1c8b-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1c8b-115">Example</span></span>  
 <span data-ttu-id="d1c8b-116">Nella query Entity SQL seguente viene usato l'operatore OVERLAPS per determinare se due raccolte hanno un valore comune.</span><span class="sxs-lookup"><span data-stu-id="d1c8b-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="d1c8b-117">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d1c8b-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d1c8b-118">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1c8b-118">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="d1c8b-119">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d1c8b-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d1c8b-120">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d1c8b-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="d1c8b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1c8b-121">See also</span></span>

- [<span data-ttu-id="d1c8b-122">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d1c8b-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
