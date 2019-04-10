---
title: CASE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: e44f48d040fc77bf702759be0c53a618cd84f9fc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334887"
---
# <a name="case-entity-sql"></a><span data-ttu-id="1fef2-102">CASE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1fef2-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="1fef2-103">Valuta un set di espressioni `Boolean` per determinare il risultato.</span><span class="sxs-lookup"><span data-stu-id="1fef2-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fef2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fef2-104">Syntax</span></span>  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="1fef2-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1fef2-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="1fef2-106">Segnaposto che indica la possibilità di usare più clausole WHEN `Boolean_expression` THEN `result_expression` .</span><span class="sxs-lookup"><span data-stu-id="1fef2-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="1fef2-107">THEN</span><span class="sxs-lookup"><span data-stu-id="1fef2-107">THEN</span></span> `result_expression`  
 <span data-ttu-id="1fef2-108">È l'espressione restituita quando `Boolean_expression` restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="1fef2-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> `result expression` <span data-ttu-id="1fef2-109">È qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="1fef2-109">is any valid expression.</span></span>  
  
 <span data-ttu-id="1fef2-110">ELSE</span><span class="sxs-lookup"><span data-stu-id="1fef2-110">ELSE</span></span> `else_result_expression`  
 <span data-ttu-id="1fef2-111">Espressione restituita se nessuna operazione di confronto restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="1fef2-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="1fef2-112">Se questo argomento viene omesso e nessuna operazione di confronto restituisce `true`, CASE restituisce null.</span><span class="sxs-lookup"><span data-stu-id="1fef2-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> `else_result_expression` <span data-ttu-id="1fef2-113">È qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="1fef2-113">is any valid expression.</span></span> <span data-ttu-id="1fef2-114">A `else_result_expression` e a ogni occorrenza di `result_expression` deve essere associato lo stesso tipo di dati o un tipo di dati convertibile in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="1fef2-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="1fef2-115">WHEN</span><span class="sxs-lookup"><span data-stu-id="1fef2-115">WHEN</span></span> `Boolean_expression`  
 <span data-ttu-id="1fef2-116">È l'espressione `Boolean` valutata quando viene usato il formato CASE cercato.</span><span class="sxs-lookup"><span data-stu-id="1fef2-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> `Boolean_expression` <span data-ttu-id="1fef2-117">valida `Boolean` espressione.</span><span class="sxs-lookup"><span data-stu-id="1fef2-117">is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fef2-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1fef2-118">Return Value</span></span>  
 <span data-ttu-id="1fef2-119">Restituisce il tipo con precedenza maggiore dal set di tipi in `result_expression` e nell'oggetto facoltativo `else_result_expression`.</span><span class="sxs-lookup"><span data-stu-id="1fef2-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fef2-120">Note</span><span class="sxs-lookup"><span data-stu-id="1fef2-120">Remarks</span></span>  
 <span data-ttu-id="1fef2-121">L'espressione case [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è simile all'espressione case [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1fef2-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] case expression.</span></span> <span data-ttu-id="1fef2-122">È possibile usare l'espressione case per eseguire una serie di test condizionali per determinare quale espressione restituirà il risultato appropriato.</span><span class="sxs-lookup"><span data-stu-id="1fef2-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="1fef2-123">Questa forma dell'espressione case si applica a una serie di una o più espressioni `Boolean` per determinare l'espressione risultante corretta.</span><span class="sxs-lookup"><span data-stu-id="1fef2-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="1fef2-124">La funzione CASE restituisce `Boolean_expression` per ogni clausola WHEN nell'ordine specificato e restituisce `result_expression` del primo oggetto `Boolean_expression` che restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="1fef2-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="1fef2-125">Le espressioni rimanenti non vengono valutate.</span><span class="sxs-lookup"><span data-stu-id="1fef2-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="1fef2-126">Se nessun oggetto `Boolean_expression` restituisce `true`, il motore di database restituisce `else_result_expression` se è stata specificata una clausola ELSE. In caso contrario, viene restituito un valore null.</span><span class="sxs-lookup"><span data-stu-id="1fef2-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="1fef2-127">Un'istruzione CASE non può restituire un multiset.</span><span class="sxs-lookup"><span data-stu-id="1fef2-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fef2-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="1fef2-128">Example</span></span>  
 <span data-ttu-id="1fef2-129">Nella query Entity SQL seguente viene usata l'espressione CASE per valutare un set di espressioni `Boolean` per determinare il risultato.</span><span class="sxs-lookup"><span data-stu-id="1fef2-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="1fef2-130">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="1fef2-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1fef2-131">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fef2-131">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1fef2-132">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1fef2-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="1fef2-133">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1fef2-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="1fef2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fef2-134">See also</span></span>

- [<span data-ttu-id="1fef2-135">THEN</span><span class="sxs-lookup"><span data-stu-id="1fef2-135">THEN</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)
- [<span data-ttu-id="1fef2-136">SELEZIONE</span><span class="sxs-lookup"><span data-stu-id="1fef2-136">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)
- [<span data-ttu-id="1fef2-137">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1fef2-137">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
