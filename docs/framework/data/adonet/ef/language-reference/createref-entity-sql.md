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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8de4266277be31fd51411d4b994f1b5de45f13df
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="createref-entity-sql"></a><span data-ttu-id="2dac3-102">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2dac3-102">CREATEREF (Entity SQL)</span></span>
<span data-ttu-id="2dac3-103">Consente di creare riferimenti a un'entità in un oggetto EntitySet.</span><span class="sxs-lookup"><span data-stu-id="2dac3-103">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dac3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2dac3-104">Syntax</span></span>  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="2dac3-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2dac3-105">Arguments</span></span>  
 `entityset_identifier`  
 <span data-ttu-id="2dac3-106">Identificatore dell'oggetto EntitySet, non un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="2dac3-106">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="2dac3-107">Espressione con tipizzazione di riga che corrisponde alle proprietà chiave del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="2dac3-107">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dac3-108">Note</span><span class="sxs-lookup"><span data-stu-id="2dac3-108">Remarks</span></span>  
 <span data-ttu-id="2dac3-109">Dal punto di vista strutturale,`row_typed_expression` deve essere equivalente al tipo di chiave per l'entità.</span><span class="sxs-lookup"><span data-stu-id="2dac3-109">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="2dac3-110">Questo significa che deve avere lo stesso numero di tipi e di campi nello stesso ordine delle chiavi di entità.</span><span class="sxs-lookup"><span data-stu-id="2dac3-110">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="2dac3-111">Nell'esempio seguente Orders e BadOrders sono entrambi oggetti EntitySet di tipo Order e si presuppone che Id sia la proprietà di chiave singola di Order.</span><span class="sxs-lookup"><span data-stu-id="2dac3-111">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="2dac3-112">Nell'esempio viene illustrato in che modo è possibile creare un riferimento a un'entità in BadOrders.</span><span class="sxs-lookup"><span data-stu-id="2dac3-112">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="2dac3-113">Si noti che il riferimento può essere inesatto,</span><span class="sxs-lookup"><span data-stu-id="2dac3-113">Note that the reference may be dangling.</span></span>  <span data-ttu-id="2dac3-114">ovvero potrebbe non identificare effettivamente un'entità specifica.</span><span class="sxs-lookup"><span data-stu-id="2dac3-114">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="2dac3-115">In casi di questo tipo un'operazione `DEREF` su tale riferimento restituisce un valore Null.</span><span class="sxs-lookup"><span data-stu-id="2dac3-115">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a><span data-ttu-id="2dac3-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="2dac3-116">Example</span></span>  
 <span data-ttu-id="2dac3-117">Nella query Entity SQL seguente viene usato l'operatore CREATEREF per creare riferimenti a un'entità in un set di entità.</span><span class="sxs-lookup"><span data-stu-id="2dac3-117">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="2dac3-118">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2dac3-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2dac3-119">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2dac3-119">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2dac3-120">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2dac3-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="2dac3-121">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2dac3-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="2dac3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dac3-122">See Also</span></span>  
 [<span data-ttu-id="2dac3-123">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2dac3-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="2dac3-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="2dac3-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [<span data-ttu-id="2dac3-125">KEY</span><span class="sxs-lookup"><span data-stu-id="2dac3-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="2dac3-126">REF</span><span class="sxs-lookup"><span data-stu-id="2dac3-126">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
