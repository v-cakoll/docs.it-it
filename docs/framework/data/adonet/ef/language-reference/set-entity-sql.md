---
title: SET (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 12ce6c47db89fe91fd11a94aa10a47b57b45d736
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="set-entity-sql"></a><span data-ttu-id="3d9df-102">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3d9df-102">SET (Entity SQL)</span></span>
<span data-ttu-id="3d9df-103">L'espressione SET viene usata per convertire una raccolta di oggetti in un set restituendo una nuova raccolta da cui sono stati rimossi tutti i duplicati.</span><span class="sxs-lookup"><span data-stu-id="3d9df-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d9df-104">Syntax</span></span>  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="3d9df-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3d9df-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3d9df-106">Qualsiasi espressione di query valida che restituisce una raccolta.</span><span class="sxs-lookup"><span data-stu-id="3d9df-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d9df-107">Note</span><span class="sxs-lookup"><span data-stu-id="3d9df-107">Remarks</span></span>  
 <span data-ttu-id="3d9df-108">L'espressione set `SET(c)` equivale, dal punto di vista logico,  all'istruzione Select seguente:</span><span class="sxs-lookup"><span data-stu-id="3d9df-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 <span data-ttu-id="3d9df-109">`SET` è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d9df-109">`SET` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="3d9df-110">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="3d9df-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="3d9df-111">Vedere [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) per informazioni sulla priorità per il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori sui set.</span><span class="sxs-lookup"><span data-stu-id="3d9df-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d9df-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d9df-112">Example</span></span>  
 <span data-ttu-id="3d9df-113">Nella query Entity SQL seguente viene usata l'espressione SET per convertire una raccolta di oggetti in un set.</span><span class="sxs-lookup"><span data-stu-id="3d9df-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="3d9df-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3d9df-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3d9df-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d9df-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3d9df-116">Attenersi alla procedura di [procedura: eseguire una Query che restituisce risultati di PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3d9df-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="3d9df-117">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3d9df-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a><span data-ttu-id="3d9df-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d9df-118">See Also</span></span>  
 [<span data-ttu-id="3d9df-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3d9df-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
