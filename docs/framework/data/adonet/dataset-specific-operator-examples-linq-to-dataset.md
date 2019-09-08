---
title: Esempi di operatori specifici di dataset (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 6a9dc82e0bb065b455c0208daaf2d28a74cd7e34
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784209"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="ed780-102">Esempi di operatori specifici di dataset (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ed780-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="ed780-103">Negli esempi di questo argomento viene illustrato l'uso del metodo <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> e della classe <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="ed780-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="ed780-104">Il `FillDataSet` metodo utilizzato in questi esempi viene specificato nel [caricamento di dati in un DataSet](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="ed780-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="ed780-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ed780-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ed780-106">Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`</span><span class="sxs-lookup"><span data-stu-id="ed780-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="ed780-107">Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="ed780-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="ed780-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="ed780-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="ed780-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed780-109">Example</span></span>  
 <span data-ttu-id="ed780-110">In questo esempio viene caricato un oggetto <xref:System.Data.DataTable> con i risultati della query usando il metodo <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="ed780-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="ed780-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="ed780-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="ed780-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed780-112">Example</span></span>  
 <span data-ttu-id="ed780-113">In questo esempio vengono confrontate due righe di dati diverse usando <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="ed780-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="ed780-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed780-114">See also</span></span>

- [<span data-ttu-id="ed780-115">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="ed780-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="ed780-116">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ed780-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
