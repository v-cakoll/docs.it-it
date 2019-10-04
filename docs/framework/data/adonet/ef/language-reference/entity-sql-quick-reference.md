---
title: Riferimento rapido a Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 9ccfc461d394af8804c960ebf460e7fbfb025b64
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833869"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="191c5-102">Riferimento rapido a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="191c5-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="191c5-103">In questo argomento viene fornita una guida di riferimento rapido alle query [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="191c5-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="191c5-104">Le query in questo argomento sono basate sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="191c5-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="191c5-105">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="191c5-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="191c5-106">Stringa</span><span class="sxs-lookup"><span data-stu-id="191c5-106">String</span></span>  
 <span data-ttu-id="191c5-107">I valori letterali carattere di tipo String possono essere Unicode e non Unicode.</span><span class="sxs-lookup"><span data-stu-id="191c5-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="191c5-108">Le stringhe Unicode vengono anteposti a N. Ad esempio, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="191c5-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="191c5-109">Di seguito è illustrato un esempio di valore letterale stringa Non-Unicode:</span><span class="sxs-lookup"><span data-stu-id="191c5-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="191c5-110">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-110">Output:</span></span>  
  
|<span data-ttu-id="191c5-111">Value</span><span class="sxs-lookup"><span data-stu-id="191c5-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="191c5-112">hello</span><span class="sxs-lookup"><span data-stu-id="191c5-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="191c5-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="191c5-113">DateTime</span></span>  
 <span data-ttu-id="191c5-114">Nei valori letterali di tipo DateTime sono obbligatorie sia la parte relativa alla data che quella relativa all'ora.</span><span class="sxs-lookup"><span data-stu-id="191c5-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="191c5-115">Non sono previsti valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="191c5-115">There are no default values.</span></span>  
  
 <span data-ttu-id="191c5-116">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="191c5-117">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-117">Output:</span></span>  
  
|<span data-ttu-id="191c5-118">Value</span><span class="sxs-lookup"><span data-stu-id="191c5-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="191c5-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="191c5-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="191c5-120">Integer</span><span class="sxs-lookup"><span data-stu-id="191c5-120">Integer</span></span>  
 <span data-ttu-id="191c5-121">I valori letterali Integer possono essere di tipo Int32 (123), UInt32 (123U), Int64 (123L) e UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="191c5-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="191c5-122">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="191c5-123">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-123">Output:</span></span>  
  
|<span data-ttu-id="191c5-124">Value</span><span class="sxs-lookup"><span data-stu-id="191c5-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="191c5-125">1</span><span class="sxs-lookup"><span data-stu-id="191c5-125">1</span></span>|  
|<span data-ttu-id="191c5-126">2</span><span class="sxs-lookup"><span data-stu-id="191c5-126">2</span></span>|  
|<span data-ttu-id="191c5-127">3</span><span class="sxs-lookup"><span data-stu-id="191c5-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="191c5-128">Altro</span><span class="sxs-lookup"><span data-stu-id="191c5-128">Other</span></span>  
 <span data-ttu-id="191c5-129">Gli altri valori letterali supportati da [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono Guid, Binary, Float/Double, Decimal e `null`.</span><span class="sxs-lookup"><span data-stu-id="191c5-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="191c5-130">I valori letterali Null in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono considerati compatibili con tutti i tipi ne modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="191c5-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="191c5-131">Costruttori di tipo</span><span class="sxs-lookup"><span data-stu-id="191c5-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="191c5-132">ROW</span><span class="sxs-lookup"><span data-stu-id="191c5-132">ROW</span></span>  
 <span data-ttu-id="191c5-133">[Row](row-entity-sql.md) costruisce un valore anonimo con tipizzazione strutturale (record) come in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="191c5-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="191c5-134">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="191c5-135">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-135">Output:</span></span>  
  
|<span data-ttu-id="191c5-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="191c5-136">ProductID</span></span>|<span data-ttu-id="191c5-137">nome</span><span class="sxs-lookup"><span data-stu-id="191c5-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="191c5-138">1</span><span class="sxs-lookup"><span data-stu-id="191c5-138">1</span></span>|<span data-ttu-id="191c5-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="191c5-139">Adjustable Race</span></span>|  
|<span data-ttu-id="191c5-140">879</span><span class="sxs-lookup"><span data-stu-id="191c5-140">879</span></span>|<span data-ttu-id="191c5-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="191c5-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="191c5-142">712</span><span class="sxs-lookup"><span data-stu-id="191c5-142">712</span></span>|<span data-ttu-id="191c5-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="191c5-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="191c5-144">...</span><span class="sxs-lookup"><span data-stu-id="191c5-144">...</span></span>|<span data-ttu-id="191c5-145">...</span><span class="sxs-lookup"><span data-stu-id="191c5-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="191c5-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="191c5-146">MULTISET</span></span>  
 <span data-ttu-id="191c5-147">[Multiset](multiset-entity-sql.md) costruisce raccolte, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="191c5-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="191c5-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="191c5-149">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="191c5-150">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-150">Output:</span></span>  
  
|<span data-ttu-id="191c5-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="191c5-151">ProductID</span></span>|<span data-ttu-id="191c5-152">nome</span><span class="sxs-lookup"><span data-stu-id="191c5-152">Name</span></span>|<span data-ttu-id="191c5-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="191c5-153">ProductNumber</span></span>|<span data-ttu-id="191c5-154">…</span><span class="sxs-lookup"><span data-stu-id="191c5-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="191c5-155">842</span><span class="sxs-lookup"><span data-stu-id="191c5-155">842</span></span>|<span data-ttu-id="191c5-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="191c5-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="191c5-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="191c5-157">PA-T100</span></span>|<span data-ttu-id="191c5-158">…</span><span class="sxs-lookup"><span data-stu-id="191c5-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="191c5-159">Object</span><span class="sxs-lookup"><span data-stu-id="191c5-159">Object</span></span>  
 <span data-ttu-id="191c5-160">Il [costruttore di tipo denominato](named-type-constructor-entity-sql.md) crea oggetti definiti dall'utente (denominati), ad esempio `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="191c5-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="191c5-161">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="191c5-162">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-162">Output:</span></span>  
  
|<span data-ttu-id="191c5-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="191c5-163">SalesOrderDetailID</span></span>|<span data-ttu-id="191c5-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="191c5-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="191c5-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="191c5-165">OrderQty</span></span>|<span data-ttu-id="191c5-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="191c5-166">ProductID</span></span>|<span data-ttu-id="191c5-167">...</span><span class="sxs-lookup"><span data-stu-id="191c5-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="191c5-168">1</span><span class="sxs-lookup"><span data-stu-id="191c5-168">1</span></span>|<span data-ttu-id="191c5-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="191c5-169">4911-403C-98</span></span>|<span data-ttu-id="191c5-170">1</span><span class="sxs-lookup"><span data-stu-id="191c5-170">1</span></span>|<span data-ttu-id="191c5-171">776</span><span class="sxs-lookup"><span data-stu-id="191c5-171">776</span></span>|<span data-ttu-id="191c5-172">...</span><span class="sxs-lookup"><span data-stu-id="191c5-172">...</span></span>|  
|<span data-ttu-id="191c5-173">2</span><span class="sxs-lookup"><span data-stu-id="191c5-173">2</span></span>|<span data-ttu-id="191c5-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="191c5-174">4911-403C-98</span></span>|<span data-ttu-id="191c5-175">3</span><span class="sxs-lookup"><span data-stu-id="191c5-175">3</span></span>|<span data-ttu-id="191c5-176">777</span><span class="sxs-lookup"><span data-stu-id="191c5-176">777</span></span>|<span data-ttu-id="191c5-177">...</span><span class="sxs-lookup"><span data-stu-id="191c5-177">...</span></span>|  
|<span data-ttu-id="191c5-178">...</span><span class="sxs-lookup"><span data-stu-id="191c5-178">...</span></span>|<span data-ttu-id="191c5-179">...</span><span class="sxs-lookup"><span data-stu-id="191c5-179">...</span></span>|<span data-ttu-id="191c5-180">...</span><span class="sxs-lookup"><span data-stu-id="191c5-180">...</span></span>|<span data-ttu-id="191c5-181">...</span><span class="sxs-lookup"><span data-stu-id="191c5-181">...</span></span>|<span data-ttu-id="191c5-182">...</span><span class="sxs-lookup"><span data-stu-id="191c5-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="191c5-183">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="191c5-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="191c5-184">REF</span><span class="sxs-lookup"><span data-stu-id="191c5-184">REF</span></span>  
 <span data-ttu-id="191c5-185">[Ref](ref-entity-sql.md) crea un riferimento a un'istanza del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="191c5-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="191c5-186">La query seguente restituisce ad esempio i riferimenti a ogni entità Order nel set di entità Orders:</span><span class="sxs-lookup"><span data-stu-id="191c5-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="191c5-187">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-187">Output:</span></span>  
  
|<span data-ttu-id="191c5-188">Value</span><span class="sxs-lookup"><span data-stu-id="191c5-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="191c5-189">1</span><span class="sxs-lookup"><span data-stu-id="191c5-189">1</span></span>|  
|<span data-ttu-id="191c5-190">2</span><span class="sxs-lookup"><span data-stu-id="191c5-190">2</span></span>|  
|<span data-ttu-id="191c5-191">3</span><span class="sxs-lookup"><span data-stu-id="191c5-191">3</span></span>|  
|<span data-ttu-id="191c5-192">...</span><span class="sxs-lookup"><span data-stu-id="191c5-192">...</span></span>|  
  
 <span data-ttu-id="191c5-193">Nell'esempio seguente viene usato l'operatore di estrazione delle proprietà (.) per accedere a una proprietà di un'entità.</span><span class="sxs-lookup"><span data-stu-id="191c5-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="191c5-194">Quando viene usato l'operatore di estrazione delle proprietà, il riferimento viene automaticamente dereferenziato.</span><span class="sxs-lookup"><span data-stu-id="191c5-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="191c5-195">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="191c5-196">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-196">Output:</span></span>  
  
|<span data-ttu-id="191c5-197">Value</span><span class="sxs-lookup"><span data-stu-id="191c5-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="191c5-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="191c5-198">Adjustable Race</span></span>|  
|<span data-ttu-id="191c5-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="191c5-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="191c5-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="191c5-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="191c5-201">...</span><span class="sxs-lookup"><span data-stu-id="191c5-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="191c5-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="191c5-202">DEREF</span></span>  
 <span data-ttu-id="191c5-203">[Deref](deref-entity-sql.md) consente di dereferenziare un valore di riferimento e produce il risultato di tale dereferenziazione.</span><span class="sxs-lookup"><span data-stu-id="191c5-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="191c5-204">La query seguente restituisce ad esempio le entità Order per ogni oggetto Order nel set di entità Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="191c5-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="191c5-205">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="191c5-206">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-206">Output:</span></span>  
  
|<span data-ttu-id="191c5-207">Value</span><span class="sxs-lookup"><span data-stu-id="191c5-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="191c5-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="191c5-208">Adjustable Race</span></span>|  
|<span data-ttu-id="191c5-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="191c5-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="191c5-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="191c5-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="191c5-211">...</span><span class="sxs-lookup"><span data-stu-id="191c5-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="191c5-212">CREATEREF e KEY</span><span class="sxs-lookup"><span data-stu-id="191c5-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="191c5-213">[CreateRef](createref-entity-sql.md) crea un riferimento passando una chiave.</span><span class="sxs-lookup"><span data-stu-id="191c5-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="191c5-214">[Key](key-entity-sql.md) estrae la parte relativa alla chiave di un'espressione con un riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="191c5-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="191c5-215">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="191c5-216">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-216">Output:</span></span>  
  
|<span data-ttu-id="191c5-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="191c5-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="191c5-218">980</span><span class="sxs-lookup"><span data-stu-id="191c5-218">980</span></span>|  
|<span data-ttu-id="191c5-219">365</span><span class="sxs-lookup"><span data-stu-id="191c5-219">365</span></span>|  
|<span data-ttu-id="191c5-220">771</span><span class="sxs-lookup"><span data-stu-id="191c5-220">771</span></span>|  
|<span data-ttu-id="191c5-221">...</span><span class="sxs-lookup"><span data-stu-id="191c5-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="191c5-222">Funzioni</span><span class="sxs-lookup"><span data-stu-id="191c5-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="191c5-223">Canoniche</span><span class="sxs-lookup"><span data-stu-id="191c5-223">Canonical</span></span>  
 <span data-ttu-id="191c5-224">Lo spazio dei nomi per le [funzioni canoniche](canonical-functions.md) è EDM, come in `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="191c5-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="191c5-225">Non è necessario specificare lo spazio dei nomi a meno che non venga importato un altro spazio dei nomi contenente una funzione con lo stesso nome della funzione canonica.</span><span class="sxs-lookup"><span data-stu-id="191c5-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="191c5-226">Se due spazi dei nomi includono la stessa funzione, l'utente deve specificare il nome completo.</span><span class="sxs-lookup"><span data-stu-id="191c5-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="191c5-227">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="191c5-228">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-228">Output:</span></span>  
  
|<span data-ttu-id="191c5-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="191c5-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="191c5-230">6</span><span class="sxs-lookup"><span data-stu-id="191c5-230">6</span></span>|  
|<span data-ttu-id="191c5-231">6</span><span class="sxs-lookup"><span data-stu-id="191c5-231">6</span></span>|  
|<span data-ttu-id="191c5-232">5</span><span class="sxs-lookup"><span data-stu-id="191c5-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="191c5-233">Specifiche del provider Microsoft</span><span class="sxs-lookup"><span data-stu-id="191c5-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="191c5-234">Le [funzioni specifiche del provider Microsoft](../sqlclient-for-ef-functions.md) si trovano nello spazio dei nomi `SqlServer`.</span><span class="sxs-lookup"><span data-stu-id="191c5-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="191c5-235">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="191c5-236">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-236">Output:</span></span>  
  
|<span data-ttu-id="191c5-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="191c5-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="191c5-238">27</span><span class="sxs-lookup"><span data-stu-id="191c5-238">27</span></span>|  
|<span data-ttu-id="191c5-239">27</span><span class="sxs-lookup"><span data-stu-id="191c5-239">27</span></span>|  
|<span data-ttu-id="191c5-240">26</span><span class="sxs-lookup"><span data-stu-id="191c5-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="191c5-241">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="191c5-241">Namespaces</span></span>  
 <span data-ttu-id="191c5-242">L' [utilizzo](using-entity-sql.md) di specifica gli spazi dei nomi utilizzati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="191c5-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="191c5-243">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="191c5-244">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-244">Output:</span></span>  
  
|<span data-ttu-id="191c5-245">Value</span><span class="sxs-lookup"><span data-stu-id="191c5-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="191c5-246">aa</span><span class="sxs-lookup"><span data-stu-id="191c5-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="191c5-247">Paging</span><span class="sxs-lookup"><span data-stu-id="191c5-247">Paging</span></span>  
 <span data-ttu-id="191c5-248">Il paging può essere espresso dichiarando una sottoclausole [Skip](skip-entity-sql.md) e [limit](limit-entity-sql.md) nella clausola [Order by](order-by-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="191c5-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="191c5-249">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="191c5-250">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-250">Output:</span></span>  
  
|<span data-ttu-id="191c5-251">id</span><span class="sxs-lookup"><span data-stu-id="191c5-251">ID</span></span>|<span data-ttu-id="191c5-252">nome</span><span class="sxs-lookup"><span data-stu-id="191c5-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="191c5-253">10</span><span class="sxs-lookup"><span data-stu-id="191c5-253">10</span></span>|<span data-ttu-id="191c5-254">Adina</span><span class="sxs-lookup"><span data-stu-id="191c5-254">Adina</span></span>|  
|<span data-ttu-id="191c5-255">11</span><span class="sxs-lookup"><span data-stu-id="191c5-255">11</span></span>|<span data-ttu-id="191c5-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="191c5-256">Agcaoili</span></span>|  
|<span data-ttu-id="191c5-257">12</span><span class="sxs-lookup"><span data-stu-id="191c5-257">12</span></span>|<span data-ttu-id="191c5-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="191c5-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="191c5-259">Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="191c5-259">Grouping</span></span>  
 <span data-ttu-id="191c5-260">Il [raggruppamento in base](group-by-entity-sql.md) a specifica i gruppi nei quali devono essere inseriti gli oggetti restituiti da un'espressione di query ([SELECT](select-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="191c5-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="191c5-261">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="191c5-262">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-262">Output:</span></span>  
  
|<span data-ttu-id="191c5-263">name</span><span class="sxs-lookup"><span data-stu-id="191c5-263">name</span></span>|  
|----------|  
|<span data-ttu-id="191c5-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="191c5-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="191c5-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="191c5-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="191c5-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="191c5-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="191c5-267">...</span><span class="sxs-lookup"><span data-stu-id="191c5-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="191c5-268">Navigazione</span><span class="sxs-lookup"><span data-stu-id="191c5-268">Navigation</span></span>  
 <span data-ttu-id="191c5-269">L' operatore di navigazione delle relazioni consente di eseguire la navigazione in una relazione da un'entità (entità finale di origine) a un'altra (entità finale di destinazione).</span><span class="sxs-lookup"><span data-stu-id="191c5-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="191c5-270">[Navigate](navigate-entity-sql.md) accetta il tipo di relazione qualificato come \<namespace >. @no__t-nome del tipo di 2relationship >.</span><span class="sxs-lookup"><span data-stu-id="191c5-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="191c5-271">Navigate restituisce Ref @ no__t-0T > Se la cardinalità dell'entità finale è 1.</span><span class="sxs-lookup"><span data-stu-id="191c5-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="191c5-272">Se la cardinalità dell'oggetto finale è n, viene restituita la raccolta < Ref @ no__t-0T > >.</span><span class="sxs-lookup"><span data-stu-id="191c5-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="191c5-273">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="191c5-274">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-274">Output:</span></span>  
  
|<span data-ttu-id="191c5-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="191c5-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="191c5-276">1</span><span class="sxs-lookup"><span data-stu-id="191c5-276">1</span></span>|  
|<span data-ttu-id="191c5-277">2</span><span class="sxs-lookup"><span data-stu-id="191c5-277">2</span></span>|  
|<span data-ttu-id="191c5-278">3</span><span class="sxs-lookup"><span data-stu-id="191c5-278">3</span></span>|  
|<span data-ttu-id="191c5-279">...</span><span class="sxs-lookup"><span data-stu-id="191c5-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="191c5-280">SELECT VALUE e SELECT</span><span class="sxs-lookup"><span data-stu-id="191c5-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="191c5-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="191c5-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="191c5-282">fornisce la clausola SELECT VALUE per consentire di ignorare la costruzione di riga implicita.</span><span class="sxs-lookup"><span data-stu-id="191c5-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="191c5-283">In una clausola SELECT VALUE può essere specificato un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="191c5-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="191c5-284">Quando si utilizza tale clausola, non viene costruito alcun wrapper di riga intorno agli elementi nella clausola SELECT ed è possibile produrre una raccolta della forma desiderata, ad esempio: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="191c5-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="191c5-285">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="191c5-286">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-286">Output:</span></span>  
  
|<span data-ttu-id="191c5-287">nome</span><span class="sxs-lookup"><span data-stu-id="191c5-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="191c5-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="191c5-288">Adjustable Race</span></span>|  
|<span data-ttu-id="191c5-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="191c5-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="191c5-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="191c5-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="191c5-291">...</span><span class="sxs-lookup"><span data-stu-id="191c5-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="191c5-292">SELEZIONE</span><span class="sxs-lookup"><span data-stu-id="191c5-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="191c5-293">fornisce inoltre il costruttore ROW per la costruzione di righe arbitrarie.</span><span class="sxs-lookup"><span data-stu-id="191c5-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="191c5-294">SELECT accetta uno o più elementi nella proiezione e restituisce un record di dati con campi, ad esempio `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="191c5-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="191c5-295">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-295">Example:</span></span>  
  
 <span data-ttu-id="191c5-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="191c5-297">nome</span><span class="sxs-lookup"><span data-stu-id="191c5-297">Name</span></span>|<span data-ttu-id="191c5-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="191c5-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="191c5-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="191c5-299">Adjustable Race</span></span>|<span data-ttu-id="191c5-300">1</span><span class="sxs-lookup"><span data-stu-id="191c5-300">1</span></span>|  
|<span data-ttu-id="191c5-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="191c5-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="191c5-302">879</span><span class="sxs-lookup"><span data-stu-id="191c5-302">879</span></span>|  
|<span data-ttu-id="191c5-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="191c5-303">AWC Logo Cap</span></span>|<span data-ttu-id="191c5-304">712</span><span class="sxs-lookup"><span data-stu-id="191c5-304">712</span></span>|  
|<span data-ttu-id="191c5-305">...</span><span class="sxs-lookup"><span data-stu-id="191c5-305">...</span></span>|<span data-ttu-id="191c5-306">...</span><span class="sxs-lookup"><span data-stu-id="191c5-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="191c5-307">Espressione CASE</span><span class="sxs-lookup"><span data-stu-id="191c5-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="191c5-308">L' [espressione case](case-entity-sql.md) valuta un set di espressioni booleane per determinare il risultato.</span><span class="sxs-lookup"><span data-stu-id="191c5-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="191c5-309">Esempio:</span><span class="sxs-lookup"><span data-stu-id="191c5-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="191c5-310">Output:</span><span class="sxs-lookup"><span data-stu-id="191c5-310">Output:</span></span>  
  
|<span data-ttu-id="191c5-311">Value</span><span class="sxs-lookup"><span data-stu-id="191c5-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="191c5-312">true</span><span class="sxs-lookup"><span data-stu-id="191c5-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="191c5-313">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="191c5-313">See also</span></span>

- [<span data-ttu-id="191c5-314">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="191c5-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="191c5-315">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="191c5-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
