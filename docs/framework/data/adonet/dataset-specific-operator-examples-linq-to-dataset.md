---
title: Esempi di operatori specifici di dataset (LINQ to DataSet)
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
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 02c923bc873eb5135cd3b1841226bc8013e04abd
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="e5c47-102">Esempi di operatori specifici di dataset (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e5c47-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="e5c47-103">Negli esempi di questo argomento viene illustrato l'uso del metodo <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> e della classe <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="e5c47-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="e5c47-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [durante il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="e5c47-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e5c47-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e5c47-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e5c47-106">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="e5c47-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="e5c47-107">Per ulteriori informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="e5c47-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="e5c47-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="e5c47-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="e5c47-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5c47-109">Example</span></span>  
 <span data-ttu-id="e5c47-110">In questo esempio viene caricato un oggetto <xref:System.Data.DataTable> con i risultati della query usando il metodo <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="e5c47-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="e5c47-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="e5c47-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="e5c47-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5c47-112">Example</span></span>  
 <span data-ttu-id="e5c47-113">In questo esempio vengono confrontate due righe di dati diverse usando <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="e5c47-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="e5c47-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5c47-114">See Also</span></span>  
 [<span data-ttu-id="e5c47-115">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="e5c47-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="e5c47-116">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e5c47-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
