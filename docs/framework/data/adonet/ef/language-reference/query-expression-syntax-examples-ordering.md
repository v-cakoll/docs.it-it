---
title: 'Esempi di sintassi delle espressioni di query: Ordering'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: fbcb6ffe27234beb120e71ebc71c782abd4be24a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249460"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="72eb2-102">Esempi di sintassi delle espressioni di query: Ordering</span><span class="sxs-lookup"><span data-stu-id="72eb2-102">Query Expression Syntax Examples: Ordering</span></span>
<span data-ttu-id="72eb2-103">Negli esempi di questo argomento viene illustrato come utilizzare i `OrderBy` metodi `OrderByDescending` e per eseguire query sul [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) utilizzando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="72eb2-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="72eb2-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="72eb2-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="72eb2-105">Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`</span><span class="sxs-lookup"><span data-stu-id="72eb2-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="72eb2-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="72eb2-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="72eb2-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="72eb2-107">Example</span></span>  
 <span data-ttu-id="72eb2-108">Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.OrderBy%2A> per restituire un elenco di contatti ordinati in base al cognome.</span><span class="sxs-lookup"><span data-stu-id="72eb2-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="72eb2-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="72eb2-109">Example</span></span>  
 <span data-ttu-id="72eb2-110">Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.OrderBy%2A> per ordinare un elenco di contatti in base alla lunghezza del cognome.</span><span class="sxs-lookup"><span data-stu-id="72eb2-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="72eb2-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="72eb2-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="72eb2-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="72eb2-112">Example</span></span>  
 <span data-ttu-id="72eb2-113">Nell'esempio seguente viene usato `orderby… descending` (`Order By … Descending` in Visual Basic), equivalente al metodo <xref:System.Linq.Enumerable.OrderByDescending%2A>, per ordinare il listino prezzi dal prezzo massimo al prezzo minimo.</span><span class="sxs-lookup"><span data-stu-id="72eb2-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="72eb2-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="72eb2-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="72eb2-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="72eb2-115">Example</span></span>  
 <span data-ttu-id="72eb2-116">Nell'esempio seguente vengono usati <xref:System.Linq.Queryable.OrderBy%2A> e <xref:System.Linq.Queryable.ThenBy%2A> per restituire un elenco di contatti ordinati in base al cognome e quindi al nome.</span><span class="sxs-lookup"><span data-stu-id="72eb2-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="72eb2-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="72eb2-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="72eb2-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="72eb2-118">Example</span></span>  
 <span data-ttu-id="72eb2-119">Nell'esempio seguente viene usato `OrderBy… Descending`, equivalente al metodo <xref:System.Linq.Enumerable.ThenByDescending%2A>, per ordinare un elenco di prodotti dapprima in base al nome e quindi in base al prezzo di listino, dal prezzo massimo al prezzo minimo.</span><span class="sxs-lookup"><span data-stu-id="72eb2-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="72eb2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72eb2-120">See also</span></span>

- [<span data-ttu-id="72eb2-121">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="72eb2-121">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
