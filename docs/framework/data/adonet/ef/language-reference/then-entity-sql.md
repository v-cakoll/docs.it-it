---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: ba01a978c53b58f7e6c1ac9bc42a97277ac64bbc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319290"
---
# <a name="then-entity-sql"></a><span data-ttu-id="3d329-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3d329-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="3d329-103">Risultato di una clausola WHEN quando restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="3d329-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d329-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d329-104">Syntax</span></span>  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3d329-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="3d329-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="3d329-106">Qualsiasi espressione booleana valida.</span><span class="sxs-lookup"><span data-stu-id="3d329-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="3d329-107">Qualsiasi espressione di query valida che restituisce una raccolta.</span><span class="sxs-lookup"><span data-stu-id="3d329-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d329-108">Note</span><span class="sxs-lookup"><span data-stu-id="3d329-108">Remarks</span></span>  
 <span data-ttu-id="3d329-109">Se `when_expression` restituisce il valore `true`, il risultato è l'oggetto `then-expression`corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3d329-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="3d329-110">Se nessuna delle condizioni WHEN è soddisfatta, viene restituito `else-expression` .</span><span class="sxs-lookup"><span data-stu-id="3d329-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="3d329-111">Se, tuttavia, non sono presenti `else-expression`, il risultato è null.</span><span class="sxs-lookup"><span data-stu-id="3d329-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="3d329-112">Per un esempio, vedere [case](case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3d329-112">For an example, see [CASE](case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d329-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d329-113">Example</span></span>  
 <span data-ttu-id="3d329-114">Nella query Entity SQL seguente viene usata l'espressione CASE per valutare un set di espressioni `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="3d329-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="3d329-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3d329-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3d329-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d329-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3d329-117">Attenersi alla procedura descritta in [procedura: eseguire una query che restituisce i risultati di PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3d329-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="3d329-118">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3d329-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="3d329-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d329-119">See also</span></span>

- [<span data-ttu-id="3d329-120">CASE</span><span class="sxs-lookup"><span data-stu-id="3d329-120">CASE</span></span>](case-entity-sql.md)
- [<span data-ttu-id="3d329-121">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3d329-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
