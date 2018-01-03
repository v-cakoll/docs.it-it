---
title: 'Esempi di sintassi di espressione di query: restrizione (LINQ to DataSet)'
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
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 99aca5fc829c38a33fbeb1bb51e8c279bff75fae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a><span data-ttu-id="981fd-102">Esempi di sintassi di espressione di query: restrizione (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="981fd-102">Query Expression Syntax Examples: Restriction (LINQ to DataSet)</span></span>
<span data-ttu-id="981fd-103">Negli esempi di questo argomento viene illustrato l'uso del metodo <xref:System.Linq.Enumerable.Where%2A> per eseguire una query su <xref:System.Data.DataSet> usando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="981fd-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="981fd-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [durante il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="981fd-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="981fd-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="981fd-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="981fd-106">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="981fd-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]        
  
 <span data-ttu-id="981fd-107">Per ulteriori informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="981fd-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="where"></a><span data-ttu-id="981fd-108">Dove</span><span class="sxs-lookup"><span data-stu-id="981fd-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="981fd-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="981fd-109">Example</span></span>  
 <span data-ttu-id="981fd-110">In questo esempio vengono restituiti tutti gli ordini online.</span><span class="sxs-lookup"><span data-stu-id="981fd-110">This example returns all online orders.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]     
  
### <a name="example"></a><span data-ttu-id="981fd-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="981fd-111">Example</span></span>  
 <span data-ttu-id="981fd-112">In questo esempio vengono restituiti gli ordini in cui la quantità ordinata è maggiore di 2 e minore di 6.</span><span class="sxs-lookup"><span data-stu-id="981fd-112">This example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]     
  
### <a name="example"></a><span data-ttu-id="981fd-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="981fd-113">Example</span></span>  
 <span data-ttu-id="981fd-114">In questo esempio vengono restituiti tutti i prodotti di colore rosso.</span><span class="sxs-lookup"><span data-stu-id="981fd-114">This example returns all red colored products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]     
  
### <a name="example"></a><span data-ttu-id="981fd-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="981fd-115">Example</span></span>  
 <span data-ttu-id="981fd-116">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Where%2A> per individuare gli ordini effettuati dopo il 1 dicembre 2002, quindi viene usato il metodo <xref:System.Data.DataRow.GetChildRows%2A> per ottenere i dettagli relativi a ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="981fd-116">This example uses the <xref:System.Linq.Enumerable.Where%2A> method to find orders that were made after December 1, 2002 and then uses the <xref:System.Data.DataRow.GetChildRows%2A> method to get the details for each order.</span></span>  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]       
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a><span data-ttu-id="981fd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="981fd-117">See Also</span></span>  
 [<span data-ttu-id="981fd-118">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="981fd-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="981fd-119">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="981fd-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="981fd-120">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="981fd-120">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
