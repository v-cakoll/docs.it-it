---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 9d4cdeac317509fd61741a19276a6764a1c2bfce
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319346"
---
# <a name="set-entity-sql"></a><span data-ttu-id="9b1c7-102">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9b1c7-102">SET (Entity SQL)</span></span>
<span data-ttu-id="9b1c7-103">L'espressione SET viene usata per convertire una raccolta di oggetti in un set restituendo una nuova raccolta da cui sono stati rimossi tutti i duplicati.</span><span class="sxs-lookup"><span data-stu-id="9b1c7-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b1c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b1c7-104">Syntax</span></span>  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="9b1c7-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="9b1c7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9b1c7-106">Qualsiasi espressione di query valida che restituisce una raccolta.</span><span class="sxs-lookup"><span data-stu-id="9b1c7-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b1c7-107">Note</span><span class="sxs-lookup"><span data-stu-id="9b1c7-107">Remarks</span></span>  
 <span data-ttu-id="9b1c7-108">L'espressione set `SET(c)` equivale, dal punto di vista logico,  all'istruzione Select seguente:</span><span class="sxs-lookup"><span data-stu-id="9b1c7-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 <span data-ttu-id="9b1c7-109">`SET` è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b1c7-109">`SET` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="9b1c7-110">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="9b1c7-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="9b1c7-111">Vedere [ad eccezione](except-entity-sql.md) delle informazioni di precedenza per gli operatori set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b1c7-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b1c7-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b1c7-112">Example</span></span>  
 <span data-ttu-id="9b1c7-113">Nella query Entity SQL seguente viene usata l'espressione SET per convertire una raccolta di oggetti in un set.</span><span class="sxs-lookup"><span data-stu-id="9b1c7-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="9b1c7-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9b1c7-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9b1c7-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b1c7-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9b1c7-116">Attenersi alla procedura descritta in [procedura: eseguire una query che restituisce i risultati di PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9b1c7-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="9b1c7-117">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="9b1c7-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a><span data-ttu-id="9b1c7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b1c7-118">See also</span></span>

- [<span data-ttu-id="9b1c7-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9b1c7-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
