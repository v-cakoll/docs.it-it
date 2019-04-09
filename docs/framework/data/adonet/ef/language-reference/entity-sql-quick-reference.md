---
title: Riferimento rapido a Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207071"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="60d72-102">Riferimento rapido a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="60d72-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="60d72-103">In questo argomento viene fornita una guida di riferimento rapido alle query [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60d72-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="60d72-104">Le query in questo argomento sono basate sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="60d72-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="60d72-105">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="60d72-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="60d72-106">Stringa</span><span class="sxs-lookup"><span data-stu-id="60d72-106">String</span></span>  
 <span data-ttu-id="60d72-107">I valori letterali carattere di tipo String possono essere Unicode e non Unicode.</span><span class="sxs-lookup"><span data-stu-id="60d72-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="60d72-108">Le stringhe Unicode vengono anteposta una n Ad esempio, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="60d72-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="60d72-109">Di seguito è illustrato un esempio di valore letterale stringa Non-Unicode:</span><span class="sxs-lookup"><span data-stu-id="60d72-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="60d72-110">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-110">Output:</span></span>  
  
|<span data-ttu-id="60d72-111">Value</span><span class="sxs-lookup"><span data-stu-id="60d72-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="60d72-112">hello</span><span class="sxs-lookup"><span data-stu-id="60d72-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="60d72-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="60d72-113">DateTime</span></span>  
 <span data-ttu-id="60d72-114">Nei valori letterali di tipo DateTime sono obbligatorie sia la parte relativa alla data che quella relativa all'ora.</span><span class="sxs-lookup"><span data-stu-id="60d72-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="60d72-115">Non sono previsti valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="60d72-115">There are no default values.</span></span>  
  
 <span data-ttu-id="60d72-116">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="60d72-117">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-117">Output:</span></span>  
  
|<span data-ttu-id="60d72-118">Value</span><span class="sxs-lookup"><span data-stu-id="60d72-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="60d72-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="60d72-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="60d72-120">Integer</span><span class="sxs-lookup"><span data-stu-id="60d72-120">Integer</span></span>  
 <span data-ttu-id="60d72-121">I valori letterali Integer possono essere di tipo Int32 (123), UInt32 (123U), Int64 (123L) e UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="60d72-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="60d72-122">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="60d72-123">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-123">Output:</span></span>  
  
|<span data-ttu-id="60d72-124">Value</span><span class="sxs-lookup"><span data-stu-id="60d72-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="60d72-125">1</span><span class="sxs-lookup"><span data-stu-id="60d72-125">1</span></span>|  
|<span data-ttu-id="60d72-126">2</span><span class="sxs-lookup"><span data-stu-id="60d72-126">2</span></span>|  
|<span data-ttu-id="60d72-127">3</span><span class="sxs-lookup"><span data-stu-id="60d72-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="60d72-128">Altro</span><span class="sxs-lookup"><span data-stu-id="60d72-128">Other</span></span>  
 <span data-ttu-id="60d72-129">Gli altri valori letterali supportati da [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono Guid, Binary, Float/Double, Decimal e `null`.</span><span class="sxs-lookup"><span data-stu-id="60d72-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="60d72-130">I valori letterali Null in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono considerati compatibili con tutti i tipi ne modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="60d72-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="60d72-131">Costruttori di tipo</span><span class="sxs-lookup"><span data-stu-id="60d72-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="60d72-132">ROW</span><span class="sxs-lookup"><span data-stu-id="60d72-132">ROW</span></span>  
 <span data-ttu-id="60d72-133">[RIGA](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) costruisce un valore (record) strutturalmente tipizzato anonimo, come in:</span><span class="sxs-lookup"><span data-stu-id="60d72-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in:</span></span> `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 <span data-ttu-id="60d72-134">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="60d72-135">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-135">Output:</span></span>  
  
|<span data-ttu-id="60d72-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="60d72-136">ProductID</span></span>|<span data-ttu-id="60d72-137">Nome</span><span class="sxs-lookup"><span data-stu-id="60d72-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="60d72-138">1</span><span class="sxs-lookup"><span data-stu-id="60d72-138">1</span></span>|<span data-ttu-id="60d72-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="60d72-139">Adjustable Race</span></span>|  
|<span data-ttu-id="60d72-140">879</span><span class="sxs-lookup"><span data-stu-id="60d72-140">879</span></span>|<span data-ttu-id="60d72-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="60d72-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="60d72-142">712</span><span class="sxs-lookup"><span data-stu-id="60d72-142">712</span></span>|<span data-ttu-id="60d72-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="60d72-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="60d72-144">...</span><span class="sxs-lookup"><span data-stu-id="60d72-144">...</span></span>|<span data-ttu-id="60d72-145">...</span><span class="sxs-lookup"><span data-stu-id="60d72-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="60d72-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="60d72-146">MULTISET</span></span>  
 <span data-ttu-id="60d72-147">[Oggetto MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) consente di costruire raccolte, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 <span data-ttu-id="60d72-148">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-148">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="60d72-149">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-149">Output:</span></span>  
  
|<span data-ttu-id="60d72-150">ProductID</span><span class="sxs-lookup"><span data-stu-id="60d72-150">ProductID</span></span>|<span data-ttu-id="60d72-151">Nome</span><span class="sxs-lookup"><span data-stu-id="60d72-151">Name</span></span>|<span data-ttu-id="60d72-152">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="60d72-152">ProductNumber</span></span>|<span data-ttu-id="60d72-153">…</span><span class="sxs-lookup"><span data-stu-id="60d72-153">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="60d72-154">842</span><span class="sxs-lookup"><span data-stu-id="60d72-154">842</span></span>|<span data-ttu-id="60d72-155">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="60d72-155">Touring-Panniers, Large</span></span>|<span data-ttu-id="60d72-156">PA-T100</span><span class="sxs-lookup"><span data-stu-id="60d72-156">PA-T100</span></span>|<span data-ttu-id="60d72-157">…</span><span class="sxs-lookup"><span data-stu-id="60d72-157">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="60d72-158">Object</span><span class="sxs-lookup"><span data-stu-id="60d72-158">Object</span></span>  
 <span data-ttu-id="60d72-159">[Denominato costruttore di tipo](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) consente di costruire oggetti definiti dall'utente (denominati), ad esempio `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="60d72-159">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="60d72-160">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-160">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="60d72-161">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-161">Output:</span></span>  
  
|<span data-ttu-id="60d72-162">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="60d72-162">SalesOrderDetailID</span></span>|<span data-ttu-id="60d72-163">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="60d72-163">CarrierTrackingNumber</span></span>|<span data-ttu-id="60d72-164">OrderQty</span><span class="sxs-lookup"><span data-stu-id="60d72-164">OrderQty</span></span>|<span data-ttu-id="60d72-165">ProductID</span><span class="sxs-lookup"><span data-stu-id="60d72-165">ProductID</span></span>|<span data-ttu-id="60d72-166">...</span><span class="sxs-lookup"><span data-stu-id="60d72-166">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="60d72-167">1</span><span class="sxs-lookup"><span data-stu-id="60d72-167">1</span></span>|<span data-ttu-id="60d72-168">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="60d72-168">4911-403C-98</span></span>|<span data-ttu-id="60d72-169">1</span><span class="sxs-lookup"><span data-stu-id="60d72-169">1</span></span>|<span data-ttu-id="60d72-170">776</span><span class="sxs-lookup"><span data-stu-id="60d72-170">776</span></span>|<span data-ttu-id="60d72-171">...</span><span class="sxs-lookup"><span data-stu-id="60d72-171">...</span></span>|  
|<span data-ttu-id="60d72-172">2</span><span class="sxs-lookup"><span data-stu-id="60d72-172">2</span></span>|<span data-ttu-id="60d72-173">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="60d72-173">4911-403C-98</span></span>|<span data-ttu-id="60d72-174">3</span><span class="sxs-lookup"><span data-stu-id="60d72-174">3</span></span>|<span data-ttu-id="60d72-175">777</span><span class="sxs-lookup"><span data-stu-id="60d72-175">777</span></span>|<span data-ttu-id="60d72-176">...</span><span class="sxs-lookup"><span data-stu-id="60d72-176">...</span></span>|  
|<span data-ttu-id="60d72-177">...</span><span class="sxs-lookup"><span data-stu-id="60d72-177">...</span></span>|<span data-ttu-id="60d72-178">...</span><span class="sxs-lookup"><span data-stu-id="60d72-178">...</span></span>|<span data-ttu-id="60d72-179">...</span><span class="sxs-lookup"><span data-stu-id="60d72-179">...</span></span>|<span data-ttu-id="60d72-180">...</span><span class="sxs-lookup"><span data-stu-id="60d72-180">...</span></span>|<span data-ttu-id="60d72-181">...</span><span class="sxs-lookup"><span data-stu-id="60d72-181">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="60d72-182">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="60d72-182">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="60d72-183">REF</span><span class="sxs-lookup"><span data-stu-id="60d72-183">REF</span></span>  
 <span data-ttu-id="60d72-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) crea un riferimento a un'istanza del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="60d72-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="60d72-185">La query seguente restituisce ad esempio i riferimenti a ogni entità Order nel set di entità Orders:</span><span class="sxs-lookup"><span data-stu-id="60d72-185">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="60d72-186">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-186">Output:</span></span>  
  
|<span data-ttu-id="60d72-187">Value</span><span class="sxs-lookup"><span data-stu-id="60d72-187">Value</span></span>|  
|-----------|  
|<span data-ttu-id="60d72-188">1</span><span class="sxs-lookup"><span data-stu-id="60d72-188">1</span></span>|  
|<span data-ttu-id="60d72-189">2</span><span class="sxs-lookup"><span data-stu-id="60d72-189">2</span></span>|  
|<span data-ttu-id="60d72-190">3</span><span class="sxs-lookup"><span data-stu-id="60d72-190">3</span></span>|  
|<span data-ttu-id="60d72-191">...</span><span class="sxs-lookup"><span data-stu-id="60d72-191">...</span></span>|  
  
 <span data-ttu-id="60d72-192">Nell'esempio seguente viene usato l'operatore di estrazione delle proprietà (.) per accedere a una proprietà di un'entità.</span><span class="sxs-lookup"><span data-stu-id="60d72-192">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="60d72-193">Quando viene usato l'operatore di estrazione delle proprietà, il riferimento viene automaticamente dereferenziato.</span><span class="sxs-lookup"><span data-stu-id="60d72-193">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="60d72-194">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-194">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="60d72-195">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-195">Output:</span></span>  
  
|<span data-ttu-id="60d72-196">Value</span><span class="sxs-lookup"><span data-stu-id="60d72-196">Value</span></span>|  
|-----------|  
|<span data-ttu-id="60d72-197">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="60d72-197">Adjustable Race</span></span>|  
|<span data-ttu-id="60d72-198">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="60d72-198">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="60d72-199">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="60d72-199">AWC Logo Cap</span></span>|  
|<span data-ttu-id="60d72-200">...</span><span class="sxs-lookup"><span data-stu-id="60d72-200">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="60d72-201">DEREF</span><span class="sxs-lookup"><span data-stu-id="60d72-201">DEREF</span></span>  
 <span data-ttu-id="60d72-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="60d72-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="60d72-203">La query seguente restituisce ad esempio le entità Order per ogni oggetto Order nel set di entità Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="60d72-203">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="60d72-204">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-204">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="60d72-205">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-205">Output:</span></span>  
  
|<span data-ttu-id="60d72-206">Value</span><span class="sxs-lookup"><span data-stu-id="60d72-206">Value</span></span>|  
|-----------|  
|<span data-ttu-id="60d72-207">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="60d72-207">Adjustable Race</span></span>|  
|<span data-ttu-id="60d72-208">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="60d72-208">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="60d72-209">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="60d72-209">AWC Logo Cap</span></span>|  
|<span data-ttu-id="60d72-210">...</span><span class="sxs-lookup"><span data-stu-id="60d72-210">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="60d72-211">CREATEREF e KEY</span><span class="sxs-lookup"><span data-stu-id="60d72-211">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="60d72-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) crea un riferimento passando una chiave.</span><span class="sxs-lookup"><span data-stu-id="60d72-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="60d72-213">[CHIAVE](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) estrae la parte di un'espressione con riferimento al tipo di chiave.</span><span class="sxs-lookup"><span data-stu-id="60d72-213">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="60d72-214">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-214">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="60d72-215">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-215">Output:</span></span>  
  
|<span data-ttu-id="60d72-216">ProductID</span><span class="sxs-lookup"><span data-stu-id="60d72-216">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="60d72-217">980</span><span class="sxs-lookup"><span data-stu-id="60d72-217">980</span></span>|  
|<span data-ttu-id="60d72-218">365</span><span class="sxs-lookup"><span data-stu-id="60d72-218">365</span></span>|  
|<span data-ttu-id="60d72-219">771</span><span class="sxs-lookup"><span data-stu-id="60d72-219">771</span></span>|  
|<span data-ttu-id="60d72-220">...</span><span class="sxs-lookup"><span data-stu-id="60d72-220">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="60d72-221">Funzioni</span><span class="sxs-lookup"><span data-stu-id="60d72-221">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="60d72-222">Canoniche</span><span class="sxs-lookup"><span data-stu-id="60d72-222">Canonical</span></span>  
 <span data-ttu-id="60d72-223">Lo spazio dei nomi [funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) è Edm, come in `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="60d72-223">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="60d72-224">Non è necessario specificare lo spazio dei nomi a meno che non venga importato un altro spazio dei nomi contenente una funzione con lo stesso nome della funzione canonica.</span><span class="sxs-lookup"><span data-stu-id="60d72-224">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="60d72-225">Se due spazi dei nomi includono la stessa funzione, l'utente deve specificare il nome completo.</span><span class="sxs-lookup"><span data-stu-id="60d72-225">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="60d72-226">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-226">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="60d72-227">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-227">Output:</span></span>  
  
|<span data-ttu-id="60d72-228">NameLen</span><span class="sxs-lookup"><span data-stu-id="60d72-228">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="60d72-229">6</span><span class="sxs-lookup"><span data-stu-id="60d72-229">6</span></span>|  
|<span data-ttu-id="60d72-230">6</span><span class="sxs-lookup"><span data-stu-id="60d72-230">6</span></span>|  
|<span data-ttu-id="60d72-231">5</span><span class="sxs-lookup"><span data-stu-id="60d72-231">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="60d72-232">Specifiche del provider Microsoft</span><span class="sxs-lookup"><span data-stu-id="60d72-232">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="60d72-233">[Funzioni specifiche del provider di Microsoft](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) sono nel `SqlServer` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="60d72-233">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="60d72-234">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-234">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="60d72-235">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-235">Output:</span></span>  
  
|<span data-ttu-id="60d72-236">EmailLen</span><span class="sxs-lookup"><span data-stu-id="60d72-236">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="60d72-237">27</span><span class="sxs-lookup"><span data-stu-id="60d72-237">27</span></span>|  
|<span data-ttu-id="60d72-238">27</span><span class="sxs-lookup"><span data-stu-id="60d72-238">27</span></span>|  
|<span data-ttu-id="60d72-239">26</span><span class="sxs-lookup"><span data-stu-id="60d72-239">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="60d72-240">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="60d72-240">Namespaces</span></span>  
 <span data-ttu-id="60d72-241">[USANDO](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifica gli spazi dei nomi usati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="60d72-241">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="60d72-242">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-242">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="60d72-243">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-243">Output:</span></span>  
  
|<span data-ttu-id="60d72-244">Value</span><span class="sxs-lookup"><span data-stu-id="60d72-244">Value</span></span>|  
|-----------|  
|<span data-ttu-id="60d72-245">aa</span><span class="sxs-lookup"><span data-stu-id="60d72-245">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="60d72-246">Paging</span><span class="sxs-lookup"><span data-stu-id="60d72-246">Paging</span></span>  
 <span data-ttu-id="60d72-247">Il paging può essere espresso dichiarando una [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) e [limite](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sottoclausole per il [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clausola.</span><span class="sxs-lookup"><span data-stu-id="60d72-247">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="60d72-248">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-248">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="60d72-249">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-249">Output:</span></span>  
  
|<span data-ttu-id="60d72-250">Id</span><span class="sxs-lookup"><span data-stu-id="60d72-250">ID</span></span>|<span data-ttu-id="60d72-251">Nome</span><span class="sxs-lookup"><span data-stu-id="60d72-251">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="60d72-252">10</span><span class="sxs-lookup"><span data-stu-id="60d72-252">10</span></span>|<span data-ttu-id="60d72-253">Adina</span><span class="sxs-lookup"><span data-stu-id="60d72-253">Adina</span></span>|  
|<span data-ttu-id="60d72-254">11</span><span class="sxs-lookup"><span data-stu-id="60d72-254">11</span></span>|<span data-ttu-id="60d72-255">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="60d72-255">Agcaoili</span></span>|  
|<span data-ttu-id="60d72-256">12</span><span class="sxs-lookup"><span data-stu-id="60d72-256">12</span></span>|<span data-ttu-id="60d72-257">Aguilar</span><span class="sxs-lookup"><span data-stu-id="60d72-257">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="60d72-258">Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="60d72-258">Grouping</span></span>  
 <span data-ttu-id="60d72-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifica i gruppi nei quali gli oggetti restituiti da una query ([selezionare](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) espressione devono essere inseriti.</span><span class="sxs-lookup"><span data-stu-id="60d72-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="60d72-260">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-260">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="60d72-261">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-261">Output:</span></span>  
  
|<span data-ttu-id="60d72-262">name</span><span class="sxs-lookup"><span data-stu-id="60d72-262">name</span></span>|  
|----------|  
|<span data-ttu-id="60d72-263">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="60d72-263">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="60d72-264">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="60d72-264">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="60d72-265">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="60d72-265">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="60d72-266">...</span><span class="sxs-lookup"><span data-stu-id="60d72-266">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="60d72-267">Navigazione</span><span class="sxs-lookup"><span data-stu-id="60d72-267">Navigation</span></span>  
 <span data-ttu-id="60d72-268">L' operatore di navigazione delle relazioni consente di eseguire la navigazione in una relazione da un'entità (entità finale di origine) a un'altra (entità finale di destinazione).</span><span class="sxs-lookup"><span data-stu-id="60d72-268">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="60d72-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) accetta il tipo di relazione qualificato come \<dello spazio dei nomi >.\< Nome tipo relazione >.</span><span class="sxs-lookup"><span data-stu-id="60d72-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="60d72-270">Passare restituisce Ref\<T > Se la cardinalità dell'entità finale è 1.</span><span class="sxs-lookup"><span data-stu-id="60d72-270">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="60d72-271">Se la cardinalità dell'entità finale è n, la raccolta < Ref\<T >> verranno restituiti.</span><span class="sxs-lookup"><span data-stu-id="60d72-271">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="60d72-272">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-272">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="60d72-273">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-273">Output:</span></span>  
  
|<span data-ttu-id="60d72-274">AddressID</span><span class="sxs-lookup"><span data-stu-id="60d72-274">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="60d72-275">1</span><span class="sxs-lookup"><span data-stu-id="60d72-275">1</span></span>|  
|<span data-ttu-id="60d72-276">2</span><span class="sxs-lookup"><span data-stu-id="60d72-276">2</span></span>|  
|<span data-ttu-id="60d72-277">3</span><span class="sxs-lookup"><span data-stu-id="60d72-277">3</span></span>|  
|<span data-ttu-id="60d72-278">...</span><span class="sxs-lookup"><span data-stu-id="60d72-278">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="60d72-279">SELECT VALUE e SELECT</span><span class="sxs-lookup"><span data-stu-id="60d72-279">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="60d72-280">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="60d72-280">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60d72-281">fornisce la clausola SELECT VALUE per ignorare la costruzione di riga implicita.</span><span class="sxs-lookup"><span data-stu-id="60d72-281">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="60d72-282">In una clausola SELECT VALUE può essere specificato un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="60d72-282">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="60d72-283">Quando viene usata questa clausola, viene costruito alcun wrapper di riga intorno agli elementi nella clausola SELECT e una raccolta della forma desiderata può essere prodotta, ad esempio: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="60d72-283">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="60d72-284">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-284">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="60d72-285">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-285">Output:</span></span>  
  
|<span data-ttu-id="60d72-286">Nome</span><span class="sxs-lookup"><span data-stu-id="60d72-286">Name</span></span>|  
|----------|  
|<span data-ttu-id="60d72-287">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="60d72-287">Adjustable Race</span></span>|  
|<span data-ttu-id="60d72-288">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="60d72-288">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="60d72-289">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="60d72-289">AWC Logo Cap</span></span>|  
|<span data-ttu-id="60d72-290">...</span><span class="sxs-lookup"><span data-stu-id="60d72-290">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="60d72-291">SELEZIONE</span><span class="sxs-lookup"><span data-stu-id="60d72-291">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="60d72-292">fornisce inoltre il costruttore row per costruire righe arbitrarie.</span><span class="sxs-lookup"><span data-stu-id="60d72-292">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="60d72-293">SELECT accetta uno o più elementi nella proiezione e restituisce un record di dati con campi, ad esempio `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="60d72-293">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="60d72-294">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-294">Example:</span></span>  
  
 <span data-ttu-id="60d72-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="60d72-296">Nome</span><span class="sxs-lookup"><span data-stu-id="60d72-296">Name</span></span>|<span data-ttu-id="60d72-297">ProductID</span><span class="sxs-lookup"><span data-stu-id="60d72-297">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="60d72-298">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="60d72-298">Adjustable Race</span></span>|<span data-ttu-id="60d72-299">1</span><span class="sxs-lookup"><span data-stu-id="60d72-299">1</span></span>|  
|<span data-ttu-id="60d72-300">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="60d72-300">All-Purpose Bike Stand</span></span>|<span data-ttu-id="60d72-301">879</span><span class="sxs-lookup"><span data-stu-id="60d72-301">879</span></span>|  
|<span data-ttu-id="60d72-302">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="60d72-302">AWC Logo Cap</span></span>|<span data-ttu-id="60d72-303">712</span><span class="sxs-lookup"><span data-stu-id="60d72-303">712</span></span>|  
|<span data-ttu-id="60d72-304">...</span><span class="sxs-lookup"><span data-stu-id="60d72-304">...</span></span>|<span data-ttu-id="60d72-305">...</span><span class="sxs-lookup"><span data-stu-id="60d72-305">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="60d72-306">Espressione CASE</span><span class="sxs-lookup"><span data-stu-id="60d72-306">CASE EXPRESSION</span></span>  
 <span data-ttu-id="60d72-307">Il [espressione case](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) valuta un set di espressioni booleane per determinare il risultato.</span><span class="sxs-lookup"><span data-stu-id="60d72-307">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="60d72-308">Esempio:</span><span class="sxs-lookup"><span data-stu-id="60d72-308">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="60d72-309">Output:</span><span class="sxs-lookup"><span data-stu-id="60d72-309">Output:</span></span>  
  
|<span data-ttu-id="60d72-310">Value</span><span class="sxs-lookup"><span data-stu-id="60d72-310">Value</span></span>|  
|-----------|  
|<span data-ttu-id="60d72-311">TRUE</span><span class="sxs-lookup"><span data-stu-id="60d72-311">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60d72-312">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60d72-312">See also</span></span>

- [<span data-ttu-id="60d72-313">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="60d72-313">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="60d72-314">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="60d72-314">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
