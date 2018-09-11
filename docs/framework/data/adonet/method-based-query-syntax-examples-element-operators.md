---
title: 'Esempi di sintassi di query basate sul metodo: operatori di elemento (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
ms.openlocfilehash: 2a52bf4a2a4999257377c7303cb6d362136d73a5
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44274700"
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="260f3-102">Esempi di sintassi di query basate sul metodo: operatori di elemento (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="260f3-102">Method-Based Query Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="260f3-103">Negli esempi di questo argomento viene illustrato come usare i metodi <xref:System.Linq.Enumerable.First%2A> e <xref:System.Linq.Enumerable.ElementAt%2A> per ottenere elementi di <xref:System.Data.DataRow> da <xref:System.Data.DataSet> usando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="260f3-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="260f3-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="260f3-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="260f3-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="260f3-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="260f3-106">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="260f3-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]   
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]     

 <span data-ttu-id="260f3-107">Per altre informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="260f3-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="260f3-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="260f3-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="260f3-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="260f3-109">Example</span></span>  
 <span data-ttu-id="260f3-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.ElementAt%2A> per recuperare il quinto indirizzo in cui `PostalCode` == "M4B 1V7".</span><span class="sxs-lookup"><span data-stu-id="260f3-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]   
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]     
  
## <a name="first"></a><span data-ttu-id="260f3-111">First</span><span class="sxs-lookup"><span data-stu-id="260f3-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="260f3-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="260f3-112">Example</span></span>  
 <span data-ttu-id="260f3-113">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.First%2A> per restituire il primo contatto il cui nome è 'Brooke'.</span><span class="sxs-lookup"><span data-stu-id="260f3-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]   
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)] 
  
## <a name="see-also"></a><span data-ttu-id="260f3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="260f3-114">See Also</span></span>  
 [<span data-ttu-id="260f3-115">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="260f3-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="260f3-116">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="260f3-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="260f3-117">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="260f3-117">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
