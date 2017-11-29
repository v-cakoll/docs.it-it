---
title: 'Esempi di sintassi di espressione di query: operatori di aggregazione (LINQ to DataSet)'
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
ms.assetid: 85dafa07-e102-46e7-ab78-37bf06f257a6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 399f7c2ace937c480ca85176895a5487fc2ead78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="query-expression-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="fcea4-102">Esempi di sintassi di espressione di query: operatori di aggregazione (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="fcea4-102">Query Expression Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="fcea4-103">Negli esempi di questo argomento viene illustrato l'uso dei metodi <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> e <xref:System.Linq.Enumerable.Sum%2A> per eseguire una query su un oggetto <xref:System.Data.DataSet> e aggregare i dati usando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="fcea4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data using query expression syntax.</span></span>  
  
 <span data-ttu-id="fcea4-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [durante il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="fcea4-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="fcea4-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="fcea4-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="fcea4-106">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="fcea4-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="fcea4-107">Per ulteriori informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="fcea4-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="average"></a><span data-ttu-id="fcea4-108">Media</span><span class="sxs-lookup"><span data-stu-id="fcea4-108">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="fcea4-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-109">Example</span></span>  
 <span data-ttu-id="fcea4-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per individuare il prezzo medio di listino dei prodotti dei singoli stili.</span><span class="sxs-lookup"><span data-stu-id="fcea4-110">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="fcea4-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-111">Example</span></span>  
 <span data-ttu-id="fcea4-112">In questo esempio viene usato <xref:System.Linq.Enumerable.Average%2A> per ottenere il totale medio dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="fcea4-112">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="fcea4-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-113">Example</span></span>  
 <span data-ttu-id="fcea4-114">In questo esempio viene usato <xref:System.Linq.Enumerable.Average%2A> per ottenere gli ordini con il valore `TotalDue` medio per i singoli contatti.</span><span class="sxs-lookup"><span data-stu-id="fcea4-114">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="fcea4-115">Conteggio</span><span class="sxs-lookup"><span data-stu-id="fcea4-115">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="fcea4-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-116">Example</span></span>  
 <span data-ttu-id="fcea4-117">In questo esempio viene usato <xref:System.Linq.Enumerable.Count%2A> per restituire un elenco di ID contatto e un elenco degli ordini relativi a ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="fcea4-117">This example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="fcea4-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-118">Example</span></span>  
 <span data-ttu-id="fcea4-119">In questo esempio i prodotti vengono raggruppati in base al colore e viene usato <xref:System.Linq.Enumerable.Count%2A> per restituire il numero di prodotti inclusi in ciascun gruppo.</span><span class="sxs-lookup"><span data-stu-id="fcea4-119">This example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="fcea4-120">Max</span><span class="sxs-lookup"><span data-stu-id="fcea4-120">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="fcea4-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-121">Example</span></span>  
 <span data-ttu-id="fcea4-122">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Max%2A> per ottenere il totale massimo dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="fcea4-122">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="fcea4-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-123">Example</span></span>  
 <span data-ttu-id="fcea4-124">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Max%2A> per ottenere gli ordini con il valore massimo di `TotalDue` per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="fcea4-124">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="fcea4-125">Min</span><span class="sxs-lookup"><span data-stu-id="fcea4-125">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="fcea4-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-126">Example</span></span>  
 <span data-ttu-id="fcea4-127">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Min%2A> per ottenere il totale minimo dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="fcea4-127">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="fcea4-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-128">Example</span></span>  
 <span data-ttu-id="fcea4-129">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Min%2A> per ottenere gli ordini con il totale minimo dovuto per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="fcea4-129">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="fcea4-130">Sum</span><span class="sxs-lookup"><span data-stu-id="fcea4-130">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="fcea4-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcea4-131">Example</span></span>  
 <span data-ttu-id="fcea4-132">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Sum%2A> per ottenere il totale dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="fcea4-132">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="fcea4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcea4-133">See Also</span></span>  
 [<span data-ttu-id="fcea4-134">Caricamento di dati in un set di dati</span><span class="sxs-lookup"><span data-stu-id="fcea4-134">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="fcea4-135">LINQ to DataSet esempi</span><span class="sxs-lookup"><span data-stu-id="fcea4-135">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="fcea4-136">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="fcea4-136">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
