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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c6d22b72e05e6293a7fd3bcf7ddfba6e116e441f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="ea086-102">Semantica di confronto (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ea086-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="ea086-103">L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:</span><span class="sxs-lookup"><span data-stu-id="ea086-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="ea086-104">Confronto esplicito</span><span class="sxs-lookup"><span data-stu-id="ea086-104">Explicit comparison</span></span>  
 <span data-ttu-id="ea086-105">Operazioni di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="ea086-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="ea086-106">!=</span><span class="sxs-lookup"><span data-stu-id="ea086-106">!=</span></span>  
  
 <span data-ttu-id="ea086-107">Operazioni di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="ea086-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 <span data-ttu-id="ea086-108">Operazioni di impostazione del supporto dei valori Null:</span><span class="sxs-lookup"><span data-stu-id="ea086-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="ea086-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="ea086-109">IS NULL</span></span>  
  
-   <span data-ttu-id="ea086-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ea086-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="ea086-111">Distinzione esplicita</span><span class="sxs-lookup"><span data-stu-id="ea086-111">Explicit distinction</span></span>  
 <span data-ttu-id="ea086-112">Distinzione di uguaglianza:</span><span class="sxs-lookup"><span data-stu-id="ea086-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="ea086-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="ea086-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="ea086-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="ea086-114">GROUP BY</span></span>  
  
 <span data-ttu-id="ea086-115">Distinzione di ordinamento:</span><span class="sxs-lookup"><span data-stu-id="ea086-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="ea086-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="ea086-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="ea086-117">Distinzione implicita</span><span class="sxs-lookup"><span data-stu-id="ea086-117">Implicit distinction</span></span>  
 <span data-ttu-id="ea086-118">Predicati e operazioni sui set (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="ea086-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="ea086-119">UNION</span><span class="sxs-lookup"><span data-stu-id="ea086-119">UNION</span></span>  
  
-   <span data-ttu-id="ea086-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="ea086-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="ea086-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="ea086-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="ea086-122">SET</span><span class="sxs-lookup"><span data-stu-id="ea086-122">SET</span></span>  
  
-   <span data-ttu-id="ea086-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="ea086-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="ea086-124">Predicati degli elementi (uguaglianza):</span><span class="sxs-lookup"><span data-stu-id="ea086-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="ea086-125">IN</span><span class="sxs-lookup"><span data-stu-id="ea086-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="ea086-126">Combinazioni supportate</span><span class="sxs-lookup"><span data-stu-id="ea086-126">Supported Combinations</span></span>  
 <span data-ttu-id="ea086-127">Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:</span><span class="sxs-lookup"><span data-stu-id="ea086-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="ea086-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="ea086-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="ea086-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="ea086-129">**!=**</span></span>|<span data-ttu-id="ea086-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="ea086-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="ea086-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="ea086-131">**DISTINCT**</span></span>|<span data-ttu-id="ea086-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="ea086-132">**UNION**</span></span><br /><br /> <span data-ttu-id="ea086-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="ea086-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="ea086-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="ea086-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="ea086-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="ea086-135">**SET**</span></span><br /><br /> <span data-ttu-id="ea086-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="ea086-136">**OVERLAPS**</span></span>|<span data-ttu-id="ea086-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="ea086-137">**IN**</span></span>|<span data-ttu-id="ea086-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="ea086-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="ea086-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="ea086-139">**>   >=**</span></span>|<span data-ttu-id="ea086-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="ea086-140">**ORDER BY**</span></span>|<span data-ttu-id="ea086-141">**È NULL**</span><span class="sxs-lookup"><span data-stu-id="ea086-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="ea086-142">**NON È NULL**</span><span class="sxs-lookup"><span data-stu-id="ea086-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="ea086-143">Tipo di entità</span><span class="sxs-lookup"><span data-stu-id="ea086-143">Entity type</span></span>|<span data-ttu-id="ea086-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="ea086-145">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="ea086-146">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="ea086-147">Tutte le proprietà<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="ea086-148">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-149">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="ea086-151">Tipo complesso</span><span class="sxs-lookup"><span data-stu-id="ea086-151">Complex type</span></span>|<span data-ttu-id="ea086-152">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-153">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-154">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-155">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-156">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-157">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-158">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="ea086-159">Riga</span><span class="sxs-lookup"><span data-stu-id="ea086-159">Row</span></span>|<span data-ttu-id="ea086-160">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="ea086-161">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="ea086-162">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="ea086-163">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-164">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-165">Tutte le proprietà<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="ea086-166">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="ea086-167">Tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="ea086-167">Primitive type</span></span>|<span data-ttu-id="ea086-168">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="ea086-168">Provider-specific</span></span>|<span data-ttu-id="ea086-169">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="ea086-169">Provider-specific</span></span>|<span data-ttu-id="ea086-170">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="ea086-170">Provider-specific</span></span>|<span data-ttu-id="ea086-171">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="ea086-171">Provider-specific</span></span>|<span data-ttu-id="ea086-172">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="ea086-172">Provider-specific</span></span>|<span data-ttu-id="ea086-173">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="ea086-173">Provider-specific</span></span>|<span data-ttu-id="ea086-174">Specifico del provider</span><span class="sxs-lookup"><span data-stu-id="ea086-174">Provider-specific</span></span>|  
|<span data-ttu-id="ea086-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="ea086-175">Multiset</span></span>|<span data-ttu-id="ea086-176">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-177">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-178">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-179">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-180">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-181">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-182">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="ea086-183">Rif</span><span class="sxs-lookup"><span data-stu-id="ea086-183">Ref</span></span>|<span data-ttu-id="ea086-184">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="ea086-185">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="ea086-186">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="ea086-187">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="ea086-188">Throw</span><span class="sxs-lookup"><span data-stu-id="ea086-188">Throw</span></span>|<span data-ttu-id="ea086-189">Throw</span><span class="sxs-lookup"><span data-stu-id="ea086-189">Throw</span></span>|<span data-ttu-id="ea086-190">Sì<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="ea086-191">Associazione</span><span class="sxs-lookup"><span data-stu-id="ea086-191">Association</span></span><br /><br /> <span data-ttu-id="ea086-192">tipo</span><span class="sxs-lookup"><span data-stu-id="ea086-192">type</span></span>|<span data-ttu-id="ea086-193">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-194">Throw</span><span class="sxs-lookup"><span data-stu-id="ea086-194">Throw</span></span>|<span data-ttu-id="ea086-195">Throw</span><span class="sxs-lookup"><span data-stu-id="ea086-195">Throw</span></span>|<span data-ttu-id="ea086-196">Throw</span><span class="sxs-lookup"><span data-stu-id="ea086-196">Throw</span></span>|<span data-ttu-id="ea086-197">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-198">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="ea086-199">Generare<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="ea086-200"><sup>1</sup>vengono confrontati in modo implicito i riferimenti delle istanze di tipo di entità specificato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ea086-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="ea086-201">Un'istanza di entità non può essere confrontata con un riferimento esplicito.</span><span class="sxs-lookup"><span data-stu-id="ea086-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="ea086-202">Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ea086-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="ea086-203">La query seguente comporta, ad esempio, la generazione di un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="ea086-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="ea086-204"><sup>2</sup>le proprietà dei tipi complessi sono impostate come bidimensionali prima dell'invio all'archivio, in modo che diventino confrontabili (fino a quando tutte le relative proprietà sono confrontabili).</span><span class="sxs-lookup"><span data-stu-id="ea086-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="ea086-205">Vedere anche <sup>4.</sup></span><span class="sxs-lookup"><span data-stu-id="ea086-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="ea086-206"><sup>3</sup>runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza ricorrere al provider o all'archivio.</span><span class="sxs-lookup"><span data-stu-id="ea086-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="ea086-207"><sup>4</sup>viene effettuato un tentativo di confrontare tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="ea086-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="ea086-208">Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.</span><span class="sxs-lookup"><span data-stu-id="ea086-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="ea086-209"><sup>5</sup>vengono confrontati tutti i singoli elementi dei riferimenti (che include il nome del set di entità e tutte le proprietà chiave del tipo di entità).</span><span class="sxs-lookup"><span data-stu-id="ea086-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea086-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea086-210">See Also</span></span>  
 [<span data-ttu-id="ea086-211">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ea086-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
