---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: 8d2d7f9a3a1d6ff9f25db3f19bf8f39781469f9f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305624"
---
# <a name="then-entity-sql"></a><span data-ttu-id="3738d-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3738d-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="3738d-103">Risultato di una clausola WHEN quando restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="3738d-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3738d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3738d-104">Syntax</span></span>  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3738d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3738d-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="3738d-106">Qualsiasi espressione booleana valida.</span><span class="sxs-lookup"><span data-stu-id="3738d-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="3738d-107">Qualsiasi espressione di query valida che restituisce una raccolta.</span><span class="sxs-lookup"><span data-stu-id="3738d-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3738d-108">Note</span><span class="sxs-lookup"><span data-stu-id="3738d-108">Remarks</span></span>  
 <span data-ttu-id="3738d-109">Se `when_expression` restituisce il valore `true`, il risultato è l'oggetto `then-expression`corrispondente.</span><span class="sxs-lookup"><span data-stu-id="3738d-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="3738d-110">Se nessuna delle condizioni WHEN è soddisfatta, viene restituito `else-expression` .</span><span class="sxs-lookup"><span data-stu-id="3738d-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="3738d-111">Se, tuttavia, non sono presenti `else-expression`, il risultato è null.</span><span class="sxs-lookup"><span data-stu-id="3738d-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="3738d-112">Per un esempio, vedere [caso](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3738d-112">For an example, see [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3738d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="3738d-113">Example</span></span>  
 <span data-ttu-id="3738d-114">Nella query Entity SQL seguente viene usata l'espressione CASE per valutare un set di espressioni `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="3738d-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="3738d-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3738d-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3738d-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3738d-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3738d-117">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3738d-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="3738d-118">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3738d-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="3738d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3738d-119">See also</span></span>

- [<span data-ttu-id="3738d-120">CASE</span><span class="sxs-lookup"><span data-stu-id="3738d-120">CASE</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)
- [<span data-ttu-id="3738d-121">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3738d-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
