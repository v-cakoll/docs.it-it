---
title: 'Esempi di sintassi di espressione di query: ordinamento (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 653a4a97-1e4a-4b2d-8d24-7dbe1f2a5c84
ms.openlocfilehash: 1e3ee4372c1c2173cff0d93dfdf84c96c60130d4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45597459"
---
# <a name="query-expression-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="83e05-102">Esempi di sintassi di espressione di query: ordinamento (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="83e05-102">Query Expression Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="83e05-103">Negli esempi di questo argomento viene illustrato come usare i metodi <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> e <xref:System.Linq.Enumerable.ThenByDescending%2A> per eseguire una query su <xref:System.Data.DataSet> e ordinare i risultati usando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="83e05-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results using the query expression syntax.</span></span>  
  
 <span data-ttu-id="83e05-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="83e05-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="83e05-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="83e05-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="83e05-106">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="83e05-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="83e05-107">Per altre informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="83e05-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="83e05-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="83e05-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="83e05-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="83e05-109">Example</span></span>  
 <span data-ttu-id="83e05-110">In questo esempio viene usato <xref:System.Linq.Enumerable.OrderBy%2A> per restituire un elenco di contatti ordinati in base al cognome.</span><span class="sxs-lookup"><span data-stu-id="83e05-110">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="83e05-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="83e05-111">Example</span></span>  
 <span data-ttu-id="83e05-112">In questo esempio viene usato <xref:System.Linq.Enumerable.OrderBy%2A> per ordinare un elenco di contatti in base alla lunghezza del cognome.</span><span class="sxs-lookup"><span data-stu-id="83e05-112">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="83e05-113">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="83e05-113">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="83e05-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="83e05-114">Example</span></span>  
 <span data-ttu-id="83e05-115">In questo esempio viene usato `orderby… descending` (`Order By … Descending`), equivalente al metodo <xref:System.Linq.Enumerable.OrderByDescending%2A>, per ordinare il listino prezzi dal massimo al minimo.</span><span class="sxs-lookup"><span data-stu-id="83e05-115">This example uses `orderby… descending` (`Order By … Descending`), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="reverse"></a><span data-ttu-id="83e05-116">Reverse</span><span class="sxs-lookup"><span data-stu-id="83e05-116">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="83e05-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="83e05-117">Example</span></span>  
 <span data-ttu-id="83e05-118">In questo esempio viene usato <xref:System.Linq.Enumerable.Reverse%2A> per creare un elenco di ordini in cui il valore di `OrderDate` è precedente al 20 febbraio 2002.</span><span class="sxs-lookup"><span data-stu-id="83e05-118">This example uses <xref:System.Linq.Enumerable.Reverse%2A> to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="83e05-119">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="83e05-119">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="83e05-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="83e05-120">Example</span></span>  
 <span data-ttu-id="83e05-121">In questo esempio viene usato `OrderBy… Descending`, equivalente al metodo <xref:System.Linq.Enumerable.ThenByDescending%2A>, per ordinare un elenco di prodotti dapprima in base al nome e quindi in base al prezzo di listino, dal massimo al minimo.</span><span class="sxs-lookup"><span data-stu-id="83e05-121">This example uses `OrderBy… Descending` , which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price, from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="83e05-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83e05-122">See Also</span></span>  
 [<span data-ttu-id="83e05-123">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="83e05-123">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="83e05-124">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="83e05-124">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="83e05-125">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="83e05-125">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
