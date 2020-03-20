---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 8c93e68095a0e0ff63532f53152f166d6c3d047c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150093"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="30771-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="30771-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="30771-103">Combina due espressioni `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="30771-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30771-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30771-104">Syntax</span></span>  
  
```sql  
boolean_expression OR boolean_expression  
-- or
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="30771-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="30771-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="30771-106">Qualsiasi espressione valida che restituisce un valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="30771-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30771-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="30771-107">Return Value</span></span>  
 <span data-ttu-id="30771-108">`true` se una delle condizioni è `true`; in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="30771-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30771-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="30771-109">Remarks</span></span>  
 <span data-ttu-id="30771-110">OR è un operatore logico [!INCLUDE[esql](../../../../../../includes/esql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30771-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="30771-111">usato per combinare due condizioni.</span><span class="sxs-lookup"><span data-stu-id="30771-111">It is used to combine two conditions.</span></span> <span data-ttu-id="30771-112">Quando un'istruzione include più operatori logici, gli operatori OR vengono valutati dopo gli operatori AND.</span><span class="sxs-lookup"><span data-stu-id="30771-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="30771-113">È tuttavia possibile modificare l'ordine di valutazione tramite l'utilizzo delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="30771-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="30771-114">Le barre verticali doppie (&#124;&#124;) hanno la stessa funzionalità dell'operatore OR.</span><span class="sxs-lookup"><span data-stu-id="30771-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="30771-115">Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="30771-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="30771-116">TRUE</span><span class="sxs-lookup"><span data-stu-id="30771-116">TRUE</span></span>|<span data-ttu-id="30771-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="30771-117">TRUE</span></span>|<span data-ttu-id="30771-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="30771-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="30771-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="30771-119">TRUE</span></span>|<span data-ttu-id="30771-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="30771-120">FALSE</span></span>|<span data-ttu-id="30771-121">NULL</span><span class="sxs-lookup"><span data-stu-id="30771-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="30771-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="30771-122">TRUE</span></span>|<span data-ttu-id="30771-123">NULL</span><span class="sxs-lookup"><span data-stu-id="30771-123">NULL</span></span>|<span data-ttu-id="30771-124">NULL</span><span class="sxs-lookup"><span data-stu-id="30771-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="30771-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="30771-125">Example</span></span>  
 <span data-ttu-id="30771-126">Nella query Entity SQL seguente viene usato l'operatore OR per combinare due espressioni `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="30771-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="30771-127">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="30771-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="30771-128">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30771-128">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="30771-129">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="30771-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="30771-130">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="30771-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a><span data-ttu-id="30771-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30771-131">See also</span></span>

- [<span data-ttu-id="30771-132">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="30771-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
