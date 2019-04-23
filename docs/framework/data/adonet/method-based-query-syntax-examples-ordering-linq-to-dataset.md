---
title: 'Esempi di sintassi delle query basate su metodo: Ordinamento (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: 76bc4751a25e82a731e136f838d12b8d1c1d691f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119561"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="7d7ee-102">Esempi di sintassi delle query basate su metodo: Ordinamento (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="7d7ee-102">Method-Based Query Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="7d7ee-103">Negli esempi di questo argomento viene illustrato come usare i metodi <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Reverse%2A> e <xref:System.Linq.Enumerable.ThenBy%2A> per eseguire una query su <xref:System.Data.DataSet> e ordinare i risultati usando la sintassi delle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="7d7ee-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>,  <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenBy%2A> methods to query a <xref:System.Data.DataSet> and order the results using the method query syntax.</span></span>  
  
 <span data-ttu-id="7d7ee-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="7d7ee-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="7d7ee-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7d7ee-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="7d7ee-106">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="7d7ee-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="7d7ee-107">Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7d7ee-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="7d7ee-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="7d7ee-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="7d7ee-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d7ee-109">Example</span></span>  
 <span data-ttu-id="7d7ee-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.OrderBy%2A> con un operatore di confronto personalizzato per ordinare i cognomi senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="7d7ee-110">This example uses the <xref:System.Linq.Enumerable.OrderBy%2A> method with a custom comparer to do a case-insensitive sort of last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a><span data-ttu-id="7d7ee-111">Reverse</span><span class="sxs-lookup"><span data-stu-id="7d7ee-111">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="7d7ee-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d7ee-112">Example</span></span>  
 <span data-ttu-id="7d7ee-113">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Reverse%2A> per creare un elenco di ordini in cui il valore di `OrderDate` è precedente al 20 febbraio 2002.</span><span class="sxs-lookup"><span data-stu-id="7d7ee-113">This example uses the <xref:System.Linq.Enumerable.Reverse%2A> method to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a><span data-ttu-id="7d7ee-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="7d7ee-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="7d7ee-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d7ee-115">Example</span></span>  
 <span data-ttu-id="7d7ee-116">In questo esempio vengono usati i metodi <xref:System.Linq.Enumerable.OrderBy%2A> e <xref:System.Linq.Enumerable.ThenBy%2A> con un operatore di confronto personalizzato per ordinare prima in base al prezzo di listino e quindi applicare l'ordinamento discendente e senza distinzione tra maiuscole e minuscole ai nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="7d7ee-116">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.ThenBy%2A> methods with a custom comparer to first sort by list price, and then perform a case-insensitive descending sort of the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="7d7ee-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d7ee-117">See also</span></span>

- [<span data-ttu-id="7d7ee-118">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="7d7ee-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="7d7ee-119">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="7d7ee-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="7d7ee-120">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="7d7ee-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="7d7ee-121">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d7ee-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
