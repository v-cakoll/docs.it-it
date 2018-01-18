---
title: DEREF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4e2bbac28e3f0f1149a9fa540692890512fb5941
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="deref-entity-sql"></a><span data-ttu-id="dd7b6-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dd7b6-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="dd7b6-103">Consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="dd7b6-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd7b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd7b6-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="dd7b6-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="dd7b6-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="dd7b6-106">Qualsiasi espressione di query valida che restituisce una raccolta.</span><span class="sxs-lookup"><span data-stu-id="dd7b6-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd7b6-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dd7b6-107">Return Value</span></span>  
 <span data-ttu-id="dd7b6-108">Valore dell'entità di cui viene risolto il riferimento.</span><span class="sxs-lookup"><span data-stu-id="dd7b6-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd7b6-109">Note</span><span class="sxs-lookup"><span data-stu-id="dd7b6-109">Remarks</span></span>  
 <span data-ttu-id="dd7b6-110">L'operatore DEREF consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="dd7b6-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="dd7b6-111">Ad esempio, se `r` è un riferimento di tipo ref\<T >, `Deref``(r)` è un'espressione di tipo `T` che restituisce l'entità a cui fa riferimento `r`.</span><span class="sxs-lookup"><span data-stu-id="dd7b6-111">For example, if `r` is a reference of type ref\<T>, `Deref``(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="dd7b6-112">Se il valore di riferimento è Null o è inesatto, ovvero la destinazione del riferimento non esiste, il risultato dell'operatore DEREF è Null.</span><span class="sxs-lookup"><span data-stu-id="dd7b6-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd7b6-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd7b6-113">Example</span></span>  
 <span data-ttu-id="dd7b6-114">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore DEREF per dereferenziare un valore di riferimento e viene restituito il risultato di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="dd7b6-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="dd7b6-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="dd7b6-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dd7b6-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd7b6-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="dd7b6-117">Attenersi alla procedura di [procedura: eseguire una Query che restituisce risultati di PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="dd7b6-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="dd7b6-118">Passare la query seguente come argomento al metodo ExecutePrimitiveTypeQuery:</span><span class="sxs-lookup"><span data-stu-id="dd7b6-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="dd7b6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd7b6-119">See Also</span></span>  
 [<span data-ttu-id="dd7b6-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="dd7b6-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="dd7b6-121">REF</span><span class="sxs-lookup"><span data-stu-id="dd7b6-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [<span data-ttu-id="dd7b6-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="dd7b6-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="dd7b6-123">KEY</span><span class="sxs-lookup"><span data-stu-id="dd7b6-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="dd7b6-124">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="dd7b6-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
