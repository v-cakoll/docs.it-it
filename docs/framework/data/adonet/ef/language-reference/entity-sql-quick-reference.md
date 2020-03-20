---
title: Riferimento rapido a Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: fc7cf8f8f692f9dc4230569d5f575b6d5fad19fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150350"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="52a95-102">Riferimento rapido a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="52a95-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="52a95-103">In questo argomento viene fornita una guida di riferimento rapido alle query [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52a95-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="52a95-104">Le query incluse in questo argomento sono basate sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="52a95-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="52a95-105">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="52a95-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="52a95-106">string</span><span class="sxs-lookup"><span data-stu-id="52a95-106">String</span></span>  
 <span data-ttu-id="52a95-107">I valori letterali carattere di tipo String possono essere Unicode e non Unicode.</span><span class="sxs-lookup"><span data-stu-id="52a95-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="52a95-108">Le stringhe Unicode vengono precedute da N. Ad esempio, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="52a95-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="52a95-109">Di seguito è illustrato un esempio di valore letterale stringa Non-Unicode:</span><span class="sxs-lookup"><span data-stu-id="52a95-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="52a95-110">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-110">Output:</span></span>  
  
|<span data-ttu-id="52a95-111">valore</span><span class="sxs-lookup"><span data-stu-id="52a95-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52a95-112">hello</span><span class="sxs-lookup"><span data-stu-id="52a95-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="52a95-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="52a95-113">DateTime</span></span>  
 <span data-ttu-id="52a95-114">Nei valori letterali di tipo DateTime sono obbligatorie sia la parte relativa alla data che quella relativa all'ora.</span><span class="sxs-lookup"><span data-stu-id="52a95-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="52a95-115">Non sono previsti valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="52a95-115">There are no default values.</span></span>  
  
 <span data-ttu-id="52a95-116">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="52a95-117">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-117">Output:</span></span>  
  
|<span data-ttu-id="52a95-118">valore</span><span class="sxs-lookup"><span data-stu-id="52a95-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52a95-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="52a95-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="52a95-120">Integer</span><span class="sxs-lookup"><span data-stu-id="52a95-120">Integer</span></span>  
 <span data-ttu-id="52a95-121">I valori letterali Integer possono essere di tipo Int32 (123), UInt32 (123U), Int64 (123L) e UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="52a95-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="52a95-122">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="52a95-123">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-123">Output:</span></span>  
  
|<span data-ttu-id="52a95-124">valore</span><span class="sxs-lookup"><span data-stu-id="52a95-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52a95-125">1</span><span class="sxs-lookup"><span data-stu-id="52a95-125">1</span></span>|  
|<span data-ttu-id="52a95-126">2</span><span class="sxs-lookup"><span data-stu-id="52a95-126">2</span></span>|  
|<span data-ttu-id="52a95-127">3</span><span class="sxs-lookup"><span data-stu-id="52a95-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="52a95-128">Altri</span><span class="sxs-lookup"><span data-stu-id="52a95-128">Other</span></span>  
 <span data-ttu-id="52a95-129">Gli altri valori letterali supportati da [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono Guid, Binary, Float/Double, Decimal e `null`.</span><span class="sxs-lookup"><span data-stu-id="52a95-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="52a95-130">I valori letterali Null in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono considerati compatibili con tutti i tipi ne modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="52a95-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="52a95-131">Costruttori di tipo</span><span class="sxs-lookup"><span data-stu-id="52a95-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="52a95-132">ROW</span><span class="sxs-lookup"><span data-stu-id="52a95-132">ROW</span></span>  
 <span data-ttu-id="52a95-133">[ROW](row-entity-sql.md) costruisce un valore (record) anonimo, strutturalmente tipizzato come in:`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="52a95-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="52a95-134">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="52a95-135">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-135">Output:</span></span>  
  
|<span data-ttu-id="52a95-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="52a95-136">ProductID</span></span>|<span data-ttu-id="52a95-137">Nome</span><span class="sxs-lookup"><span data-stu-id="52a95-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="52a95-138">1</span><span class="sxs-lookup"><span data-stu-id="52a95-138">1</span></span>|<span data-ttu-id="52a95-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52a95-139">Adjustable Race</span></span>|  
|<span data-ttu-id="52a95-140">879</span><span class="sxs-lookup"><span data-stu-id="52a95-140">879</span></span>|<span data-ttu-id="52a95-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52a95-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="52a95-142">712</span><span class="sxs-lookup"><span data-stu-id="52a95-142">712</span></span>|<span data-ttu-id="52a95-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52a95-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="52a95-144">...</span><span class="sxs-lookup"><span data-stu-id="52a95-144">...</span></span>|<span data-ttu-id="52a95-145">...</span><span class="sxs-lookup"><span data-stu-id="52a95-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="52a95-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="52a95-146">MULTISET</span></span>  
 <span data-ttu-id="52a95-147">[MULTISET](multiset-entity-sql.md) costruisce raccolte, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="52a95-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="52a95-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="52a95-149">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="52a95-150">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-150">Output:</span></span>  
  
|<span data-ttu-id="52a95-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="52a95-151">ProductID</span></span>|<span data-ttu-id="52a95-152">Nome</span><span class="sxs-lookup"><span data-stu-id="52a95-152">Name</span></span>|<span data-ttu-id="52a95-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="52a95-153">ProductNumber</span></span>|<span data-ttu-id="52a95-154">…</span><span class="sxs-lookup"><span data-stu-id="52a95-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="52a95-155">842</span><span class="sxs-lookup"><span data-stu-id="52a95-155">842</span></span>|<span data-ttu-id="52a95-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="52a95-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="52a95-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="52a95-157">PA-T100</span></span>|<span data-ttu-id="52a95-158">…</span><span class="sxs-lookup"><span data-stu-id="52a95-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="52a95-159">Oggetto</span><span class="sxs-lookup"><span data-stu-id="52a95-159">Object</span></span>  
 <span data-ttu-id="52a95-160">[Costrutti di costruttore](named-type-constructor-entity-sql.md) di tipi denominati `person("abc", 12)`(denominati) oggetti definiti dall'utente, ad esempio .</span><span class="sxs-lookup"><span data-stu-id="52a95-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="52a95-161">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="52a95-162">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-162">Output:</span></span>  
  
|<span data-ttu-id="52a95-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="52a95-163">SalesOrderDetailID</span></span>|<span data-ttu-id="52a95-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="52a95-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="52a95-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="52a95-165">OrderQty</span></span>|<span data-ttu-id="52a95-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="52a95-166">ProductID</span></span>|<span data-ttu-id="52a95-167">...</span><span class="sxs-lookup"><span data-stu-id="52a95-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="52a95-168">1</span><span class="sxs-lookup"><span data-stu-id="52a95-168">1</span></span>|<span data-ttu-id="52a95-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="52a95-169">4911-403C-98</span></span>|<span data-ttu-id="52a95-170">1</span><span class="sxs-lookup"><span data-stu-id="52a95-170">1</span></span>|<span data-ttu-id="52a95-171">776</span><span class="sxs-lookup"><span data-stu-id="52a95-171">776</span></span>|<span data-ttu-id="52a95-172">...</span><span class="sxs-lookup"><span data-stu-id="52a95-172">...</span></span>|  
|<span data-ttu-id="52a95-173">2</span><span class="sxs-lookup"><span data-stu-id="52a95-173">2</span></span>|<span data-ttu-id="52a95-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="52a95-174">4911-403C-98</span></span>|<span data-ttu-id="52a95-175">3</span><span class="sxs-lookup"><span data-stu-id="52a95-175">3</span></span>|<span data-ttu-id="52a95-176">777</span><span class="sxs-lookup"><span data-stu-id="52a95-176">777</span></span>|<span data-ttu-id="52a95-177">...</span><span class="sxs-lookup"><span data-stu-id="52a95-177">...</span></span>|  
|<span data-ttu-id="52a95-178">...</span><span class="sxs-lookup"><span data-stu-id="52a95-178">...</span></span>|<span data-ttu-id="52a95-179">...</span><span class="sxs-lookup"><span data-stu-id="52a95-179">...</span></span>|<span data-ttu-id="52a95-180">...</span><span class="sxs-lookup"><span data-stu-id="52a95-180">...</span></span>|<span data-ttu-id="52a95-181">...</span><span class="sxs-lookup"><span data-stu-id="52a95-181">...</span></span>|<span data-ttu-id="52a95-182">...</span><span class="sxs-lookup"><span data-stu-id="52a95-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="52a95-183">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="52a95-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="52a95-184">REF</span><span class="sxs-lookup"><span data-stu-id="52a95-184">REF</span></span>  
 <span data-ttu-id="52a95-185">[REF](ref-entity-sql.md) crea un riferimento a un'istanza del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="52a95-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="52a95-186">La query seguente restituisce ad esempio i riferimenti a ogni entità Order nel set di entità Orders:</span><span class="sxs-lookup"><span data-stu-id="52a95-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="52a95-187">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-187">Output:</span></span>  
  
|<span data-ttu-id="52a95-188">valore</span><span class="sxs-lookup"><span data-stu-id="52a95-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52a95-189">1</span><span class="sxs-lookup"><span data-stu-id="52a95-189">1</span></span>|  
|<span data-ttu-id="52a95-190">2</span><span class="sxs-lookup"><span data-stu-id="52a95-190">2</span></span>|  
|<span data-ttu-id="52a95-191">3</span><span class="sxs-lookup"><span data-stu-id="52a95-191">3</span></span>|  
|<span data-ttu-id="52a95-192">...</span><span class="sxs-lookup"><span data-stu-id="52a95-192">...</span></span>|  
  
 <span data-ttu-id="52a95-193">Nell'esempio seguente viene usato l'operatore di estrazione delle proprietà (.) per accedere a una proprietà di un'entità.</span><span class="sxs-lookup"><span data-stu-id="52a95-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="52a95-194">Quando viene usato l'operatore di estrazione delle proprietà, il riferimento viene automaticamente dereferenziato.</span><span class="sxs-lookup"><span data-stu-id="52a95-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="52a95-195">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="52a95-196">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-196">Output:</span></span>  
  
|<span data-ttu-id="52a95-197">valore</span><span class="sxs-lookup"><span data-stu-id="52a95-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52a95-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52a95-198">Adjustable Race</span></span>|  
|<span data-ttu-id="52a95-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52a95-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="52a95-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52a95-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="52a95-201">...</span><span class="sxs-lookup"><span data-stu-id="52a95-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="52a95-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="52a95-202">DEREF</span></span>  
 <span data-ttu-id="52a95-203">[DEREF](deref-entity-sql.md) dereferenzia un valore di riferimento e produce il risultato di tale dereferenziazione.</span><span class="sxs-lookup"><span data-stu-id="52a95-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="52a95-204">La query seguente restituisce ad esempio le entità Order per ogni oggetto Order nel set di entità Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="52a95-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="52a95-205">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="52a95-206">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-206">Output:</span></span>  
  
|<span data-ttu-id="52a95-207">valore</span><span class="sxs-lookup"><span data-stu-id="52a95-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52a95-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52a95-208">Adjustable Race</span></span>|  
|<span data-ttu-id="52a95-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52a95-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="52a95-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52a95-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="52a95-211">...</span><span class="sxs-lookup"><span data-stu-id="52a95-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="52a95-212">CREATEREF e KEY</span><span class="sxs-lookup"><span data-stu-id="52a95-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="52a95-213">[CREATEREF](createref-entity-sql.md) crea un riferimento passando una chiave.</span><span class="sxs-lookup"><span data-stu-id="52a95-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="52a95-214">[KEY](key-entity-sql.md) estrae la parte chiave di un'espressione con riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="52a95-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="52a95-215">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="52a95-216">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-216">Output:</span></span>  
  
|<span data-ttu-id="52a95-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="52a95-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="52a95-218">980</span><span class="sxs-lookup"><span data-stu-id="52a95-218">980</span></span>|  
|<span data-ttu-id="52a95-219">365</span><span class="sxs-lookup"><span data-stu-id="52a95-219">365</span></span>|  
|<span data-ttu-id="52a95-220">771</span><span class="sxs-lookup"><span data-stu-id="52a95-220">771</span></span>|  
|<span data-ttu-id="52a95-221">...</span><span class="sxs-lookup"><span data-stu-id="52a95-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="52a95-222">Funzioni</span><span class="sxs-lookup"><span data-stu-id="52a95-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="52a95-223">Canonical</span><span class="sxs-lookup"><span data-stu-id="52a95-223">Canonical</span></span>  
 <span data-ttu-id="52a95-224">Lo spazio dei nomi per le `Edm.Length("string")` [funzioni canoniche](canonical-functions.md) è Edm, come in .</span><span class="sxs-lookup"><span data-stu-id="52a95-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="52a95-225">Non è necessario specificare lo spazio dei nomi a meno che non venga importato un altro spazio dei nomi contenente una funzione con lo stesso nome della funzione canonica.</span><span class="sxs-lookup"><span data-stu-id="52a95-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="52a95-226">Se due spazi dei nomi includono la stessa funzione, l'utente deve specificare il nome completo.</span><span class="sxs-lookup"><span data-stu-id="52a95-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="52a95-227">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="52a95-228">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-228">Output:</span></span>  
  
|<span data-ttu-id="52a95-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="52a95-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="52a95-230">6</span><span class="sxs-lookup"><span data-stu-id="52a95-230">6</span></span>|  
|<span data-ttu-id="52a95-231">6</span><span class="sxs-lookup"><span data-stu-id="52a95-231">6</span></span>|  
|<span data-ttu-id="52a95-232">5</span><span class="sxs-lookup"><span data-stu-id="52a95-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="52a95-233">Specifiche del provider Microsoft</span><span class="sxs-lookup"><span data-stu-id="52a95-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="52a95-234">[Le funzioni specifiche](../sqlclient-for-ef-functions.md) del `SqlServer` provider Microsoft si trovano nello spazio dei nomi .</span><span class="sxs-lookup"><span data-stu-id="52a95-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="52a95-235">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="52a95-236">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-236">Output:</span></span>  
  
|<span data-ttu-id="52a95-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="52a95-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="52a95-238">27</span><span class="sxs-lookup"><span data-stu-id="52a95-238">27</span></span>|  
|<span data-ttu-id="52a95-239">27</span><span class="sxs-lookup"><span data-stu-id="52a95-239">27</span></span>|  
|<span data-ttu-id="52a95-240">26</span><span class="sxs-lookup"><span data-stu-id="52a95-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="52a95-241">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="52a95-241">Namespaces</span></span>  
 <span data-ttu-id="52a95-242">[USING](using-entity-sql.md) specifica gli spazi dei nomi utilizzati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="52a95-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="52a95-243">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="52a95-244">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-244">Output:</span></span>  
  
|<span data-ttu-id="52a95-245">valore</span><span class="sxs-lookup"><span data-stu-id="52a95-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52a95-246">aa</span><span class="sxs-lookup"><span data-stu-id="52a95-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="52a95-247">Paging</span><span class="sxs-lookup"><span data-stu-id="52a95-247">Paging</span></span>  
 <span data-ttu-id="52a95-248">Il paging può essere espresso dichiarando una sottoclausola [SKIP](skip-entity-sql.md) e [LIMIT](limit-entity-sql.md) alla clausola [ORDER BY.](order-by-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="52a95-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="52a95-249">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="52a95-250">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-250">Output:</span></span>  
  
|<span data-ttu-id="52a95-251">ID</span><span class="sxs-lookup"><span data-stu-id="52a95-251">ID</span></span>|<span data-ttu-id="52a95-252">Nome</span><span class="sxs-lookup"><span data-stu-id="52a95-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="52a95-253">10</span><span class="sxs-lookup"><span data-stu-id="52a95-253">10</span></span>|<span data-ttu-id="52a95-254">Adina</span><span class="sxs-lookup"><span data-stu-id="52a95-254">Adina</span></span>|  
|<span data-ttu-id="52a95-255">11</span><span class="sxs-lookup"><span data-stu-id="52a95-255">11</span></span>|<span data-ttu-id="52a95-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="52a95-256">Agcaoili</span></span>|  
|<span data-ttu-id="52a95-257">12</span><span class="sxs-lookup"><span data-stu-id="52a95-257">12</span></span>|<span data-ttu-id="52a95-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="52a95-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="52a95-259">Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="52a95-259">Grouping</span></span>  
 <span data-ttu-id="52a95-260">[GROUPING BY](group-by-entity-sql.md) specifica i gruppi in cui devono essere inseriti gli oggetti restituiti da un'espressione di query ([SELECT](select-entity-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="52a95-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="52a95-261">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="52a95-262">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-262">Output:</span></span>  
  
|<span data-ttu-id="52a95-263">name</span><span class="sxs-lookup"><span data-stu-id="52a95-263">name</span></span>|  
|----------|  
|<span data-ttu-id="52a95-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="52a95-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="52a95-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="52a95-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="52a95-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="52a95-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="52a95-267">...</span><span class="sxs-lookup"><span data-stu-id="52a95-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="52a95-268">Navigazione</span><span class="sxs-lookup"><span data-stu-id="52a95-268">Navigation</span></span>  
 <span data-ttu-id="52a95-269">L' operatore di navigazione delle relazioni consente di eseguire la navigazione in una relazione da un'entità (entità finale di origine) a un'altra (entità finale di destinazione).</span><span class="sxs-lookup"><span data-stu-id="52a95-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="52a95-270">[NAVIGATE](navigate-entity-sql.md) accetta il tipo \<di relazione qualificato come> dello spazio dei nomi. \<> del nome del tipo di relazione.</span><span class="sxs-lookup"><span data-stu-id="52a95-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="52a95-271">Navigate restituisce Ref\<T> se la cardinalità della fine alla fine è 1.</span><span class="sxs-lookup"><span data-stu-id="52a95-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="52a95-272">Se la cardinalità della fine di fine\<è n, verrà restituita la raccolta<>> Ref T.</span><span class="sxs-lookup"><span data-stu-id="52a95-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="52a95-273">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="52a95-274">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-274">Output:</span></span>  
  
|<span data-ttu-id="52a95-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="52a95-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="52a95-276">1</span><span class="sxs-lookup"><span data-stu-id="52a95-276">1</span></span>|  
|<span data-ttu-id="52a95-277">2</span><span class="sxs-lookup"><span data-stu-id="52a95-277">2</span></span>|  
|<span data-ttu-id="52a95-278">3</span><span class="sxs-lookup"><span data-stu-id="52a95-278">3</span></span>|  
|<span data-ttu-id="52a95-279">...</span><span class="sxs-lookup"><span data-stu-id="52a95-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="52a95-280">SELECT VALUE e SELECT</span><span class="sxs-lookup"><span data-stu-id="52a95-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="52a95-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="52a95-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="52a95-282">fornisce la clausola SELECT VALUE per consentire di ignorare la costruzione di riga implicita.</span><span class="sxs-lookup"><span data-stu-id="52a95-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="52a95-283">In una clausola SELECT VALUE può essere specificato un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="52a95-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="52a95-284">Quando viene utilizzata una clausola di questo tipo, non viene costruito alcun wrapper di riga intorno `SELECT VALUE a`agli elementi nella clausola SELECT ed è possibile produrre una raccolta della forma desiderata, ad esempio: .</span><span class="sxs-lookup"><span data-stu-id="52a95-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="52a95-285">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="52a95-286">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-286">Output:</span></span>  
  
|<span data-ttu-id="52a95-287">Nome</span><span class="sxs-lookup"><span data-stu-id="52a95-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="52a95-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52a95-288">Adjustable Race</span></span>|  
|<span data-ttu-id="52a95-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52a95-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="52a95-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52a95-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="52a95-291">...</span><span class="sxs-lookup"><span data-stu-id="52a95-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="52a95-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="52a95-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="52a95-293">fornisce inoltre il costruttore ROW per la costruzione di righe arbitrarie.</span><span class="sxs-lookup"><span data-stu-id="52a95-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="52a95-294">SELECT accetta uno o più elementi nella proiezione e restituisce un record di dati con campi, ad esempio `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="52a95-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="52a95-295">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-295">Example:</span></span>  
  
 <span data-ttu-id="52a95-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="52a95-297">Nome</span><span class="sxs-lookup"><span data-stu-id="52a95-297">Name</span></span>|<span data-ttu-id="52a95-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="52a95-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="52a95-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="52a95-299">Adjustable Race</span></span>|<span data-ttu-id="52a95-300">1</span><span class="sxs-lookup"><span data-stu-id="52a95-300">1</span></span>|  
|<span data-ttu-id="52a95-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="52a95-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="52a95-302">879</span><span class="sxs-lookup"><span data-stu-id="52a95-302">879</span></span>|  
|<span data-ttu-id="52a95-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="52a95-303">AWC Logo Cap</span></span>|<span data-ttu-id="52a95-304">712</span><span class="sxs-lookup"><span data-stu-id="52a95-304">712</span></span>|  
|<span data-ttu-id="52a95-305">...</span><span class="sxs-lookup"><span data-stu-id="52a95-305">...</span></span>|<span data-ttu-id="52a95-306">...</span><span class="sxs-lookup"><span data-stu-id="52a95-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="52a95-307">Espressione CASE</span><span class="sxs-lookup"><span data-stu-id="52a95-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="52a95-308">[L'espressione case](case-entity-sql.md) valuta un set di espressioni booleane per determinare il risultato.</span><span class="sxs-lookup"><span data-stu-id="52a95-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="52a95-309">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52a95-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="52a95-310">Output:</span><span class="sxs-lookup"><span data-stu-id="52a95-310">Output:</span></span>  
  
|<span data-ttu-id="52a95-311">valore</span><span class="sxs-lookup"><span data-stu-id="52a95-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="52a95-312">TRUE</span><span class="sxs-lookup"><span data-stu-id="52a95-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52a95-313">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52a95-313">See also</span></span>

- [<span data-ttu-id="52a95-314">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="52a95-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="52a95-315">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="52a95-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
