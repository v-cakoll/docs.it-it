---
title: CREATEREF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9fe960d5b19f5119f2337ec410738a2df31f20c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="createref-entity-sql"></a><span data-ttu-id="c0147-102">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c0147-102">CREATEREF (Entity SQL)</span></span>
<span data-ttu-id="c0147-103">Consente di creare riferimenti a un'entità in un oggetto EntitySet.</span><span class="sxs-lookup"><span data-stu-id="c0147-103">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0147-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0147-104">Syntax</span></span>  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c0147-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c0147-105">Arguments</span></span>  
 `entityset_identifier`  
 <span data-ttu-id="c0147-106">Identificatore dell'oggetto EntitySet, non un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="c0147-106">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="c0147-107">Espressione con tipizzazione di riga che corrisponde alle proprietà chiave del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="c0147-107">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0147-108">Note</span><span class="sxs-lookup"><span data-stu-id="c0147-108">Remarks</span></span>  
 <span data-ttu-id="c0147-109">Dal punto di vista strutturale,`row_typed_expression` deve essere equivalente al tipo di chiave per l'entità.</span><span class="sxs-lookup"><span data-stu-id="c0147-109">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="c0147-110">Questo significa che deve avere lo stesso numero di tipi e di campi nello stesso ordine delle chiavi di entità.</span><span class="sxs-lookup"><span data-stu-id="c0147-110">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="c0147-111">Nell'esempio seguente Orders e BadOrders sono entrambi oggetti EntitySet di tipo Order e si presuppone che Id sia la proprietà di chiave singola di Order.</span><span class="sxs-lookup"><span data-stu-id="c0147-111">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="c0147-112">Nell'esempio viene illustrato in che modo è possibile creare un riferimento a un'entità in BadOrders.</span><span class="sxs-lookup"><span data-stu-id="c0147-112">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="c0147-113">Si noti che il riferimento può essere inesatto,</span><span class="sxs-lookup"><span data-stu-id="c0147-113">Note that the reference may be dangling.</span></span>  <span data-ttu-id="c0147-114">ovvero potrebbe non identificare effettivamente un'entità specifica.</span><span class="sxs-lookup"><span data-stu-id="c0147-114">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="c0147-115">In casi di questo tipo un'operazione `DEREF` su tale riferimento restituisce un valore Null.</span><span class="sxs-lookup"><span data-stu-id="c0147-115">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a><span data-ttu-id="c0147-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0147-116">Example</span></span>  
 <span data-ttu-id="c0147-117">Nella query Entity SQL seguente viene usato l'operatore CREATEREF per creare riferimenti a un'entità in un set di entità.</span><span class="sxs-lookup"><span data-stu-id="c0147-117">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="c0147-118">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c0147-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c0147-119">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0147-119">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c0147-120">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c0147-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="c0147-121">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c0147-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="c0147-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0147-122">See Also</span></span>  
 [<span data-ttu-id="c0147-123">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c0147-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="c0147-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="c0147-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [<span data-ttu-id="c0147-125">CHIAVE</span><span class="sxs-lookup"><span data-stu-id="c0147-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="c0147-126">REF</span><span class="sxs-lookup"><span data-stu-id="c0147-126">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
