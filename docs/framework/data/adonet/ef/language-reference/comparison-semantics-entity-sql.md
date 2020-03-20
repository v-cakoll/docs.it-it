---
title: Semantica di confronto (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150454"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="25e5a-102">Semantica di confronto (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="25e5a-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="25e5a-103">L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:</span><span class="sxs-lookup"><span data-stu-id="25e5a-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="25e5a-104">Confronto esplicito</span><span class="sxs-lookup"><span data-stu-id="25e5a-104">Explicit comparison</span></span>  
 <span data-ttu-id="25e5a-105">Operazioni di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="25e5a-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="25e5a-106">!=</span><span class="sxs-lookup"><span data-stu-id="25e5a-106">!=</span></span>  
  
 <span data-ttu-id="25e5a-107">Operazioni di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="25e5a-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="25e5a-108">Operazioni di impostazione del supporto dei valori Null:</span><span class="sxs-lookup"><span data-stu-id="25e5a-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="25e5a-109">È NULL</span><span class="sxs-lookup"><span data-stu-id="25e5a-109">IS NULL</span></span>  
  
- <span data-ttu-id="25e5a-110">IS NOT NULL (NON È NULL)</span><span class="sxs-lookup"><span data-stu-id="25e5a-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="25e5a-111">Distinzione esplicita</span><span class="sxs-lookup"><span data-stu-id="25e5a-111">Explicit distinction</span></span>  
 <span data-ttu-id="25e5a-112">Distinzione di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="25e5a-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="25e5a-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="25e5a-113">DISTINCT</span></span>  
  
- <span data-ttu-id="25e5a-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="25e5a-114">GROUP BY</span></span>  
  
 <span data-ttu-id="25e5a-115">Distinzione di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="25e5a-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="25e5a-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="25e5a-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="25e5a-117">Distinzione implicita</span><span class="sxs-lookup"><span data-stu-id="25e5a-117">Implicit distinction</span></span>  
 <span data-ttu-id="25e5a-118">Predicati e operazioni sui set (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="25e5a-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="25e5a-119">UNION</span><span class="sxs-lookup"><span data-stu-id="25e5a-119">UNION</span></span>  
  
- <span data-ttu-id="25e5a-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="25e5a-120">INTERSECT</span></span>  
  
- <span data-ttu-id="25e5a-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="25e5a-121">EXCEPT</span></span>  
  
- <span data-ttu-id="25e5a-122">SET</span><span class="sxs-lookup"><span data-stu-id="25e5a-122">SET</span></span>  
  
- <span data-ttu-id="25e5a-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="25e5a-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="25e5a-124">Predicati degli elementi (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="25e5a-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="25e5a-125">IN</span><span class="sxs-lookup"><span data-stu-id="25e5a-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="25e5a-126">Combinazioni supportate</span><span class="sxs-lookup"><span data-stu-id="25e5a-126">Supported Combinations</span></span>  
 <span data-ttu-id="25e5a-127">Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:</span><span class="sxs-lookup"><span data-stu-id="25e5a-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="25e5a-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="25e5a-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="25e5a-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="25e5a-129">**!=**</span></span>|<span data-ttu-id="25e5a-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="25e5a-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="25e5a-131">**Distinti**</span><span class="sxs-lookup"><span data-stu-id="25e5a-131">**DISTINCT**</span></span>|<span data-ttu-id="25e5a-132">**Unione**</span><span class="sxs-lookup"><span data-stu-id="25e5a-132">**UNION**</span></span><br /><br /> <span data-ttu-id="25e5a-133">**Intersect**</span><span class="sxs-lookup"><span data-stu-id="25e5a-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="25e5a-134">**Tranne**</span><span class="sxs-lookup"><span data-stu-id="25e5a-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="25e5a-135">**Impostare**</span><span class="sxs-lookup"><span data-stu-id="25e5a-135">**SET**</span></span><br /><br /> <span data-ttu-id="25e5a-136">**Sovrapposizioni**</span><span class="sxs-lookup"><span data-stu-id="25e5a-136">**OVERLAPS**</span></span>|<span data-ttu-id="25e5a-137">**Pollici**</span><span class="sxs-lookup"><span data-stu-id="25e5a-137">**IN**</span></span>|<span data-ttu-id="25e5a-138">**< <**</span><span class="sxs-lookup"><span data-stu-id="25e5a-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="25e5a-139">**> >**</span><span class="sxs-lookup"><span data-stu-id="25e5a-139">**>   >=**</span></span>|<span data-ttu-id="25e5a-140">**ORDINA PER**</span><span class="sxs-lookup"><span data-stu-id="25e5a-140">**ORDER BY**</span></span>|<span data-ttu-id="25e5a-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="25e5a-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="25e5a-142">**NON È NULL**</span><span class="sxs-lookup"><span data-stu-id="25e5a-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="25e5a-143">Tipo di entità</span><span class="sxs-lookup"><span data-stu-id="25e5a-143">Entity type</span></span>|<span data-ttu-id="25e5a-144">Riifd.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="25e5a-145">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="25e5a-146">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="25e5a-147">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="25e5a-148">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-149">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-150">Riifd.<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="25e5a-151">Tipo complesso</span><span class="sxs-lookup"><span data-stu-id="25e5a-151">Complex type</span></span>|<span data-ttu-id="25e5a-152">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-153">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-154">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-155">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-156">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-157">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-158">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="25e5a-159">Riga</span><span class="sxs-lookup"><span data-stu-id="25e5a-159">Row</span></span>|<span data-ttu-id="25e5a-160">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="25e5a-161">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="25e5a-162">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="25e5a-163">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-164">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-165">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="25e5a-166">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="25e5a-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="25e5a-167">Primitive type</span></span>|<span data-ttu-id="25e5a-168">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="25e5a-168">Provider-specific</span></span>|<span data-ttu-id="25e5a-169">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="25e5a-169">Provider-specific</span></span>|<span data-ttu-id="25e5a-170">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="25e5a-170">Provider-specific</span></span>|<span data-ttu-id="25e5a-171">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="25e5a-171">Provider-specific</span></span>|<span data-ttu-id="25e5a-172">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="25e5a-172">Provider-specific</span></span>|<span data-ttu-id="25e5a-173">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="25e5a-173">Provider-specific</span></span>|<span data-ttu-id="25e5a-174">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="25e5a-174">Provider-specific</span></span>|  
|<span data-ttu-id="25e5a-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="25e5a-175">Multiset</span></span>|<span data-ttu-id="25e5a-176">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-177">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-178">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-179">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-180">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-181">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-182">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="25e5a-183">Rif</span><span class="sxs-lookup"><span data-stu-id="25e5a-183">Ref</span></span>|<span data-ttu-id="25e5a-184">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="25e5a-185">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="25e5a-186">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="25e5a-187">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="25e5a-188">Throw</span><span class="sxs-lookup"><span data-stu-id="25e5a-188">Throw</span></span>|<span data-ttu-id="25e5a-189">Throw</span><span class="sxs-lookup"><span data-stu-id="25e5a-189">Throw</span></span>|<span data-ttu-id="25e5a-190">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="25e5a-191">Association Rules</span><span class="sxs-lookup"><span data-stu-id="25e5a-191">Association</span></span><br /><br /> <span data-ttu-id="25e5a-192">type</span><span class="sxs-lookup"><span data-stu-id="25e5a-192">type</span></span>|<span data-ttu-id="25e5a-193">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-194">Throw</span><span class="sxs-lookup"><span data-stu-id="25e5a-194">Throw</span></span>|<span data-ttu-id="25e5a-195">Throw</span><span class="sxs-lookup"><span data-stu-id="25e5a-195">Throw</span></span>|<span data-ttu-id="25e5a-196">Throw</span><span class="sxs-lookup"><span data-stu-id="25e5a-196">Throw</span></span>|<span data-ttu-id="25e5a-197">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-198">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="25e5a-199">Lancio<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="25e5a-200"><sup>1 : il</sup> nome del I riferimenti delle istanze del tipo di entità specificato vengono confrontati in modo implicito, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="25e5a-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="25e5a-201">Un'istanza di entità non può essere confrontata con un riferimento esplicito.</span><span class="sxs-lookup"><span data-stu-id="25e5a-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="25e5a-202">Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="25e5a-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="25e5a-203">La query seguente comporta, ad esempio, la generazione di un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="25e5a-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="25e5a-204"><sup>2 Il</sup> nome del sistema Le proprietà dei tipi complessi vengono appiattite prima di essere inviate al negozio, in modo che diventino comparabili (a condizione che tutte le loro proprietà siano comparabili).</span><span class="sxs-lookup"><span data-stu-id="25e5a-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="25e5a-205">Vedi anche <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="25e5a-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="25e5a-206"><sup>3 (COM del</sup> nome Il runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza coinvolgere il provider/archivio.</span><span class="sxs-lookup"><span data-stu-id="25e5a-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="25e5a-207"><sup>4 DEL psu'</sup> Viene effettuato un tentativo di confrontare tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="25e5a-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="25e5a-208">Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.</span><span class="sxs-lookup"><span data-stu-id="25e5a-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="25e5a-209">5 Del numero <sup>3(</sup> Vengono confrontati tutti i singoli elementi dei riferimenti (inclusi il nome del set di entità e tutte le proprietà chiave del tipo di entità).</span><span class="sxs-lookup"><span data-stu-id="25e5a-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e5a-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25e5a-210">See also</span></span>

- [<span data-ttu-id="25e5a-211">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="25e5a-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
