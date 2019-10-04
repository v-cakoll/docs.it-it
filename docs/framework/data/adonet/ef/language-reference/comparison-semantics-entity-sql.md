---
title: Semantica di confronto (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 8d7868b0166f0a18824ec25e6cdf639deec665ac
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833939"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="75847-102">Semantica di confronto (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="75847-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="75847-103">L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:</span><span class="sxs-lookup"><span data-stu-id="75847-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="75847-104">Confronto esplicito</span><span class="sxs-lookup"><span data-stu-id="75847-104">Explicit comparison</span></span>  
 <span data-ttu-id="75847-105">Operazioni di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="75847-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="75847-106">!=</span><span class="sxs-lookup"><span data-stu-id="75847-106">!=</span></span>  
  
 <span data-ttu-id="75847-107">Operazioni di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="75847-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="75847-108">Operazioni di impostazione del supporto dei valori Null:</span><span class="sxs-lookup"><span data-stu-id="75847-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="75847-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="75847-109">IS NULL</span></span>  
  
- <span data-ttu-id="75847-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="75847-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="75847-111">Distinzione esplicita</span><span class="sxs-lookup"><span data-stu-id="75847-111">Explicit distinction</span></span>  
 <span data-ttu-id="75847-112">Distinzione di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="75847-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="75847-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="75847-113">DISTINCT</span></span>  
  
- <span data-ttu-id="75847-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="75847-114">GROUP BY</span></span>  
  
 <span data-ttu-id="75847-115">Distinzione di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="75847-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="75847-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="75847-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="75847-117">Distinzione implicita</span><span class="sxs-lookup"><span data-stu-id="75847-117">Implicit distinction</span></span>  
 <span data-ttu-id="75847-118">Predicati e operazioni sui set (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="75847-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="75847-119">UNION</span><span class="sxs-lookup"><span data-stu-id="75847-119">UNION</span></span>  
  
- <span data-ttu-id="75847-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="75847-120">INTERSECT</span></span>  
  
- <span data-ttu-id="75847-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="75847-121">EXCEPT</span></span>  
  
- <span data-ttu-id="75847-122">SET</span><span class="sxs-lookup"><span data-stu-id="75847-122">SET</span></span>  
  
- <span data-ttu-id="75847-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="75847-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="75847-124">Predicati degli elementi (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="75847-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="75847-125">IN</span><span class="sxs-lookup"><span data-stu-id="75847-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="75847-126">Combinazioni supportate</span><span class="sxs-lookup"><span data-stu-id="75847-126">Supported Combinations</span></span>  
 <span data-ttu-id="75847-127">Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:</span><span class="sxs-lookup"><span data-stu-id="75847-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="75847-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="75847-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="75847-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="75847-129">**!=**</span></span>|<span data-ttu-id="75847-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="75847-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="75847-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="75847-131">**DISTINCT**</span></span>|<span data-ttu-id="75847-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="75847-132">**UNION**</span></span><br /><br /> <span data-ttu-id="75847-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="75847-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="75847-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="75847-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="75847-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="75847-135">**SET**</span></span><br /><br /> <span data-ttu-id="75847-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="75847-136">**OVERLAPS**</span></span>|<span data-ttu-id="75847-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="75847-137">**IN**</span></span>|<span data-ttu-id="75847-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="75847-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="75847-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="75847-139">**>   >=**</span></span>|<span data-ttu-id="75847-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="75847-140">**ORDER BY**</span></span>|<span data-ttu-id="75847-141">**È NULL**</span><span class="sxs-lookup"><span data-stu-id="75847-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="75847-142">**NON È NULL**</span><span class="sxs-lookup"><span data-stu-id="75847-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="75847-143">Tipo di entità</span><span class="sxs-lookup"><span data-stu-id="75847-143">Entity type</span></span>|<span data-ttu-id="75847-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="75847-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="75847-145">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="75847-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="75847-146">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="75847-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="75847-147">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="75847-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="75847-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="75847-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="75847-151">Tipo complesso</span><span class="sxs-lookup"><span data-stu-id="75847-151">Complex type</span></span>|<span data-ttu-id="75847-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="75847-159">Riga</span><span class="sxs-lookup"><span data-stu-id="75847-159">Row</span></span>|<span data-ttu-id="75847-160">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="75847-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="75847-161">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="75847-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="75847-162">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="75847-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="75847-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-165">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="75847-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="75847-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="75847-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="75847-167">Primitive type</span></span>|<span data-ttu-id="75847-168">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="75847-168">Provider-specific</span></span>|<span data-ttu-id="75847-169">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="75847-169">Provider-specific</span></span>|<span data-ttu-id="75847-170">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="75847-170">Provider-specific</span></span>|<span data-ttu-id="75847-171">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="75847-171">Provider-specific</span></span>|<span data-ttu-id="75847-172">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="75847-172">Provider-specific</span></span>|<span data-ttu-id="75847-173">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="75847-173">Provider-specific</span></span>|<span data-ttu-id="75847-174">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="75847-174">Provider-specific</span></span>|  
|<span data-ttu-id="75847-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="75847-175">Multiset</span></span>|<span data-ttu-id="75847-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="75847-183">Rif</span><span class="sxs-lookup"><span data-stu-id="75847-183">Ref</span></span>|<span data-ttu-id="75847-184">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="75847-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="75847-185">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="75847-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="75847-186">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="75847-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="75847-187">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="75847-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="75847-188">Throw</span><span class="sxs-lookup"><span data-stu-id="75847-188">Throw</span></span>|<span data-ttu-id="75847-189">Throw</span><span class="sxs-lookup"><span data-stu-id="75847-189">Throw</span></span>|<span data-ttu-id="75847-190">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="75847-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="75847-191">Associazione</span><span class="sxs-lookup"><span data-stu-id="75847-191">Association</span></span><br /><br /> <span data-ttu-id="75847-192">type</span><span class="sxs-lookup"><span data-stu-id="75847-192">type</span></span>|<span data-ttu-id="75847-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-194">Throw</span><span class="sxs-lookup"><span data-stu-id="75847-194">Throw</span></span>|<span data-ttu-id="75847-195">Throw</span><span class="sxs-lookup"><span data-stu-id="75847-195">Throw</span></span>|<span data-ttu-id="75847-196">Throw</span><span class="sxs-lookup"><span data-stu-id="75847-196">Throw</span></span>|<span data-ttu-id="75847-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="75847-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="75847-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="75847-200"><sup>1</sup> I riferimenti delle istanze del tipo di entità specificate vengono confrontati in modo implicito, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="75847-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="75847-201">Un'istanza di entità non può essere confrontata con un riferimento esplicito.</span><span class="sxs-lookup"><span data-stu-id="75847-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="75847-202">Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="75847-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="75847-203">La query seguente comporta, ad esempio, la generazione di un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="75847-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="75847-204"><sup>2</sup> Le proprietà dei tipi complessi sono bidimensionali prima di essere inviate all'archivio, quindi diventano confrontabili (purché tutte le relative proprietà siano confrontabili).</span><span class="sxs-lookup"><span data-stu-id="75847-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="75847-205">Vedere anche <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="75847-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="75847-206"><sup>3</sup> Il runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza coinvolgere il provider o l'archivio.</span><span class="sxs-lookup"><span data-stu-id="75847-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="75847-207"><sup>4</sup> Viene effettuato un tentativo di confrontare tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="75847-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="75847-208">Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.</span><span class="sxs-lookup"><span data-stu-id="75847-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="75847-209"><sup>5</sup> Vengono confrontati tutti i singoli elementi dei riferimenti (inclusi il nome del set di entità e tutte le proprietà chiave del tipo di entità).</span><span class="sxs-lookup"><span data-stu-id="75847-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75847-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75847-210">See also</span></span>

- [<span data-ttu-id="75847-211">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="75847-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
