---
title: FLATTEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 467277a1697f9f6ca4da7278045cbec34202eed5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="97843-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="97843-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="97843-103">Converte una raccolta di raccolte in una raccolta bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="97843-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="97843-104">La nuova raccolta contiene tutti gli stessi elementi di quella vecchia, ma senza una struttura annidata.</span><span class="sxs-lookup"><span data-stu-id="97843-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97843-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97843-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="97843-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="97843-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="97843-107">Qualsiasi espressione valida che restituisce una raccolta di valori da inserire in un'unica raccolta bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="97843-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97843-108">Note</span><span class="sxs-lookup"><span data-stu-id="97843-108">Remarks</span></span>  
 <span data-ttu-id="97843-109">`FLATTEN` è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97843-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="97843-110">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="97843-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="97843-111">Vedere [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) per informazioni sulla priorità per il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori sui set.</span><span class="sxs-lookup"><span data-stu-id="97843-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97843-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="97843-112">Example</span></span>  
 <span data-ttu-id="97843-113">Nella query Entity SQL seguente viene usato l'operatore `FLATTEN` per convertire una raccolta di raccolte in una raccolta bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="97843-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="97843-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="97843-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="97843-115">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="97843-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="97843-116">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="97843-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="97843-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97843-117">See Also</span></span>  
 [<span data-ttu-id="97843-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="97843-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
