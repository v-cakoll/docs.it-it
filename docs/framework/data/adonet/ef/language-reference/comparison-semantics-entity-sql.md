---
title: Semantica di confronto (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2835d2064f1845b55dd3a33abb086c5af0fb9e6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="e7a17-102">Semantica di confronto (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e7a17-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="e7a17-103">L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:</span><span class="sxs-lookup"><span data-stu-id="e7a17-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="e7a17-104">Confronto esplicito</span><span class="sxs-lookup"><span data-stu-id="e7a17-104">Explicit comparison</span></span>  
 <span data-ttu-id="e7a17-105">Operazioni di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="e7a17-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="e7a17-106">!=</span><span class="sxs-lookup"><span data-stu-id="e7a17-106">!=</span></span>  
  
 <span data-ttu-id="e7a17-107">Operazioni di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="e7a17-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 <span data-ttu-id="e7a17-108">Operazioni di impostazione del supporto dei valori Null:</span><span class="sxs-lookup"><span data-stu-id="e7a17-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="e7a17-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="e7a17-109">IS NULL</span></span>  
  
-   <span data-ttu-id="e7a17-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="e7a17-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="e7a17-111">Distinzione esplicita</span><span class="sxs-lookup"><span data-stu-id="e7a17-111">Explicit distinction</span></span>  
 <span data-ttu-id="e7a17-112">Distinzione di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="e7a17-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="e7a17-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="e7a17-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="e7a17-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="e7a17-114">GROUP BY</span></span>  
  
 <span data-ttu-id="e7a17-115">Distinzione di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="e7a17-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="e7a17-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="e7a17-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="e7a17-117">Distinzione implicita</span><span class="sxs-lookup"><span data-stu-id="e7a17-117">Implicit distinction</span></span>  
 <span data-ttu-id="e7a17-118">Predicati e operazioni sui set (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="e7a17-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="e7a17-119">UNION</span><span class="sxs-lookup"><span data-stu-id="e7a17-119">UNION</span></span>  
  
-   <span data-ttu-id="e7a17-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="e7a17-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="e7a17-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="e7a17-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="e7a17-122">SET</span><span class="sxs-lookup"><span data-stu-id="e7a17-122">SET</span></span>  
  
-   <span data-ttu-id="e7a17-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="e7a17-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="e7a17-124">Predicati degli elementi (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="e7a17-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="e7a17-125">IN</span><span class="sxs-lookup"><span data-stu-id="e7a17-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="e7a17-126">Combinazioni supportate</span><span class="sxs-lookup"><span data-stu-id="e7a17-126">Supported Combinations</span></span>  
 <span data-ttu-id="e7a17-127">Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:</span><span class="sxs-lookup"><span data-stu-id="e7a17-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="e7a17-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="e7a17-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="e7a17-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="e7a17-129">**!=**</span></span>|<span data-ttu-id="e7a17-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="e7a17-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="e7a17-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="e7a17-131">**DISTINCT**</span></span>|<span data-ttu-id="e7a17-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="e7a17-132">**UNION**</span></span><br /><br /> <span data-ttu-id="e7a17-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="e7a17-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="e7a17-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="e7a17-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="e7a17-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="e7a17-135">**SET**</span></span><br /><br /> <span data-ttu-id="e7a17-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="e7a17-136">**OVERLAPS**</span></span>|<span data-ttu-id="e7a17-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="e7a17-137">**IN**</span></span>|<span data-ttu-id="e7a17-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="e7a17-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="e7a17-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="e7a17-139">**>   >=**</span></span>|<span data-ttu-id="e7a17-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="e7a17-140">**ORDER BY**</span></span>|<span data-ttu-id="e7a17-141">**È NULL**</span><span class="sxs-lookup"><span data-stu-id="e7a17-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="e7a17-142">**NON È NULL**</span><span class="sxs-lookup"><span data-stu-id="e7a17-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="e7a17-143">Tipo di entità</span><span class="sxs-lookup"><span data-stu-id="e7a17-143">Entity type</span></span>|<span data-ttu-id="e7a17-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="e7a17-145">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="e7a17-146">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="e7a17-147">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="e7a17-148">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-149">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="e7a17-151">Tipo complesso</span><span class="sxs-lookup"><span data-stu-id="e7a17-151">Complex type</span></span>|<span data-ttu-id="e7a17-152">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-153">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-154">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-155">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-156">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-157">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-158">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="e7a17-159">Riga</span><span class="sxs-lookup"><span data-stu-id="e7a17-159">Row</span></span>|<span data-ttu-id="e7a17-160">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="e7a17-161">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="e7a17-162">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="e7a17-163">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-164">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-165">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="e7a17-166">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="e7a17-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="e7a17-167">Primitive type</span></span>|<span data-ttu-id="e7a17-168">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="e7a17-168">Provider-specific</span></span>|<span data-ttu-id="e7a17-169">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="e7a17-169">Provider-specific</span></span>|<span data-ttu-id="e7a17-170">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="e7a17-170">Provider-specific</span></span>|<span data-ttu-id="e7a17-171">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="e7a17-171">Provider-specific</span></span>|<span data-ttu-id="e7a17-172">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="e7a17-172">Provider-specific</span></span>|<span data-ttu-id="e7a17-173">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="e7a17-173">Provider-specific</span></span>|<span data-ttu-id="e7a17-174">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="e7a17-174">Provider-specific</span></span>|  
|<span data-ttu-id="e7a17-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="e7a17-175">Multiset</span></span>|<span data-ttu-id="e7a17-176">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-177">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-178">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-179">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-180">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-181">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-182">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="e7a17-183">Rif</span><span class="sxs-lookup"><span data-stu-id="e7a17-183">Ref</span></span>|<span data-ttu-id="e7a17-184">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="e7a17-185">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="e7a17-186">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="e7a17-187">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="e7a17-188">Throw</span><span class="sxs-lookup"><span data-stu-id="e7a17-188">Throw</span></span>|<span data-ttu-id="e7a17-189">Throw</span><span class="sxs-lookup"><span data-stu-id="e7a17-189">Throw</span></span>|<span data-ttu-id="e7a17-190">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="e7a17-191">Associazione</span><span class="sxs-lookup"><span data-stu-id="e7a17-191">Association</span></span><br /><br /> <span data-ttu-id="e7a17-192">tipo</span><span class="sxs-lookup"><span data-stu-id="e7a17-192">type</span></span>|<span data-ttu-id="e7a17-193">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-194">Throw</span><span class="sxs-lookup"><span data-stu-id="e7a17-194">Throw</span></span>|<span data-ttu-id="e7a17-195">Throw</span><span class="sxs-lookup"><span data-stu-id="e7a17-195">Throw</span></span>|<span data-ttu-id="e7a17-196">Throw</span><span class="sxs-lookup"><span data-stu-id="e7a17-196">Throw</span></span>|<span data-ttu-id="e7a17-197">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-198">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="e7a17-199">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="e7a17-200"><sup>1</sup>vengono confrontati in modo implicito i riferimenti delle istanze di tipo di entità specificato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e7a17-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="e7a17-201">Un'istanza di entità non può essere confrontata con un riferimento esplicito.</span><span class="sxs-lookup"><span data-stu-id="e7a17-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="e7a17-202">Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e7a17-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="e7a17-203">La query seguente comporta, ad esempio, la generazione di un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="e7a17-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="e7a17-204"><sup>2</sup>le proprietà dei tipi complessi sono impostate come bidimensionali prima dell'invio all'archivio, in modo che diventino confrontabili (fino a quando tutte le relative proprietà sono confrontabili).</span><span class="sxs-lookup"><span data-stu-id="e7a17-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="e7a17-205">Vedere anche <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="e7a17-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="e7a17-206"><sup>3</sup>runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza ricorrere al provider o all'archivio.</span><span class="sxs-lookup"><span data-stu-id="e7a17-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="e7a17-207"><sup>4</sup>viene effettuato un tentativo di confrontare tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="e7a17-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="e7a17-208">Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.</span><span class="sxs-lookup"><span data-stu-id="e7a17-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="e7a17-209"><sup>5</sup>vengono confrontati tutti i singoli elementi dei riferimenti (che include il nome del set di entità e tutte le proprietà chiave del tipo di entità).</span><span class="sxs-lookup"><span data-stu-id="e7a17-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a17-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7a17-210">See Also</span></span>  
 [<span data-ttu-id="e7a17-211">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e7a17-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
