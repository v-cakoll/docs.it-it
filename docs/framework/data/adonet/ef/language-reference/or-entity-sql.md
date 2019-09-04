---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: c88e041638fbe6f32717ce9c4f9c2ff6fb56d803
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249769"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="a33e4-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a33e4-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="a33e4-103">Combina due espressioni `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="a33e4-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a33e4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a33e4-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a33e4-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a33e4-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="a33e4-106">Qualsiasi espressione valida che restituisce un valore `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a33e4-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a33e4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a33e4-107">Return Value</span></span>  
 <span data-ttu-id="a33e4-108">`true` se una delle condizioni è `true`; in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="a33e4-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a33e4-109">Note</span><span class="sxs-lookup"><span data-stu-id="a33e4-109">Remarks</span></span>  
 <span data-ttu-id="a33e4-110">OR è un operatore logico [!INCLUDE[esql](../../../../../../includes/esql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a33e4-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="a33e4-111">usato per combinare due condizioni.</span><span class="sxs-lookup"><span data-stu-id="a33e4-111">It is used to combine two conditions.</span></span> <span data-ttu-id="a33e4-112">Quando in un'istruzione si usa più di un operatore logico, gli operatori OR vengono valutati dopo gli operatori AND.</span><span class="sxs-lookup"><span data-stu-id="a33e4-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="a33e4-113">È tuttavia possibile modificare l'ordine di valutazione tramite l'uso delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="a33e4-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="a33e4-114">La doppia barra verticale&#124;&#124;() ha la stessa funzionalità dell'operatore o.</span><span class="sxs-lookup"><span data-stu-id="a33e4-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="a33e4-115">Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="a33e4-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="a33e4-116">true</span><span class="sxs-lookup"><span data-stu-id="a33e4-116">TRUE</span></span>|<span data-ttu-id="a33e4-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33e4-117">TRUE</span></span>|<span data-ttu-id="a33e4-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33e4-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="a33e4-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33e4-119">TRUE</span></span>|<span data-ttu-id="a33e4-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="a33e4-120">FALSE</span></span>|<span data-ttu-id="a33e4-121">NULL</span><span class="sxs-lookup"><span data-stu-id="a33e4-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="a33e4-122">TRUE</span><span class="sxs-lookup"><span data-stu-id="a33e4-122">TRUE</span></span>|<span data-ttu-id="a33e4-123">NULL</span><span class="sxs-lookup"><span data-stu-id="a33e4-123">NULL</span></span>|<span data-ttu-id="a33e4-124">NULL</span><span class="sxs-lookup"><span data-stu-id="a33e4-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a33e4-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="a33e4-125">Example</span></span>  
 <span data-ttu-id="a33e4-126">Nella query Entity SQL seguente viene usato l'operatore OR per combinare due espressioni `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="a33e4-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="a33e4-127">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a33e4-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a33e4-128">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a33e4-128">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a33e4-129">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="a33e4-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a33e4-130">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a33e4-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="a33e4-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a33e4-131">See also</span></span>

- [<span data-ttu-id="a33e4-132">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a33e4-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
