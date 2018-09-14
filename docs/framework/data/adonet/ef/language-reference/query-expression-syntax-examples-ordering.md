---
title: "Esempi di sintassi dell'espressione di query: ordinamento"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: bc8bfaabb9e90e66e4ec81e551fd66319a78ca7e
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "44756704"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="968a9-102">Esempi di sintassi dell'espressione di query: ordinamento</span><span class="sxs-lookup"><span data-stu-id="968a9-102">Query Expression Syntax Examples: Ordering</span></span>
<span data-ttu-id="968a9-103">Gli esempi in questo argomento illustrano come usare il `OrderBy` e `OrderByDescending` metodi per eseguire una query il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) usando la sintassi di espressione di query.</span><span class="sxs-lookup"><span data-stu-id="968a9-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="968a9-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="968a9-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="968a9-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="968a9-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="968a9-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="968a9-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="968a9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="968a9-107">Example</span></span>  
 <span data-ttu-id="968a9-108">Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.OrderBy%2A> per restituire un elenco di contatti ordinati in base al cognome.</span><span class="sxs-lookup"><span data-stu-id="968a9-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="968a9-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="968a9-109">Example</span></span>  
 <span data-ttu-id="968a9-110">Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.OrderBy%2A> per ordinare un elenco di contatti in base alla lunghezza del cognome.</span><span class="sxs-lookup"><span data-stu-id="968a9-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="968a9-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="968a9-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="968a9-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="968a9-112">Example</span></span>  
 <span data-ttu-id="968a9-113">Nell'esempio seguente viene usato `orderby… descending` (`Order By … Descending` in Visual Basic), equivalente al metodo <xref:System.Linq.Enumerable.OrderByDescending%2A>, per ordinare il listino prezzi dal prezzo massimo al prezzo minimo.</span><span class="sxs-lookup"><span data-stu-id="968a9-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="968a9-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="968a9-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="968a9-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="968a9-115">Example</span></span>  
 <span data-ttu-id="968a9-116">Nell'esempio seguente vengono usati <xref:System.Linq.Queryable.OrderBy%2A> e <xref:System.Linq.Queryable.ThenBy%2A> per restituire un elenco di contatti ordinati in base al cognome e quindi al nome.</span><span class="sxs-lookup"><span data-stu-id="968a9-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="968a9-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="968a9-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="968a9-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="968a9-118">Example</span></span>  
 <span data-ttu-id="968a9-119">Nell'esempio seguente viene usato `OrderBy… Descending`, equivalente al metodo <xref:System.Linq.Enumerable.ThenByDescending%2A>, per ordinare un elenco di prodotti dapprima in base al nome e quindi in base al prezzo di listino, dal prezzo massimo al prezzo minimo.</span><span class="sxs-lookup"><span data-stu-id="968a9-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="968a9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="968a9-120">See Also</span></span>  
 [<span data-ttu-id="968a9-121">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="968a9-121">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
