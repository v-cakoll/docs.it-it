---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: d54c350196ad1ef7cfafa6d931d9d1ad8f267177
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250563"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="cf801-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cf801-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="cf801-103">Consente di determinare se un'espressione di query è null.</span><span class="sxs-lookup"><span data-stu-id="cf801-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf801-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf801-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf801-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cf801-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="cf801-106">Qualsiasi espressione di query valida.</span><span class="sxs-lookup"><span data-stu-id="cf801-106">Any valid query expression.</span></span> <span data-ttu-id="cf801-107">Non può trattarsi di una raccolta, includere membri di una raccolta o essere un tipo di record con proprietà di un tipo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="cf801-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="cf801-108">NOT</span><span class="sxs-lookup"><span data-stu-id="cf801-108">NOT</span></span>  
 <span data-ttu-id="cf801-109">Nega il risultato EDM.Boolean di IS NULL.</span><span class="sxs-lookup"><span data-stu-id="cf801-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf801-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cf801-110">Return Value</span></span>  
 <span data-ttu-id="cf801-111">`true` se `expression` restituisce null; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="cf801-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf801-112">Note</span><span class="sxs-lookup"><span data-stu-id="cf801-112">Remarks</span></span>  
 <span data-ttu-id="cf801-113">Usare `IS NULL` per determinare se l'elemento di un outer join è null:</span><span class="sxs-lookup"><span data-stu-id="cf801-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="cf801-114">Usare `IS NULL` per determinare se un membro ha un valore effettivo:</span><span class="sxs-lookup"><span data-stu-id="cf801-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="cf801-115">Nella tabella seguente viene illustrato il comportamento di `IS NULL` con alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="cf801-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="cf801-116">Tutte le eccezioni vengono generate sul lato client prima che il provider venga richiamato:</span><span class="sxs-lookup"><span data-stu-id="cf801-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="cf801-117">Modello</span><span class="sxs-lookup"><span data-stu-id="cf801-117">Pattern</span></span>|<span data-ttu-id="cf801-118">Comportamento</span><span class="sxs-lookup"><span data-stu-id="cf801-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="cf801-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="cf801-119">null IS NULL</span></span>|<span data-ttu-id="cf801-120">Restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="cf801-120">Returns `true`.</span></span>|  
|<span data-ttu-id="cf801-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="cf801-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="cf801-122">Restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="cf801-122">Returns `true`.</span></span>|  
|<span data-ttu-id="cf801-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="cf801-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="cf801-124">Genera un errore.</span><span class="sxs-lookup"><span data-stu-id="cf801-124">Throws an error.</span></span>|  
|<span data-ttu-id="cf801-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="cf801-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="cf801-126">Genera un errore.</span><span class="sxs-lookup"><span data-stu-id="cf801-126">Throws an error.</span></span>|  
|<span data-ttu-id="cf801-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="cf801-127">EntityType IS NULL</span></span>|<span data-ttu-id="cf801-128">Restituisce `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="cf801-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="cf801-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="cf801-129">ComplexType IS NULL</span></span>|<span data-ttu-id="cf801-130">Genera un errore.</span><span class="sxs-lookup"><span data-stu-id="cf801-130">Throws an error.</span></span>|  
|<span data-ttu-id="cf801-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="cf801-131">RowType IS NULL</span></span>|<span data-ttu-id="cf801-132">Genera un errore.</span><span class="sxs-lookup"><span data-stu-id="cf801-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cf801-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf801-133">Example</span></span>  
 <span data-ttu-id="cf801-134">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore is not null per determinare se un'espressione di query non è null.</span><span class="sxs-lookup"><span data-stu-id="cf801-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="cf801-135">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="cf801-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cf801-136">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf801-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cf801-137">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="cf801-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="cf801-138">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="cf801-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="cf801-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf801-139">See also</span></span>

- [<span data-ttu-id="cf801-140">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cf801-140">Entity SQL Reference</span></span>](entity-sql-reference.md)
