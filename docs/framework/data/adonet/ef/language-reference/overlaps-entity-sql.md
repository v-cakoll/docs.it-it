---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: f0c5d79b437ff06603ea10404357aa0b3270bc53
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150774"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="a2a15-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a2a15-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="a2a15-103">Determina se due raccolte includono elementi comuni.</span><span class="sxs-lookup"><span data-stu-id="a2a15-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2a15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2a15-104">Syntax</span></span>  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a2a15-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a2a15-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a2a15-106">Qualsiasi espressione di query valida che restituisce una raccolta da confrontare con la raccolta restituita da un'altra espressione di query.</span><span class="sxs-lookup"><span data-stu-id="a2a15-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="a2a15-107">Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="a2a15-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2a15-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a2a15-108">Return Value</span></span>  
 <span data-ttu-id="a2a15-109">`true` se le due raccolte includono elementi comuni; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a2a15-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2a15-110">Note</span><span class="sxs-lookup"><span data-stu-id="a2a15-110">Remarks</span></span>  
 <span data-ttu-id="a2a15-111">OVERLAPS fornisce funzionalmente equivalente alla seguente:</span><span class="sxs-lookup"><span data-stu-id="a2a15-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="a2a15-112">OVERLAPS è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2a15-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="a2a15-113">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="a2a15-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="a2a15-114">Per informazioni sulla priorità per la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori sui set, vedere [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a2a15-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2a15-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2a15-115">Example</span></span>  
 <span data-ttu-id="a2a15-116">Nella query Entity SQL seguente viene usato l'operatore OVERLAPS per determinare se due raccolte hanno un valore comune.</span><span class="sxs-lookup"><span data-stu-id="a2a15-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="a2a15-117">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a2a15-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a2a15-118">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2a15-118">To compile and run this, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a2a15-119">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a2a15-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="a2a15-120">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a2a15-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="a2a15-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2a15-121">See Also</span></span>  
 [<span data-ttu-id="a2a15-122">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a2a15-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
