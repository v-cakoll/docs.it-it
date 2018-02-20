---
title: Semantica di confronto (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e20d47e0ae97067d2dcafcf929f717598d4e3e80
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="06cdb-102">Semantica di confronto (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="06cdb-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="06cdb-103">L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:</span><span class="sxs-lookup"><span data-stu-id="06cdb-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="06cdb-104">Confronto esplicito</span><span class="sxs-lookup"><span data-stu-id="06cdb-104">Explicit comparison</span></span>  
 <span data-ttu-id="06cdb-105">Operazioni di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="06cdb-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="06cdb-106">!=</span><span class="sxs-lookup"><span data-stu-id="06cdb-106">!=</span></span>  
  
 <span data-ttu-id="06cdb-107">Operazioni di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="06cdb-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="06cdb-108">Operazioni di impostazione del supporto dei valori Null:</span><span class="sxs-lookup"><span data-stu-id="06cdb-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="06cdb-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="06cdb-109">IS NULL</span></span>  
  
-   <span data-ttu-id="06cdb-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="06cdb-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="06cdb-111">Distinzione esplicita</span><span class="sxs-lookup"><span data-stu-id="06cdb-111">Explicit distinction</span></span>  
 <span data-ttu-id="06cdb-112">Distinzione di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="06cdb-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="06cdb-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="06cdb-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="06cdb-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="06cdb-114">GROUP BY</span></span>  
  
 <span data-ttu-id="06cdb-115">Distinzione di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="06cdb-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="06cdb-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="06cdb-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="06cdb-117">Distinzione implicita</span><span class="sxs-lookup"><span data-stu-id="06cdb-117">Implicit distinction</span></span>  
 <span data-ttu-id="06cdb-118">Predicati e operazioni sui set (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="06cdb-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="06cdb-119">UNION</span><span class="sxs-lookup"><span data-stu-id="06cdb-119">UNION</span></span>  
  
-   <span data-ttu-id="06cdb-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="06cdb-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="06cdb-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="06cdb-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="06cdb-122">SET</span><span class="sxs-lookup"><span data-stu-id="06cdb-122">SET</span></span>  
  
-   <span data-ttu-id="06cdb-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="06cdb-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="06cdb-124">Predicati degli elementi (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="06cdb-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="06cdb-125">IN</span><span class="sxs-lookup"><span data-stu-id="06cdb-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="06cdb-126">Combinazioni supportate</span><span class="sxs-lookup"><span data-stu-id="06cdb-126">Supported Combinations</span></span>  
 <span data-ttu-id="06cdb-127">Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:</span><span class="sxs-lookup"><span data-stu-id="06cdb-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="06cdb-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="06cdb-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="06cdb-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="06cdb-129">**!=**</span></span>|<span data-ttu-id="06cdb-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="06cdb-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="06cdb-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="06cdb-131">**DISTINCT**</span></span>|<span data-ttu-id="06cdb-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="06cdb-132">**UNION**</span></span><br /><br /> <span data-ttu-id="06cdb-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="06cdb-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="06cdb-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="06cdb-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="06cdb-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="06cdb-135">**SET**</span></span><br /><br /> <span data-ttu-id="06cdb-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="06cdb-136">**OVERLAPS**</span></span>|<span data-ttu-id="06cdb-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="06cdb-137">**IN**</span></span>|<span data-ttu-id="06cdb-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="06cdb-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="06cdb-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="06cdb-139">**>   >=**</span></span>|<span data-ttu-id="06cdb-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="06cdb-140">**ORDER BY**</span></span>|<span data-ttu-id="06cdb-141">**È NULL**</span><span class="sxs-lookup"><span data-stu-id="06cdb-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="06cdb-142">**NON È NULL**</span><span class="sxs-lookup"><span data-stu-id="06cdb-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="06cdb-143">Tipo di entità</span><span class="sxs-lookup"><span data-stu-id="06cdb-143">Entity type</span></span>|<span data-ttu-id="06cdb-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="06cdb-145">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="06cdb-146">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="06cdb-147">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="06cdb-148">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-149">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="06cdb-151">Tipo complesso</span><span class="sxs-lookup"><span data-stu-id="06cdb-151">Complex type</span></span>|<span data-ttu-id="06cdb-152">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-153">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-154">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-155">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-156">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-157">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-158">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="06cdb-159">Riga</span><span class="sxs-lookup"><span data-stu-id="06cdb-159">Row</span></span>|<span data-ttu-id="06cdb-160">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="06cdb-161">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="06cdb-162">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="06cdb-163">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-164">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-165">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="06cdb-166">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="06cdb-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="06cdb-167">Primitive type</span></span>|<span data-ttu-id="06cdb-168">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="06cdb-168">Provider-specific</span></span>|<span data-ttu-id="06cdb-169">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="06cdb-169">Provider-specific</span></span>|<span data-ttu-id="06cdb-170">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="06cdb-170">Provider-specific</span></span>|<span data-ttu-id="06cdb-171">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="06cdb-171">Provider-specific</span></span>|<span data-ttu-id="06cdb-172">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="06cdb-172">Provider-specific</span></span>|<span data-ttu-id="06cdb-173">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="06cdb-173">Provider-specific</span></span>|<span data-ttu-id="06cdb-174">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="06cdb-174">Provider-specific</span></span>|  
|<span data-ttu-id="06cdb-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="06cdb-175">Multiset</span></span>|<span data-ttu-id="06cdb-176">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-177">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-178">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-179">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-180">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-181">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-182">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="06cdb-183">Rif</span><span class="sxs-lookup"><span data-stu-id="06cdb-183">Ref</span></span>|<span data-ttu-id="06cdb-184">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="06cdb-185">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="06cdb-186">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="06cdb-187">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="06cdb-188">Throw</span><span class="sxs-lookup"><span data-stu-id="06cdb-188">Throw</span></span>|<span data-ttu-id="06cdb-189">Throw</span><span class="sxs-lookup"><span data-stu-id="06cdb-189">Throw</span></span>|<span data-ttu-id="06cdb-190">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="06cdb-191">Associazione</span><span class="sxs-lookup"><span data-stu-id="06cdb-191">Association</span></span><br /><br /> <span data-ttu-id="06cdb-192">tipo</span><span class="sxs-lookup"><span data-stu-id="06cdb-192">type</span></span>|<span data-ttu-id="06cdb-193">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-194">Throw</span><span class="sxs-lookup"><span data-stu-id="06cdb-194">Throw</span></span>|<span data-ttu-id="06cdb-195">Throw</span><span class="sxs-lookup"><span data-stu-id="06cdb-195">Throw</span></span>|<span data-ttu-id="06cdb-196">Throw</span><span class="sxs-lookup"><span data-stu-id="06cdb-196">Throw</span></span>|<span data-ttu-id="06cdb-197">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-198">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="06cdb-199">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="06cdb-200"><sup>1</sup>vengono confrontati in modo implicito i riferimenti delle istanze di tipo di entità specificato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="06cdb-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="06cdb-201">Un'istanza di entità non può essere confrontata con un riferimento esplicito.</span><span class="sxs-lookup"><span data-stu-id="06cdb-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="06cdb-202">Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="06cdb-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="06cdb-203">La query seguente comporta, ad esempio, la generazione di un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="06cdb-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="06cdb-204"><sup>2</sup>le proprietà dei tipi complessi sono impostate come bidimensionali prima dell'invio all'archivio, in modo che diventino confrontabili (fino a quando tutte le relative proprietà sono confrontabili).</span><span class="sxs-lookup"><span data-stu-id="06cdb-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="06cdb-205">Vedere anche <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="06cdb-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="06cdb-206"><sup>3</sup>runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza ricorrere al provider o all'archivio.</span><span class="sxs-lookup"><span data-stu-id="06cdb-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="06cdb-207"><sup>4</sup>viene effettuato un tentativo di confrontare tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="06cdb-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="06cdb-208">Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.</span><span class="sxs-lookup"><span data-stu-id="06cdb-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="06cdb-209"><sup>5</sup>vengono confrontati tutti i singoli elementi dei riferimenti (che include il nome del set di entità e tutte le proprietà chiave del tipo di entità).</span><span class="sxs-lookup"><span data-stu-id="06cdb-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06cdb-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06cdb-210">See Also</span></span>  
 [<span data-ttu-id="06cdb-211">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="06cdb-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
