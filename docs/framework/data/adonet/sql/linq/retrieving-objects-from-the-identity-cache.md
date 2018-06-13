---
title: Recupero di oggetti dalla cache di identità
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
ms.openlocfilehash: fe22dbdff0e5e9ea6bfe55fc24c492414e01cd6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357608"
---
# <a name="retrieving-objects-from-the-identity-cache"></a><span data-ttu-id="35ed0-102">Recupero di oggetti dalla cache di identità</span><span class="sxs-lookup"><span data-stu-id="35ed0-102">Retrieving Objects from the Identity Cache</span></span>
<span data-ttu-id="35ed0-103">In questo argomento vengono descritti i tipi di query LINQ to SQL che restituiscono un oggetto dalla cache delle identità gestita dall'oggetto <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="35ed0-103">This topic describes the types of LINQ to SQL queries that return an object from the identity cache that is managed by the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="35ed0-104">In LINQ to SQL, uno dei modi in cui l'oggetto <xref:System.Data.Linq.DataContext> gestisce gli oggetti prevede la registrazione delle identità degli oggetti in una cache delle identità durante l'esecuzione delle query.</span><span class="sxs-lookup"><span data-stu-id="35ed0-104">In LINQ to SQL, one of the ways in which the <xref:System.Data.Linq.DataContext> manages objects is by logging object identities in an identity cache as queries are executed.</span></span> <span data-ttu-id="35ed0-105">In alcuni casi, LINQ to SQL tenterà di recuperare un oggetto dalla cache delle identità prima di eseguire una query nel database.</span><span class="sxs-lookup"><span data-stu-id="35ed0-105">In some cases, LINQ to SQL will attempt to retrieve an object from the identity cache before executing a query in the database.</span></span>  
  
 <span data-ttu-id="35ed0-106">In generale, affinché una query LINQ to SQL restituisca un oggetto dalla cache delle identità, la query deve essere basata sulla chiave primaria di un oggetto e deve restituire un unico oggetto.</span><span class="sxs-lookup"><span data-stu-id="35ed0-106">In general, for a LINQ to SQL query to return an object from the identity cache, the query must be based on the primary key of an object and must return a single object.</span></span> <span data-ttu-id="35ed0-107">In particolare, il formato della query deve essere uno di quelli illustrati di seguito.</span><span class="sxs-lookup"><span data-stu-id="35ed0-107">In particular, the query must be in one of the general forms shown below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35ed0-108">Le query precompilate non restituiranno oggetti dalla cache delle identità.</span><span class="sxs-lookup"><span data-stu-id="35ed0-108">Pre-compiled queries will not return objects from the identity cache.</span></span> <span data-ttu-id="35ed0-109">Per ulteriori informazioni sulle query pre-compilate, vedere <xref:System.Data.Linq.CompiledQuery> e [come: Store e riutilizzare le query](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).</span><span class="sxs-lookup"><span data-stu-id="35ed0-109">For more information about pre-compiled queries, see <xref:System.Data.Linq.CompiledQuery> and [How to: Store and Reuse Queries](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).</span></span>  
  
 <span data-ttu-id="35ed0-110">Il formato di una query deve essere uno dei formati generali riportati di seguito per poter recuperare un oggetto dalla cache delle identità:</span><span class="sxs-lookup"><span data-stu-id="35ed0-110">A query must be in one of the following general forms to retrieve an object from the identity cache:</span></span>  
  
-   <span data-ttu-id="35ed0-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span><span class="sxs-lookup"><span data-stu-id="35ed0-111"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`</span></span>  
  
-   <span data-ttu-id="35ed0-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span><span class="sxs-lookup"><span data-stu-id="35ed0-112"><xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`</span></span>  
  
 <span data-ttu-id="35ed0-113">In questi formati generali, `Function1`, `Function2` e `predicate` vengono definiti nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="35ed0-113">In these general forms, `Function1`, `Function2`, and `predicate` are defined as follows.</span></span>  
  
 <span data-ttu-id="35ed0-114">`Function1` può essere uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="35ed0-114">`Function1` can be any of the following:</span></span>  
  
-   <xref:System.Linq.Queryable.Where%2A>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="35ed0-115">`Function2` può essere uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="35ed0-115">`Function2` can be any of the following:</span></span>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 <span data-ttu-id="35ed0-116">`predicate` deve essere un'espressione in cui la proprietà della chiave primaria dell'oggetto è impostata su un valore costante.</span><span class="sxs-lookup"><span data-stu-id="35ed0-116">`predicate` must be an expression in which the object's primary key property is set to a constant value.</span></span> <span data-ttu-id="35ed0-117">Se un oggetto dispone di una chiave primaria definita da più proprietà, ogni proprietà della chiave primaria deve essere impostata su un valore costante.</span><span class="sxs-lookup"><span data-stu-id="35ed0-117">If an object has a primary key defined by more than one property, each primary key property must be set to a constant value.</span></span> <span data-ttu-id="35ed0-118">Di seguito sono riportati esempi del formato che deve essere adottato da `predicate`:</span><span class="sxs-lookup"><span data-stu-id="35ed0-118">The following are examples of the form `predicate` must take:</span></span>  
  
-   `c => c.PK == constant_value`  
  
-   `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a><span data-ttu-id="35ed0-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="35ed0-119">Example</span></span>  
 <span data-ttu-id="35ed0-120">Nel codice seguente vengono forniti esempi di tipi di query LINQ to SQL che recuperano un oggetto dalla cache delle identità.</span><span class="sxs-lookup"><span data-stu-id="35ed0-120">The following code provides examples of the types of LINQ to SQL queries that retrieve an object from the identity cache.</span></span>  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="35ed0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35ed0-121">See Also</span></span>  
 [<span data-ttu-id="35ed0-122">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="35ed0-122">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="35ed0-123">Identità degli oggetti</span><span class="sxs-lookup"><span data-stu-id="35ed0-123">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)  
 [<span data-ttu-id="35ed0-124">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="35ed0-124">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="35ed0-125">Identità degli oggetti</span><span class="sxs-lookup"><span data-stu-id="35ed0-125">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)
