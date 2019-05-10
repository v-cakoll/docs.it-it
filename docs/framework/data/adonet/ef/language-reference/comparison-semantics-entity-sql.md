---
title: Semantica di confronto (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 2ca91861d4830321168e96fb200c4889dc33b04b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631709"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="462a5-102">Semantica di confronto (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="462a5-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="462a5-103">L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:</span><span class="sxs-lookup"><span data-stu-id="462a5-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="462a5-104">Confronto esplicito</span><span class="sxs-lookup"><span data-stu-id="462a5-104">Explicit comparison</span></span>  
 <span data-ttu-id="462a5-105">Operazioni di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="462a5-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="462a5-106">!=</span><span class="sxs-lookup"><span data-stu-id="462a5-106">!=</span></span>  
  
 <span data-ttu-id="462a5-107">Operazioni di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="462a5-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="462a5-108">Operazioni di impostazione del supporto dei valori Null:</span><span class="sxs-lookup"><span data-stu-id="462a5-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="462a5-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="462a5-109">IS NULL</span></span>  
  
- <span data-ttu-id="462a5-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="462a5-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="462a5-111">Distinzione esplicita</span><span class="sxs-lookup"><span data-stu-id="462a5-111">Explicit distinction</span></span>  
 <span data-ttu-id="462a5-112">Distinzione di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="462a5-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="462a5-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="462a5-113">DISTINCT</span></span>  
  
- <span data-ttu-id="462a5-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="462a5-114">GROUP BY</span></span>  
  
 <span data-ttu-id="462a5-115">Distinzione di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="462a5-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="462a5-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="462a5-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="462a5-117">Distinzione implicita</span><span class="sxs-lookup"><span data-stu-id="462a5-117">Implicit distinction</span></span>  
 <span data-ttu-id="462a5-118">Predicati e operazioni sui set (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="462a5-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="462a5-119">UNION</span><span class="sxs-lookup"><span data-stu-id="462a5-119">UNION</span></span>  
  
- <span data-ttu-id="462a5-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="462a5-120">INTERSECT</span></span>  
  
- <span data-ttu-id="462a5-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="462a5-121">EXCEPT</span></span>  
  
- <span data-ttu-id="462a5-122">SET</span><span class="sxs-lookup"><span data-stu-id="462a5-122">SET</span></span>  
  
- <span data-ttu-id="462a5-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="462a5-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="462a5-124">Predicati degli elementi (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="462a5-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="462a5-125">IN</span><span class="sxs-lookup"><span data-stu-id="462a5-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="462a5-126">Combinazioni supportate</span><span class="sxs-lookup"><span data-stu-id="462a5-126">Supported Combinations</span></span>  
 <span data-ttu-id="462a5-127">Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:</span><span class="sxs-lookup"><span data-stu-id="462a5-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="462a5-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="462a5-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="462a5-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="462a5-129">**!=**</span></span>|<span data-ttu-id="462a5-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="462a5-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="462a5-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="462a5-131">**DISTINCT**</span></span>|<span data-ttu-id="462a5-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="462a5-132">**UNION**</span></span><br /><br /> <span data-ttu-id="462a5-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="462a5-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="462a5-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="462a5-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="462a5-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="462a5-135">**SET**</span></span><br /><br /> <span data-ttu-id="462a5-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="462a5-136">**OVERLAPS**</span></span>|<span data-ttu-id="462a5-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="462a5-137">**IN**</span></span>|<span data-ttu-id="462a5-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="462a5-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="462a5-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="462a5-139">**>   >=**</span></span>|<span data-ttu-id="462a5-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="462a5-140">**ORDER BY**</span></span>|<span data-ttu-id="462a5-141">**È NULL**</span><span class="sxs-lookup"><span data-stu-id="462a5-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="462a5-142">**NON È NULL**</span><span class="sxs-lookup"><span data-stu-id="462a5-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="462a5-143">Tipo di entità</span><span class="sxs-lookup"><span data-stu-id="462a5-143">Entity type</span></span>|<span data-ttu-id="462a5-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="462a5-145">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="462a5-146">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="462a5-147">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="462a5-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="462a5-151">Tipo complesso</span><span class="sxs-lookup"><span data-stu-id="462a5-151">Complex type</span></span>|<span data-ttu-id="462a5-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="462a5-159">Riga</span><span class="sxs-lookup"><span data-stu-id="462a5-159">Row</span></span>|<span data-ttu-id="462a5-160">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="462a5-161">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="462a5-162">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="462a5-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-165">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="462a5-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="462a5-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="462a5-167">Primitive type</span></span>|<span data-ttu-id="462a5-168">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="462a5-168">Provider-specific</span></span>|<span data-ttu-id="462a5-169">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="462a5-169">Provider-specific</span></span>|<span data-ttu-id="462a5-170">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="462a5-170">Provider-specific</span></span>|<span data-ttu-id="462a5-171">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="462a5-171">Provider-specific</span></span>|<span data-ttu-id="462a5-172">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="462a5-172">Provider-specific</span></span>|<span data-ttu-id="462a5-173">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="462a5-173">Provider-specific</span></span>|<span data-ttu-id="462a5-174">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="462a5-174">Provider-specific</span></span>|  
|<span data-ttu-id="462a5-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="462a5-175">Multiset</span></span>|<span data-ttu-id="462a5-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="462a5-183">Rif</span><span class="sxs-lookup"><span data-stu-id="462a5-183">Ref</span></span>|<span data-ttu-id="462a5-184">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="462a5-185">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="462a5-186">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="462a5-187">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="462a5-188">Throw</span><span class="sxs-lookup"><span data-stu-id="462a5-188">Throw</span></span>|<span data-ttu-id="462a5-189">Throw</span><span class="sxs-lookup"><span data-stu-id="462a5-189">Throw</span></span>|<span data-ttu-id="462a5-190">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="462a5-191">Associazione</span><span class="sxs-lookup"><span data-stu-id="462a5-191">Association</span></span><br /><br /> <span data-ttu-id="462a5-192">tipo</span><span class="sxs-lookup"><span data-stu-id="462a5-192">type</span></span>|<span data-ttu-id="462a5-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-194">Throw</span><span class="sxs-lookup"><span data-stu-id="462a5-194">Throw</span></span>|<span data-ttu-id="462a5-195">Throw</span><span class="sxs-lookup"><span data-stu-id="462a5-195">Throw</span></span>|<span data-ttu-id="462a5-196">Throw</span><span class="sxs-lookup"><span data-stu-id="462a5-196">Throw</span></span>|<span data-ttu-id="462a5-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="462a5-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="462a5-200"><sup>1</sup>vengono confrontati in modo implicito i riferimenti delle istanze di tipo di entità specificato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="462a5-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="462a5-201">Un'istanza di entità non può essere confrontata con un riferimento esplicito.</span><span class="sxs-lookup"><span data-stu-id="462a5-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="462a5-202">Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="462a5-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="462a5-203">La query seguente comporta, ad esempio, la generazione di un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="462a5-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="462a5-204"><sup>2</sup>le proprietà dei tipi complessi vengono convertite prima dell'invio all'archivio, che quindi diventano confrontabili (purché tutte le relative proprietà sono confrontabili).</span><span class="sxs-lookup"><span data-stu-id="462a5-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="462a5-205">Vedere anche <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="462a5-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="462a5-206"><sup>3</sup>runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza ricorrere dell'archivio/provider.</span><span class="sxs-lookup"><span data-stu-id="462a5-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="462a5-207"><sup>4</sup>viene effettuato un tentativo di confrontare tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="462a5-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="462a5-208">Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.</span><span class="sxs-lookup"><span data-stu-id="462a5-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="462a5-209"><sup>5</sup>vengono confrontati tutti i singoli elementi dei riferimenti (che include il nome del set di entità e tutte le proprietà chiave del tipo di entità).</span><span class="sxs-lookup"><span data-stu-id="462a5-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="462a5-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="462a5-210">See also</span></span>

- [<span data-ttu-id="462a5-211">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="462a5-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
