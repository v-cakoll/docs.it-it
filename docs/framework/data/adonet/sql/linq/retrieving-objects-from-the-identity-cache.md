---
title: "Recupero di oggetti dalla cache di identità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e7677f2fcfe854aad5d01c0e024955da2480c375
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="retrieving-objects-from-the-identity-cache"></a><span data-ttu-id="0ffd7-102">Recupero di oggetti dalla cache di identità</span><span class="sxs-lookup"><span data-stu-id="0ffd7-102">Retrieving Objects from the Identity Cache</span></span>
<span data-ttu-id="0ffd7-103">In questo argomento vengono descritti i tipi di query LINQ to SQL che restituiscono un oggetto dalla cache delle identità gestita dall'oggetto <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-103">This topic describes the types of LINQ to SQL queries that return an object from the identity cache that is managed by the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="0ffd7-104">In LINQ to SQL, uno dei modi in cui l'oggetto <xref:System.Data.Linq.DataContext> gestisce gli oggetti prevede la registrazione delle identità degli oggetti in una cache delle identità durante l'esecuzione delle query.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-104">In LINQ to SQL, one of the ways in which the <xref:System.Data.Linq.DataContext> manages objects is by logging object identities in an identity cache as queries are executed.</span></span> <span data-ttu-id="0ffd7-105">In alcuni casi, LINQ to SQL tenterà di recuperare un oggetto dalla cache delle identità prima di eseguire una query nel database.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-105">In some cases, LINQ to SQL will attempt to retrieve an object from the identity cache before executing a query in the database.</span></span>  
  
 <span data-ttu-id="0ffd7-106">In generale, affinché una query LINQ to SQL restituisca un oggetto dalla cache delle identità, la query deve essere basata sulla chiave primaria di un oggetto e deve restituire un unico oggetto.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-106">In general, for a LINQ to SQL query to return an object from the identity cache, the query must be based on the primary key of an object and must return a single object.</span></span> <span data-ttu-id="0ffd7-107">In particolare, il formato della query deve essere uno di quelli illustrati di seguito.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-107">In particular, the query must be in one of the general forms shown below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ffd7-108">Le query precompilate non restituiranno oggetti dalla cache delle identità.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-108">Pre-compiled queries will not return objects from the identity cache.</span></span> <span data-ttu-id="0ffd7-109">Per ulteriori informazioni sulle query pre-compilate, vedere <xref:System.Data.Linq.CompiledQuery> e [come: Store e riutilizzare le query](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0ffd7-109">For more information about pre-compiled queries, see <xref:System.Data.Linq.CompiledQuery> and [How to: Store and Reuse Queries](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).</span></span>  
  
 <span data-ttu-id="0ffd7-110">Il formato di una query deve essere uno dei formati generali riportati di seguito per poter recuperare un oggetto dalla cache delle identità:</span><span class="sxs-lookup"><span data-stu-id="0ffd7-110">A query must be in one of the following general forms to retrieve an object from the identity cache:</span></span>  
  
-   <span data-ttu-id="0ffd7-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span><span class="sxs-lookup"><span data-stu-id="0ffd7-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span></span>  
  
-   <span data-ttu-id="0ffd7-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span><span class="sxs-lookup"><span data-stu-id="0ffd7-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span></span>  
  
 <span data-ttu-id="0ffd7-113">In questi formati generali, `Function1`, `Function2` e `predicate` vengono definiti nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-113">In these general forms, `Function1`, `Function2`, and `predicate` are defined as follows.</span></span>  
  
 <span data-ttu-id="0ffd7-114">`Function1` può essere uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ffd7-114">`Function1` can be any of the following:</span></span>  
  
-   <xref:System.Linq.Queryable.Where%2A>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="0ffd7-115">`Function2` può essere uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ffd7-115">`Function2` can be any of the following:</span></span>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="0ffd7-116">`predicate` deve essere un'espressione in cui la proprietà della chiave primaria dell'oggetto è impostata su un valore costante.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-116">`predicate` must be an expression in which the object's primary key property is set to a constant value.</span></span> <span data-ttu-id="0ffd7-117">Se un oggetto dispone di una chiave primaria definita da più proprietà, ogni proprietà della chiave primaria deve essere impostata su un valore costante.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-117">If an object has a primary key defined by more than one property, each primary key property must be set to a constant value.</span></span> <span data-ttu-id="0ffd7-118">Di seguito sono riportati esempi del formato che deve essere adottato da `predicate`:</span><span class="sxs-lookup"><span data-stu-id="0ffd7-118">The following are examples of the form `predicate` must take:</span></span>  
  
-   `c => c.PK == constant_value`  
  
-   `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a><span data-ttu-id="0ffd7-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ffd7-119">Example</span></span>  
 <span data-ttu-id="0ffd7-120">Nel codice seguente vengono forniti esempi di tipi di query LINQ to SQL che recuperano un oggetto dalla cache delle identità.</span><span class="sxs-lookup"><span data-stu-id="0ffd7-120">The following code provides examples of the types of LINQ to SQL queries that retrieve an object from the identity cache.</span></span>  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0ffd7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ffd7-121">See Also</span></span>  
 [<span data-ttu-id="0ffd7-122">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="0ffd7-122">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="0ffd7-123">Identità degli oggetti</span><span class="sxs-lookup"><span data-stu-id="0ffd7-123">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)  
 [<span data-ttu-id="0ffd7-124">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="0ffd7-124">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="0ffd7-125">Identità degli oggetti</span><span class="sxs-lookup"><span data-stu-id="0ffd7-125">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)
