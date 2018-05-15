---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 09ae742f648f95819a8c6fc64d402c4f11c7748a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="-or-entity-sql"></a><span data-ttu-id="7c07f-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7c07f-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="7c07f-103">Combina due espressioni `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7c07f-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c07f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c07f-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7c07f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7c07f-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="7c07f-106">Qualsiasi espressione valida che restituisce un valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7c07f-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c07f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7c07f-107">Return Value</span></span>  
 <span data-ttu-id="7c07f-108">`true` se una delle condizioni è `true`; in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="7c07f-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c07f-109">Note</span><span class="sxs-lookup"><span data-stu-id="7c07f-109">Remarks</span></span>  
 <span data-ttu-id="7c07f-110">OR è un operatore logico [!INCLUDE[esql](../../../../../../includes/esql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c07f-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="7c07f-111">usato per combinare due condizioni.</span><span class="sxs-lookup"><span data-stu-id="7c07f-111">It is used to combine two conditions.</span></span> <span data-ttu-id="7c07f-112">Quando in un'istruzione si usa più di un operatore logico, gli operatori OR vengono valutati dopo gli operatori AND.</span><span class="sxs-lookup"><span data-stu-id="7c07f-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="7c07f-113">È tuttavia possibile modificare l'ordine di valutazione tramite l'uso delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="7c07f-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="7c07f-114">Le barre verticali doppie (&#124;&#124;) ha la stessa funzionalità come l'operatore OR.</span><span class="sxs-lookup"><span data-stu-id="7c07f-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="7c07f-115">Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="7c07f-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="7c07f-116">true</span><span class="sxs-lookup"><span data-stu-id="7c07f-116">TRUE</span></span>|<span data-ttu-id="7c07f-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="7c07f-117">TRUE</span></span>|<span data-ttu-id="7c07f-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="7c07f-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="7c07f-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="7c07f-119">TRUE</span></span>|<span data-ttu-id="7c07f-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="7c07f-120">FALSE</span></span>|<span data-ttu-id="7c07f-121">NULL</span><span class="sxs-lookup"><span data-stu-id="7c07f-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="7c07f-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="7c07f-122">TRUE</span></span>|<span data-ttu-id="7c07f-123">NULL</span><span class="sxs-lookup"><span data-stu-id="7c07f-123">NULL</span></span>|<span data-ttu-id="7c07f-124">NULL</span><span class="sxs-lookup"><span data-stu-id="7c07f-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7c07f-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c07f-125">Example</span></span>  
 <span data-ttu-id="7c07f-126">Nella query Entity SQL seguente viene usato l'operatore OR per combinare due espressioni `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7c07f-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="7c07f-127">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7c07f-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7c07f-128">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c07f-128">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="7c07f-129">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="7c07f-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="7c07f-130">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="7c07f-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="7c07f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c07f-131">See Also</span></span>  
 [<span data-ttu-id="7c07f-132">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7c07f-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
