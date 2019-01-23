---
title: Semantica di confronto (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 371999df0fb3177ecc90f9b1fa43d457a51bfd7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492494"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="38fa6-102">Semantica di confronto (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="38fa6-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="38fa6-103">L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:</span><span class="sxs-lookup"><span data-stu-id="38fa6-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="38fa6-104">Confronto esplicito</span><span class="sxs-lookup"><span data-stu-id="38fa6-104">Explicit comparison</span></span>  
 <span data-ttu-id="38fa6-105">Operazioni di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="38fa6-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="38fa6-106">!=</span><span class="sxs-lookup"><span data-stu-id="38fa6-106">!=</span></span>  
  
 <span data-ttu-id="38fa6-107">Operazioni di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="38fa6-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="38fa6-108">Operazioni di impostazione del supporto dei valori Null:</span><span class="sxs-lookup"><span data-stu-id="38fa6-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="38fa6-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="38fa6-109">IS NULL</span></span>  
  
-   <span data-ttu-id="38fa6-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="38fa6-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="38fa6-111">Distinzione esplicita</span><span class="sxs-lookup"><span data-stu-id="38fa6-111">Explicit distinction</span></span>  
 <span data-ttu-id="38fa6-112">Distinzione di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="38fa6-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="38fa6-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="38fa6-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="38fa6-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="38fa6-114">GROUP BY</span></span>  
  
 <span data-ttu-id="38fa6-115">Distinzione di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="38fa6-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="38fa6-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="38fa6-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="38fa6-117">Distinzione implicita</span><span class="sxs-lookup"><span data-stu-id="38fa6-117">Implicit distinction</span></span>  
 <span data-ttu-id="38fa6-118">Predicati e operazioni sui set (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="38fa6-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="38fa6-119">UNION</span><span class="sxs-lookup"><span data-stu-id="38fa6-119">UNION</span></span>  
  
-   <span data-ttu-id="38fa6-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="38fa6-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="38fa6-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="38fa6-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="38fa6-122">SET</span><span class="sxs-lookup"><span data-stu-id="38fa6-122">SET</span></span>  
  
-   <span data-ttu-id="38fa6-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="38fa6-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="38fa6-124">Predicati degli elementi (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="38fa6-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="38fa6-125">IN</span><span class="sxs-lookup"><span data-stu-id="38fa6-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="38fa6-126">Combinazioni supportate</span><span class="sxs-lookup"><span data-stu-id="38fa6-126">Supported Combinations</span></span>  
 <span data-ttu-id="38fa6-127">Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:</span><span class="sxs-lookup"><span data-stu-id="38fa6-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="38fa6-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="38fa6-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="38fa6-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="38fa6-129">**!=**</span></span>|<span data-ttu-id="38fa6-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="38fa6-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="38fa6-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="38fa6-131">**DISTINCT**</span></span>|<span data-ttu-id="38fa6-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="38fa6-132">**UNION**</span></span><br /><br /> <span data-ttu-id="38fa6-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="38fa6-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="38fa6-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="38fa6-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="38fa6-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="38fa6-135">**SET**</span></span><br /><br /> <span data-ttu-id="38fa6-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="38fa6-136">**OVERLAPS**</span></span>|<span data-ttu-id="38fa6-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="38fa6-137">**IN**</span></span>|<span data-ttu-id="38fa6-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="38fa6-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="38fa6-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="38fa6-139">**>   >=**</span></span>|<span data-ttu-id="38fa6-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="38fa6-140">**ORDER BY**</span></span>|<span data-ttu-id="38fa6-141">**È NULL**</span><span class="sxs-lookup"><span data-stu-id="38fa6-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="38fa6-142">**NON È NULL**</span><span class="sxs-lookup"><span data-stu-id="38fa6-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="38fa6-143">Tipo di entità</span><span class="sxs-lookup"><span data-stu-id="38fa6-143">Entity type</span></span>|<span data-ttu-id="38fa6-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="38fa6-145">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="38fa6-146">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="38fa6-147">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="38fa6-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="38fa6-151">Tipo complesso</span><span class="sxs-lookup"><span data-stu-id="38fa6-151">Complex type</span></span>|<span data-ttu-id="38fa6-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="38fa6-159">Riga</span><span class="sxs-lookup"><span data-stu-id="38fa6-159">Row</span></span>|<span data-ttu-id="38fa6-160">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="38fa6-161">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="38fa6-162">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="38fa6-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-165">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="38fa6-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="38fa6-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="38fa6-167">Primitive type</span></span>|<span data-ttu-id="38fa6-168">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="38fa6-168">Provider-specific</span></span>|<span data-ttu-id="38fa6-169">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="38fa6-169">Provider-specific</span></span>|<span data-ttu-id="38fa6-170">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="38fa6-170">Provider-specific</span></span>|<span data-ttu-id="38fa6-171">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="38fa6-171">Provider-specific</span></span>|<span data-ttu-id="38fa6-172">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="38fa6-172">Provider-specific</span></span>|<span data-ttu-id="38fa6-173">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="38fa6-173">Provider-specific</span></span>|<span data-ttu-id="38fa6-174">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="38fa6-174">Provider-specific</span></span>|  
|<span data-ttu-id="38fa6-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="38fa6-175">Multiset</span></span>|<span data-ttu-id="38fa6-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="38fa6-183">Rif</span><span class="sxs-lookup"><span data-stu-id="38fa6-183">Ref</span></span>|<span data-ttu-id="38fa6-184">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="38fa6-185">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="38fa6-186">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="38fa6-187">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="38fa6-188">Throw</span><span class="sxs-lookup"><span data-stu-id="38fa6-188">Throw</span></span>|<span data-ttu-id="38fa6-189">Throw</span><span class="sxs-lookup"><span data-stu-id="38fa6-189">Throw</span></span>|<span data-ttu-id="38fa6-190">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="38fa6-191">Associazione</span><span class="sxs-lookup"><span data-stu-id="38fa6-191">Association</span></span><br /><br /> <span data-ttu-id="38fa6-192">tipo</span><span class="sxs-lookup"><span data-stu-id="38fa6-192">type</span></span>|<span data-ttu-id="38fa6-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-194">Throw</span><span class="sxs-lookup"><span data-stu-id="38fa6-194">Throw</span></span>|<span data-ttu-id="38fa6-195">Throw</span><span class="sxs-lookup"><span data-stu-id="38fa6-195">Throw</span></span>|<span data-ttu-id="38fa6-196">Throw</span><span class="sxs-lookup"><span data-stu-id="38fa6-196">Throw</span></span>|<span data-ttu-id="38fa6-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="38fa6-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="38fa6-200"><sup>1</sup>vengono confrontati in modo implicito i riferimenti delle istanze di tipo di entità specificato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="38fa6-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="38fa6-201">Un'istanza di entità non può essere confrontata con un riferimento esplicito.</span><span class="sxs-lookup"><span data-stu-id="38fa6-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="38fa6-202">Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="38fa6-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="38fa6-203">La query seguente comporta, ad esempio, la generazione di un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="38fa6-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="38fa6-204"><sup>2</sup>le proprietà dei tipi complessi vengono convertite prima dell'invio all'archivio, che quindi diventano confrontabili (purché tutte le relative proprietà sono confrontabili).</span><span class="sxs-lookup"><span data-stu-id="38fa6-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="38fa6-205">Vedere anche <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="38fa6-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="38fa6-206"><sup>3</sup>runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza ricorrere dell'archivio/provider.</span><span class="sxs-lookup"><span data-stu-id="38fa6-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="38fa6-207"><sup>4</sup>viene effettuato un tentativo di confrontare tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="38fa6-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="38fa6-208">Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.</span><span class="sxs-lookup"><span data-stu-id="38fa6-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="38fa6-209"><sup>5</sup>vengono confrontati tutti i singoli elementi dei riferimenti (che include il nome del set di entità e tutte le proprietà chiave del tipo di entità).</span><span class="sxs-lookup"><span data-stu-id="38fa6-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38fa6-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38fa6-210">See also</span></span>
- [<span data-ttu-id="38fa6-211">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="38fa6-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
