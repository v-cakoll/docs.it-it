---
title: ISNULL (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 57e90f013227f08ce365262da633a79d7abb5a8d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="7e82c-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7e82c-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="7e82c-103">Consente di determinare se un'espressione di query è null.</span><span class="sxs-lookup"><span data-stu-id="7e82c-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e82c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e82c-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="7e82c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7e82c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="7e82c-106">Qualsiasi espressione di query valida.</span><span class="sxs-lookup"><span data-stu-id="7e82c-106">Any valid query expression.</span></span> <span data-ttu-id="7e82c-107">Non può trattarsi di una raccolta, includere membri di una raccolta o essere un tipo di record con proprietà di un tipo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="7e82c-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="7e82c-108">NOT</span><span class="sxs-lookup"><span data-stu-id="7e82c-108">NOT</span></span>  
 <span data-ttu-id="7e82c-109">Nega il risultato EDM.Boolean di IS NULL.</span><span class="sxs-lookup"><span data-stu-id="7e82c-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e82c-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7e82c-110">Return Value</span></span>  
 <span data-ttu-id="7e82c-111">`true` se `expression` restituisce null; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7e82c-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e82c-112">Note</span><span class="sxs-lookup"><span data-stu-id="7e82c-112">Remarks</span></span>  
 <span data-ttu-id="7e82c-113">Usare `IS NULL` per determinare se l'elemento di un outer join è null:</span><span class="sxs-lookup"><span data-stu-id="7e82c-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="7e82c-114">Usare `IS NULL` per determinare se un membro ha un valore effettivo:</span><span class="sxs-lookup"><span data-stu-id="7e82c-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="7e82c-115">Nella tabella seguente viene illustrato il comportamento di `IS NULL` con alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="7e82c-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="7e82c-116">Tutte le eccezioni vengono generate sul lato client prima che il provider venga richiamato:</span><span class="sxs-lookup"><span data-stu-id="7e82c-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="7e82c-117">Criterio</span><span class="sxs-lookup"><span data-stu-id="7e82c-117">Pattern</span></span>|<span data-ttu-id="7e82c-118">Comportamento</span><span class="sxs-lookup"><span data-stu-id="7e82c-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="7e82c-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="7e82c-119">null IS NULL</span></span>|<span data-ttu-id="7e82c-120">Restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="7e82c-120">Returns `true`.</span></span>|  
|<span data-ttu-id="7e82c-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="7e82c-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="7e82c-122">Restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="7e82c-122">Returns `true`.</span></span>|  
|<span data-ttu-id="7e82c-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="7e82c-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="7e82c-124">Genera un errore.</span><span class="sxs-lookup"><span data-stu-id="7e82c-124">Throws an error.</span></span>|  
|<span data-ttu-id="7e82c-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="7e82c-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="7e82c-126">Genera un errore.</span><span class="sxs-lookup"><span data-stu-id="7e82c-126">Throws an error.</span></span>|  
|<span data-ttu-id="7e82c-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="7e82c-127">EntityType IS NULL</span></span>|<span data-ttu-id="7e82c-128">Restituisce `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="7e82c-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="7e82c-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="7e82c-129">ComplexType IS NULL</span></span>|<span data-ttu-id="7e82c-130">Genera un errore.</span><span class="sxs-lookup"><span data-stu-id="7e82c-130">Throws an error.</span></span>|  
|<span data-ttu-id="7e82c-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="7e82c-131">RowType IS NULL</span></span>|<span data-ttu-id="7e82c-132">Genera un errore.</span><span class="sxs-lookup"><span data-stu-id="7e82c-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7e82c-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e82c-133">Example</span></span>  
 <span data-ttu-id="7e82c-134">Le operazioni seguenti [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query utilizza l'operatore IS NOT NULL per determinare se un'espressione di query non è null.</span><span class="sxs-lookup"><span data-stu-id="7e82c-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="7e82c-135">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7e82c-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7e82c-136">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e82c-136">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="7e82c-137">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="7e82c-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="7e82c-138">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="7e82c-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="7e82c-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e82c-139">See Also</span></span>  
 [<span data-ttu-id="7e82c-140">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7e82c-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
