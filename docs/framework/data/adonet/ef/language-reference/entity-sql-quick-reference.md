---
title: Riferimento rapido a Entity SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 81fd76d09f9cc02e89ac34d5f8fa74bd7f9d92f9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="fedbc-102">Riferimento rapido a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fedbc-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="fedbc-103">In questo argomento viene fornita una guida di riferimento rapido alle query [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fedbc-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="fedbc-104">Le query in questo argomento sono basate sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="fedbc-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="fedbc-105">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="fedbc-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="fedbc-106">String</span><span class="sxs-lookup"><span data-stu-id="fedbc-106">String</span></span>  
 <span data-ttu-id="fedbc-107">I valori letterali carattere di tipo String possono essere Unicode e non Unicode.</span><span class="sxs-lookup"><span data-stu-id="fedbc-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="fedbc-108">Le stringhe Unicode vengano anteposta una n Ad esempio, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="fedbc-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="fedbc-109">Di seguito è illustrato un esempio di valore letterale stringa Non-Unicode:</span><span class="sxs-lookup"><span data-stu-id="fedbc-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="fedbc-110">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-110">Output:</span></span>  
  
|<span data-ttu-id="fedbc-111">Valore</span><span class="sxs-lookup"><span data-stu-id="fedbc-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="fedbc-112">hello</span><span class="sxs-lookup"><span data-stu-id="fedbc-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="fedbc-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="fedbc-113">DateTime</span></span>  
 <span data-ttu-id="fedbc-114">Nei valori letterali di tipo DateTime sono obbligatorie sia la parte relativa alla data che quella relativa all'ora.</span><span class="sxs-lookup"><span data-stu-id="fedbc-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="fedbc-115">Non sono previsti valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="fedbc-115">There are no default values.</span></span>  
  
 <span data-ttu-id="fedbc-116">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="fedbc-117">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-117">Output:</span></span>  
  
|<span data-ttu-id="fedbc-118">Valore</span><span class="sxs-lookup"><span data-stu-id="fedbc-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="fedbc-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="fedbc-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="fedbc-120">Integer</span><span class="sxs-lookup"><span data-stu-id="fedbc-120">Integer</span></span>  
 <span data-ttu-id="fedbc-121">I valori letterali Integer possono essere di tipo Int32 (123), UInt32 (123U), Int64 (123L) e UInt64 (123UL).</span><span class="sxs-lookup"><span data-stu-id="fedbc-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="fedbc-122">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="fedbc-123">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-123">Output:</span></span>  
  
|<span data-ttu-id="fedbc-124">Valore</span><span class="sxs-lookup"><span data-stu-id="fedbc-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="fedbc-125">1</span><span class="sxs-lookup"><span data-stu-id="fedbc-125">1</span></span>|  
|<span data-ttu-id="fedbc-126">2</span><span class="sxs-lookup"><span data-stu-id="fedbc-126">2</span></span>|  
|<span data-ttu-id="fedbc-127">3</span><span class="sxs-lookup"><span data-stu-id="fedbc-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="fedbc-128">Altro</span><span class="sxs-lookup"><span data-stu-id="fedbc-128">Other</span></span>  
 <span data-ttu-id="fedbc-129">Gli altri valori letterali supportati da [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono Guid, Binary, Float/Double, Decimal e `null`.</span><span class="sxs-lookup"><span data-stu-id="fedbc-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="fedbc-130">I valori letterali Null in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono considerati compatibili con tutti i tipi ne modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="fedbc-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="fedbc-131">Costruttori di tipo</span><span class="sxs-lookup"><span data-stu-id="fedbc-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="fedbc-132">ROW</span><span class="sxs-lookup"><span data-stu-id="fedbc-132">ROW</span></span>  
 <span data-ttu-id="fedbc-133">[RIGA](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) costruisce un anonimo strutturalmente tipizzati (record) valore come in:`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="fedbc-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="fedbc-134">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="fedbc-135">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-135">Output:</span></span>  
  
|<span data-ttu-id="fedbc-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="fedbc-136">ProductID</span></span>|<span data-ttu-id="fedbc-137">Nome</span><span class="sxs-lookup"><span data-stu-id="fedbc-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="fedbc-138">1</span><span class="sxs-lookup"><span data-stu-id="fedbc-138">1</span></span>|<span data-ttu-id="fedbc-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="fedbc-139">Adjustable Race</span></span>|  
|<span data-ttu-id="fedbc-140">879</span><span class="sxs-lookup"><span data-stu-id="fedbc-140">879</span></span>|<span data-ttu-id="fedbc-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="fedbc-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="fedbc-142">712</span><span class="sxs-lookup"><span data-stu-id="fedbc-142">712</span></span>|<span data-ttu-id="fedbc-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="fedbc-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="fedbc-144">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-144">...</span></span>|<span data-ttu-id="fedbc-145">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="fedbc-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="fedbc-146">MULTISET</span></span>  
 <span data-ttu-id="fedbc-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) costruisce raccolte, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="fedbc-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="fedbc-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="fedbc-149">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-149">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="fedbc-150">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-150">Output:</span></span>  
  
|<span data-ttu-id="fedbc-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="fedbc-151">ProductID</span></span>|<span data-ttu-id="fedbc-152">Nome</span><span class="sxs-lookup"><span data-stu-id="fedbc-152">Name</span></span>|<span data-ttu-id="fedbc-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="fedbc-153">ProductNumber</span></span>|<span data-ttu-id="fedbc-154">…</span><span class="sxs-lookup"><span data-stu-id="fedbc-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="fedbc-155">842</span><span class="sxs-lookup"><span data-stu-id="fedbc-155">842</span></span>|<span data-ttu-id="fedbc-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="fedbc-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="fedbc-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="fedbc-157">PA-T100</span></span>|<span data-ttu-id="fedbc-158">…</span><span class="sxs-lookup"><span data-stu-id="fedbc-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="fedbc-159">Object</span><span class="sxs-lookup"><span data-stu-id="fedbc-159">Object</span></span>  
 <span data-ttu-id="fedbc-160">[Costruttore di tipo denominato](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) costruisce oggetti (denominati) definito dall'utente, ad esempio `person("abc", 12)`.</span><span class="sxs-lookup"><span data-stu-id="fedbc-160">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="fedbc-161">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-161">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="fedbc-162">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-162">Output:</span></span>  
  
|<span data-ttu-id="fedbc-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="fedbc-163">SalesOrderDetailID</span></span>|<span data-ttu-id="fedbc-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="fedbc-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="fedbc-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="fedbc-165">OrderQty</span></span>|<span data-ttu-id="fedbc-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="fedbc-166">ProductID</span></span>|<span data-ttu-id="fedbc-167">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="fedbc-168">1</span><span class="sxs-lookup"><span data-stu-id="fedbc-168">1</span></span>|<span data-ttu-id="fedbc-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="fedbc-169">4911-403C-98</span></span>|<span data-ttu-id="fedbc-170">1</span><span class="sxs-lookup"><span data-stu-id="fedbc-170">1</span></span>|<span data-ttu-id="fedbc-171">776</span><span class="sxs-lookup"><span data-stu-id="fedbc-171">776</span></span>|<span data-ttu-id="fedbc-172">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-172">...</span></span>|  
|<span data-ttu-id="fedbc-173">2</span><span class="sxs-lookup"><span data-stu-id="fedbc-173">2</span></span>|<span data-ttu-id="fedbc-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="fedbc-174">4911-403C-98</span></span>|<span data-ttu-id="fedbc-175">3</span><span class="sxs-lookup"><span data-stu-id="fedbc-175">3</span></span>|<span data-ttu-id="fedbc-176">777</span><span class="sxs-lookup"><span data-stu-id="fedbc-176">777</span></span>|<span data-ttu-id="fedbc-177">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-177">...</span></span>|  
|<span data-ttu-id="fedbc-178">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-178">...</span></span>|<span data-ttu-id="fedbc-179">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-179">...</span></span>|<span data-ttu-id="fedbc-180">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-180">...</span></span>|<span data-ttu-id="fedbc-181">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-181">...</span></span>|<span data-ttu-id="fedbc-182">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="fedbc-183">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="fedbc-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="fedbc-184">REF</span><span class="sxs-lookup"><span data-stu-id="fedbc-184">REF</span></span>  
 <span data-ttu-id="fedbc-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) crea un riferimento a un'istanza del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="fedbc-185">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="fedbc-186">La query seguente restituisce ad esempio i riferimenti a ogni entità Order nel set di entità Orders:</span><span class="sxs-lookup"><span data-stu-id="fedbc-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="fedbc-187">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-187">Output:</span></span>  
  
|<span data-ttu-id="fedbc-188">Valore</span><span class="sxs-lookup"><span data-stu-id="fedbc-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="fedbc-189">1</span><span class="sxs-lookup"><span data-stu-id="fedbc-189">1</span></span>|  
|<span data-ttu-id="fedbc-190">2</span><span class="sxs-lookup"><span data-stu-id="fedbc-190">2</span></span>|  
|<span data-ttu-id="fedbc-191">3</span><span class="sxs-lookup"><span data-stu-id="fedbc-191">3</span></span>|  
|<span data-ttu-id="fedbc-192">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-192">...</span></span>|  
  
 <span data-ttu-id="fedbc-193">Nell'esempio seguente viene usato l'operatore di estrazione delle proprietà (.) per accedere a una proprietà di un'entità.</span><span class="sxs-lookup"><span data-stu-id="fedbc-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="fedbc-194">Quando viene usato l'operatore di estrazione delle proprietà, il riferimento viene automaticamente dereferenziato.</span><span class="sxs-lookup"><span data-stu-id="fedbc-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="fedbc-195">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-195">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="fedbc-196">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-196">Output:</span></span>  
  
|<span data-ttu-id="fedbc-197">Valore</span><span class="sxs-lookup"><span data-stu-id="fedbc-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="fedbc-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="fedbc-198">Adjustable Race</span></span>|  
|<span data-ttu-id="fedbc-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="fedbc-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="fedbc-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="fedbc-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="fedbc-201">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="fedbc-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="fedbc-202">DEREF</span></span>  
 <span data-ttu-id="fedbc-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="fedbc-203">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="fedbc-204">La query seguente restituisce ad esempio le entità Order per ogni oggetto Order nel set di entità Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.</span><span class="sxs-lookup"><span data-stu-id="fedbc-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="fedbc-205">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-205">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="fedbc-206">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-206">Output:</span></span>  
  
|<span data-ttu-id="fedbc-207">Valore</span><span class="sxs-lookup"><span data-stu-id="fedbc-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="fedbc-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="fedbc-208">Adjustable Race</span></span>|  
|<span data-ttu-id="fedbc-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="fedbc-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="fedbc-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="fedbc-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="fedbc-211">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="fedbc-212">CREATEREF e KEY</span><span class="sxs-lookup"><span data-stu-id="fedbc-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="fedbc-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) crea un riferimento passando una chiave.</span><span class="sxs-lookup"><span data-stu-id="fedbc-213">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="fedbc-214">[CHIAVE](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) estrae la parte di un'espressione con riferimento al tipo di chiave.</span><span class="sxs-lookup"><span data-stu-id="fedbc-214">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="fedbc-215">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-215">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="fedbc-216">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-216">Output:</span></span>  
  
|<span data-ttu-id="fedbc-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="fedbc-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="fedbc-218">980</span><span class="sxs-lookup"><span data-stu-id="fedbc-218">980</span></span>|  
|<span data-ttu-id="fedbc-219">365</span><span class="sxs-lookup"><span data-stu-id="fedbc-219">365</span></span>|  
|<span data-ttu-id="fedbc-220">771</span><span class="sxs-lookup"><span data-stu-id="fedbc-220">771</span></span>|  
|<span data-ttu-id="fedbc-221">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="fedbc-222">Funzioni</span><span class="sxs-lookup"><span data-stu-id="fedbc-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="fedbc-223">Canoniche</span><span class="sxs-lookup"><span data-stu-id="fedbc-223">Canonical</span></span>  
 <span data-ttu-id="fedbc-224">Lo spazio dei nomi per [funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) è Edm, come in `Edm.Length("string")`.</span><span class="sxs-lookup"><span data-stu-id="fedbc-224">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="fedbc-225">Non è necessario specificare lo spazio dei nomi a meno che non venga importato un altro spazio dei nomi contenente una funzione con lo stesso nome della funzione canonica.</span><span class="sxs-lookup"><span data-stu-id="fedbc-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="fedbc-226">Se due spazi dei nomi includono la stessa funzione, l'utente deve specificare il nome completo.</span><span class="sxs-lookup"><span data-stu-id="fedbc-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="fedbc-227">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-227">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="fedbc-228">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-228">Output:</span></span>  
  
|<span data-ttu-id="fedbc-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="fedbc-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="fedbc-230">6</span><span class="sxs-lookup"><span data-stu-id="fedbc-230">6</span></span>|  
|<span data-ttu-id="fedbc-231">6</span><span class="sxs-lookup"><span data-stu-id="fedbc-231">6</span></span>|  
|<span data-ttu-id="fedbc-232">5</span><span class="sxs-lookup"><span data-stu-id="fedbc-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="fedbc-233">Specifiche del provider Microsoft</span><span class="sxs-lookup"><span data-stu-id="fedbc-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="fedbc-234">[Funzioni specifiche del provider Microsoft](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) presenti il `SqlServer` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fedbc-234">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="fedbc-235">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-235">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="fedbc-236">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-236">Output:</span></span>  
  
|<span data-ttu-id="fedbc-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="fedbc-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="fedbc-238">27</span><span class="sxs-lookup"><span data-stu-id="fedbc-238">27</span></span>|  
|<span data-ttu-id="fedbc-239">27</span><span class="sxs-lookup"><span data-stu-id="fedbc-239">27</span></span>|  
|<span data-ttu-id="fedbc-240">26</span><span class="sxs-lookup"><span data-stu-id="fedbc-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="fedbc-241">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="fedbc-241">Namespaces</span></span>  
 <span data-ttu-id="fedbc-242">[UTILIZZANDO](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifica spazi dei nomi utilizzati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="fedbc-242">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="fedbc-243">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-243">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="fedbc-244">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-244">Output:</span></span>  
  
|<span data-ttu-id="fedbc-245">Valore</span><span class="sxs-lookup"><span data-stu-id="fedbc-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="fedbc-246">aa</span><span class="sxs-lookup"><span data-stu-id="fedbc-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="fedbc-247">Paging</span><span class="sxs-lookup"><span data-stu-id="fedbc-247">Paging</span></span>  
 <span data-ttu-id="fedbc-248">Paging può essere espresso dichiarando un [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) e [limite](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sottoclausole per il [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clausola.</span><span class="sxs-lookup"><span data-stu-id="fedbc-248">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="fedbc-249">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-249">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="fedbc-250">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-250">Output:</span></span>  
  
|<span data-ttu-id="fedbc-251">ID</span><span class="sxs-lookup"><span data-stu-id="fedbc-251">ID</span></span>|<span data-ttu-id="fedbc-252">Nome</span><span class="sxs-lookup"><span data-stu-id="fedbc-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="fedbc-253">10</span><span class="sxs-lookup"><span data-stu-id="fedbc-253">10</span></span>|<span data-ttu-id="fedbc-254">Adina</span><span class="sxs-lookup"><span data-stu-id="fedbc-254">Adina</span></span>|  
|<span data-ttu-id="fedbc-255">11</span><span class="sxs-lookup"><span data-stu-id="fedbc-255">11</span></span>|<span data-ttu-id="fedbc-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="fedbc-256">Agcaoili</span></span>|  
|<span data-ttu-id="fedbc-257">12</span><span class="sxs-lookup"><span data-stu-id="fedbc-257">12</span></span>|<span data-ttu-id="fedbc-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="fedbc-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="fedbc-259">Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="fedbc-259">Grouping</span></span>  
 <span data-ttu-id="fedbc-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifica i gruppi nei quali oggetti restituiti da una query ([selezionare](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) espressione devono essere inseriti.</span><span class="sxs-lookup"><span data-stu-id="fedbc-260">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="fedbc-261">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-261">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="fedbc-262">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-262">Output:</span></span>  
  
|<span data-ttu-id="fedbc-263">name</span><span class="sxs-lookup"><span data-stu-id="fedbc-263">name</span></span>|  
|----------|  
|<span data-ttu-id="fedbc-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="fedbc-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="fedbc-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="fedbc-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="fedbc-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="fedbc-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="fedbc-267">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="fedbc-268">Navigazione</span><span class="sxs-lookup"><span data-stu-id="fedbc-268">Navigation</span></span>  
 <span data-ttu-id="fedbc-269">L' operatore di navigazione delle relazioni consente di eseguire la navigazione in una relazione da un'entità (entità finale di origine) a un'altra (entità finale di destinazione).</span><span class="sxs-lookup"><span data-stu-id="fedbc-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="fedbc-270">[NAVIGA](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) accetta il tipo di relazione qualificato come \<dello spazio dei nomi >.\< Nome tipo relazione >.</span><span class="sxs-lookup"><span data-stu-id="fedbc-270">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="fedbc-271">Passare restituisce Ref\<T > Se la cardinalità dell'entità finale è 1.</span><span class="sxs-lookup"><span data-stu-id="fedbc-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="fedbc-272">Se la cardinalità dell'entità finale è n, la raccolta < Ref\<T >> verranno restituiti.</span><span class="sxs-lookup"><span data-stu-id="fedbc-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="fedbc-273">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-273">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="fedbc-274">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-274">Output:</span></span>  
  
|<span data-ttu-id="fedbc-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="fedbc-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="fedbc-276">1</span><span class="sxs-lookup"><span data-stu-id="fedbc-276">1</span></span>|  
|<span data-ttu-id="fedbc-277">2</span><span class="sxs-lookup"><span data-stu-id="fedbc-277">2</span></span>|  
|<span data-ttu-id="fedbc-278">3</span><span class="sxs-lookup"><span data-stu-id="fedbc-278">3</span></span>|  
|<span data-ttu-id="fedbc-279">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="fedbc-280">SELECT VALUE e SELECT</span><span class="sxs-lookup"><span data-stu-id="fedbc-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="fedbc-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="fedbc-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="fedbc-282"> fornisce la clausola SELECT VALUE per consentire di ignorare la costruzione di riga implicita.</span><span class="sxs-lookup"><span data-stu-id="fedbc-282"> provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="fedbc-283">In una clausola SELECT VALUE può essere specificato un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="fedbc-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="fedbc-284">Quando viene usata questa clausola, viene costruito alcun wrapper di riga intorno agli elementi nella clausola SELECT e una raccolta della forma desiderata può essere prodotta, ad esempio: `SELECT VALUE a`.</span><span class="sxs-lookup"><span data-stu-id="fedbc-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="fedbc-285">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-285">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="fedbc-286">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-286">Output:</span></span>  
  
|<span data-ttu-id="fedbc-287">Nome</span><span class="sxs-lookup"><span data-stu-id="fedbc-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="fedbc-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="fedbc-288">Adjustable Race</span></span>|  
|<span data-ttu-id="fedbc-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="fedbc-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="fedbc-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="fedbc-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="fedbc-291">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="fedbc-292">SELEZIONE</span><span class="sxs-lookup"><span data-stu-id="fedbc-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="fedbc-293"> fornisce inoltre il costruttore ROW per la costruzione di righe arbitrarie.</span><span class="sxs-lookup"><span data-stu-id="fedbc-293"> also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="fedbc-294">SELECT accetta uno o più elementi nella proiezione e restituisce un record di dati con campi, ad esempio `SELECT a, b, c`.</span><span class="sxs-lookup"><span data-stu-id="fedbc-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="fedbc-295">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-295">Example:</span></span>  
  
 <span data-ttu-id="fedbc-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="fedbc-297">Nome</span><span class="sxs-lookup"><span data-stu-id="fedbc-297">Name</span></span>|<span data-ttu-id="fedbc-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="fedbc-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="fedbc-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="fedbc-299">Adjustable Race</span></span>|<span data-ttu-id="fedbc-300">1</span><span class="sxs-lookup"><span data-stu-id="fedbc-300">1</span></span>|  
|<span data-ttu-id="fedbc-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="fedbc-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="fedbc-302">879</span><span class="sxs-lookup"><span data-stu-id="fedbc-302">879</span></span>|  
|<span data-ttu-id="fedbc-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="fedbc-303">AWC Logo Cap</span></span>|<span data-ttu-id="fedbc-304">712</span><span class="sxs-lookup"><span data-stu-id="fedbc-304">712</span></span>|  
|<span data-ttu-id="fedbc-305">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-305">...</span></span>|<span data-ttu-id="fedbc-306">...</span><span class="sxs-lookup"><span data-stu-id="fedbc-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="fedbc-307">Espressione CASE</span><span class="sxs-lookup"><span data-stu-id="fedbc-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="fedbc-308">Il [espressione case](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) valuta un set di espressioni booleane per determinare il risultato.</span><span class="sxs-lookup"><span data-stu-id="fedbc-308">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="fedbc-309">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fedbc-309">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="fedbc-310">Output:</span><span class="sxs-lookup"><span data-stu-id="fedbc-310">Output:</span></span>  
  
|<span data-ttu-id="fedbc-311">Valore</span><span class="sxs-lookup"><span data-stu-id="fedbc-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="fedbc-312">true</span><span class="sxs-lookup"><span data-stu-id="fedbc-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fedbc-313">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fedbc-313">See Also</span></span>  
 [<span data-ttu-id="fedbc-314">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fedbc-314">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="fedbc-315">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fedbc-315">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
