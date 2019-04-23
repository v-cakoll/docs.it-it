---
title: Semantica di confronto (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 6b4c4177ebd6c45e00a1ac7774e40a43e0c14a74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083335"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="79be2-102">Semantica di confronto (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="79be2-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="79be2-103">L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:</span><span class="sxs-lookup"><span data-stu-id="79be2-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="79be2-104">Confronto esplicito</span><span class="sxs-lookup"><span data-stu-id="79be2-104">Explicit comparison</span></span>  
 <span data-ttu-id="79be2-105">Operazioni di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="79be2-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="79be2-106">!=</span><span class="sxs-lookup"><span data-stu-id="79be2-106">!=</span></span>  
  
 <span data-ttu-id="79be2-107">Operazioni di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="79be2-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="79be2-108">Operazioni di impostazione del supporto dei valori Null:</span><span class="sxs-lookup"><span data-stu-id="79be2-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="79be2-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="79be2-109">IS NULL</span></span>  
  
-   <span data-ttu-id="79be2-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="79be2-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="79be2-111">Distinzione esplicita</span><span class="sxs-lookup"><span data-stu-id="79be2-111">Explicit distinction</span></span>  
 <span data-ttu-id="79be2-112">Distinzione di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="79be2-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="79be2-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="79be2-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="79be2-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="79be2-114">GROUP BY</span></span>  
  
 <span data-ttu-id="79be2-115">Distinzione di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="79be2-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="79be2-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="79be2-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="79be2-117">Distinzione implicita</span><span class="sxs-lookup"><span data-stu-id="79be2-117">Implicit distinction</span></span>  
 <span data-ttu-id="79be2-118">Predicati e operazioni sui set (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="79be2-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="79be2-119">UNION</span><span class="sxs-lookup"><span data-stu-id="79be2-119">UNION</span></span>  
  
-   <span data-ttu-id="79be2-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="79be2-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="79be2-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="79be2-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="79be2-122">SET</span><span class="sxs-lookup"><span data-stu-id="79be2-122">SET</span></span>  
  
-   <span data-ttu-id="79be2-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="79be2-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="79be2-124">Predicati degli elementi (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="79be2-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="79be2-125">IN</span><span class="sxs-lookup"><span data-stu-id="79be2-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="79be2-126">Combinazioni supportate</span><span class="sxs-lookup"><span data-stu-id="79be2-126">Supported Combinations</span></span>  
 <span data-ttu-id="79be2-127">Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:</span><span class="sxs-lookup"><span data-stu-id="79be2-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="79be2-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="79be2-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="79be2-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="79be2-129">**!=**</span></span>|<span data-ttu-id="79be2-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="79be2-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="79be2-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="79be2-131">**DISTINCT**</span></span>|<span data-ttu-id="79be2-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="79be2-132">**UNION**</span></span><br /><br /> <span data-ttu-id="79be2-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="79be2-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="79be2-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="79be2-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="79be2-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="79be2-135">**SET**</span></span><br /><br /> <span data-ttu-id="79be2-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="79be2-136">**OVERLAPS**</span></span>|<span data-ttu-id="79be2-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="79be2-137">**IN**</span></span>|<span data-ttu-id="79be2-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="79be2-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="79be2-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="79be2-139">**>   >=**</span></span>|<span data-ttu-id="79be2-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="79be2-140">**ORDER BY**</span></span>|<span data-ttu-id="79be2-141">**È NULL**</span><span class="sxs-lookup"><span data-stu-id="79be2-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="79be2-142">**NON È NULL**</span><span class="sxs-lookup"><span data-stu-id="79be2-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="79be2-143">Tipo di entità</span><span class="sxs-lookup"><span data-stu-id="79be2-143">Entity type</span></span>|<span data-ttu-id="79be2-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="79be2-145">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="79be2-146">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="79be2-147">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="79be2-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="79be2-151">Tipo complesso</span><span class="sxs-lookup"><span data-stu-id="79be2-151">Complex type</span></span>|<span data-ttu-id="79be2-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="79be2-159">Riga</span><span class="sxs-lookup"><span data-stu-id="79be2-159">Row</span></span>|<span data-ttu-id="79be2-160">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="79be2-161">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="79be2-162">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="79be2-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-165">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="79be2-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="79be2-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="79be2-167">Primitive type</span></span>|<span data-ttu-id="79be2-168">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="79be2-168">Provider-specific</span></span>|<span data-ttu-id="79be2-169">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="79be2-169">Provider-specific</span></span>|<span data-ttu-id="79be2-170">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="79be2-170">Provider-specific</span></span>|<span data-ttu-id="79be2-171">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="79be2-171">Provider-specific</span></span>|<span data-ttu-id="79be2-172">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="79be2-172">Provider-specific</span></span>|<span data-ttu-id="79be2-173">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="79be2-173">Provider-specific</span></span>|<span data-ttu-id="79be2-174">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="79be2-174">Provider-specific</span></span>|  
|<span data-ttu-id="79be2-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="79be2-175">Multiset</span></span>|<span data-ttu-id="79be2-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="79be2-183">Rif</span><span class="sxs-lookup"><span data-stu-id="79be2-183">Ref</span></span>|<span data-ttu-id="79be2-184">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="79be2-185">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="79be2-186">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="79be2-187">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="79be2-188">Throw</span><span class="sxs-lookup"><span data-stu-id="79be2-188">Throw</span></span>|<span data-ttu-id="79be2-189">Throw</span><span class="sxs-lookup"><span data-stu-id="79be2-189">Throw</span></span>|<span data-ttu-id="79be2-190">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="79be2-191">Associazione</span><span class="sxs-lookup"><span data-stu-id="79be2-191">Association</span></span><br /><br /> <span data-ttu-id="79be2-192">tipo</span><span class="sxs-lookup"><span data-stu-id="79be2-192">type</span></span>|<span data-ttu-id="79be2-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-194">Throw</span><span class="sxs-lookup"><span data-stu-id="79be2-194">Throw</span></span>|<span data-ttu-id="79be2-195">Throw</span><span class="sxs-lookup"><span data-stu-id="79be2-195">Throw</span></span>|<span data-ttu-id="79be2-196">Throw</span><span class="sxs-lookup"><span data-stu-id="79be2-196">Throw</span></span>|<span data-ttu-id="79be2-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="79be2-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="79be2-200"><sup>1</sup>vengono confrontati in modo implicito i riferimenti delle istanze di tipo di entità specificato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="79be2-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="79be2-201">Un'istanza di entità non può essere confrontata con un riferimento esplicito.</span><span class="sxs-lookup"><span data-stu-id="79be2-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="79be2-202">Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="79be2-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="79be2-203">La query seguente comporta, ad esempio, la generazione di un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="79be2-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="79be2-204"><sup>2</sup>le proprietà dei tipi complessi vengono convertite prima dell'invio all'archivio, che quindi diventano confrontabili (purché tutte le relative proprietà sono confrontabili).</span><span class="sxs-lookup"><span data-stu-id="79be2-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="79be2-205">Vedere anche <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="79be2-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="79be2-206"><sup>3</sup>runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza ricorrere dell'archivio/provider.</span><span class="sxs-lookup"><span data-stu-id="79be2-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="79be2-207"><sup>4</sup>viene effettuato un tentativo di confrontare tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="79be2-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="79be2-208">Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.</span><span class="sxs-lookup"><span data-stu-id="79be2-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="79be2-209"><sup>5</sup>vengono confrontati tutti i singoli elementi dei riferimenti (che include il nome del set di entità e tutte le proprietà chiave del tipo di entità).</span><span class="sxs-lookup"><span data-stu-id="79be2-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79be2-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79be2-210">See also</span></span>

- [<span data-ttu-id="79be2-211">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="79be2-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
