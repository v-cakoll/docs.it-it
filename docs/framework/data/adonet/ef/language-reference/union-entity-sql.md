---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 52a7a332166250e8fa8084986fd0d89da6fdf42d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764879"
---
# <a name="union-entity-sql"></a><span data-ttu-id="0d3ad-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0d3ad-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="0d3ad-103">Combina i risultati di due o più query in una singola raccolta.</span><span class="sxs-lookup"><span data-stu-id="0d3ad-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d3ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d3ad-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d3ad-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0d3ad-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0d3ad-106">Qualsiasi espressione di query valida che restituisce una raccolta da combinare con le espressioni ALL della raccolta deve essere dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="0d3ad-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="0d3ad-107">UNION</span><span class="sxs-lookup"><span data-stu-id="0d3ad-107">UNION</span></span>  
 <span data-ttu-id="0d3ad-108">Specifica che più raccolte devono essere combinate e restituite come singola raccolta.</span><span class="sxs-lookup"><span data-stu-id="0d3ad-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="0d3ad-109">ALL</span><span class="sxs-lookup"><span data-stu-id="0d3ad-109">ALL</span></span>  
 <span data-ttu-id="0d3ad-110">Specifica che più raccolte devono essere combinate e restituite come singola raccolta, inclusi i duplicati.</span><span class="sxs-lookup"><span data-stu-id="0d3ad-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="0d3ad-111">Se non viene specificato, i duplicati vengono rimossi dalla raccolta dei risultati.</span><span class="sxs-lookup"><span data-stu-id="0d3ad-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d3ad-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0d3ad-112">Return Value</span></span>  
 <span data-ttu-id="0d3ad-113">Raccolta dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="0d3ad-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d3ad-114">Note</span><span class="sxs-lookup"><span data-stu-id="0d3ad-114">Remarks</span></span>  
 <span data-ttu-id="0d3ad-115">UNION è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d3ad-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="0d3ad-116">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="0d3ad-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="0d3ad-117">Per informazioni sulla priorità per il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori sui set, vedere [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0d3ad-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d3ad-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d3ad-118">Example</span></span>  
 <span data-ttu-id="0d3ad-119">Nella query Entity SQL seguente viene usato l'operatore UNION ALL per combinare i risultati di due query in una singola raccolta.</span><span class="sxs-lookup"><span data-stu-id="0d3ad-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="0d3ad-120">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0d3ad-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0d3ad-121">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d3ad-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0d3ad-122">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0d3ad-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="0d3ad-123">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="0d3ad-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="0d3ad-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d3ad-124">See Also</span></span>  
 [<span data-ttu-id="0d3ad-125">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0d3ad-125">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
