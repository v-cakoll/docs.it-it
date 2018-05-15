---
title: 'Esempi di sintassi di query basate sul metodo: operatori di aggregazione (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ed5f01d-acb2-4dd4-be60-f04c2d570fa8
ms.openlocfilehash: 40a1ba551d261091ad38c2e6758ff65622bef0ec
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="13a92-102">Esempi di sintassi di query basate sul metodo: operatori di aggregazione (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="13a92-102">Method-Based Query Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="13a92-103">Negli esempi di questo argomento viene illustrato l'uso degli operatori <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> e <xref:System.Linq.Enumerable.Sum%2A> per eseguire una query su un oggetto <xref:System.Data.DataSet> e aggregare i dati usando la sintassi delle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="13a92-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> operators to query a <xref:System.Data.DataSet> and aggregate data using method query syntax.</span></span>  
  
 <span data-ttu-id="13a92-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [durante il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="13a92-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="13a92-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="13a92-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="13a92-106">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="13a92-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="13a92-107">Per ulteriori informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="13a92-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="aggregate"></a><span data-ttu-id="13a92-108">Aggregate</span><span class="sxs-lookup"><span data-stu-id="13a92-108">Aggregate</span></span>  
  
### <a name="example"></a><span data-ttu-id="13a92-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-109">Example</span></span>  
 <span data-ttu-id="13a92-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Aggregate%2A> per ottenere i primi 5 contatti dalla tabella `Contact` e compilare un elenco delimitato da virgole degli ultimi nomi.</span><span class="sxs-lookup"><span data-stu-id="13a92-110">This example uses the <xref:System.Linq.Enumerable.Aggregate%2A> method to get the first 5 contacts from the `Contact` table and build a comma-delimited list of the last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#aggregate_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#aggregate_mq)]  
  
## <a name="average"></a><span data-ttu-id="13a92-111">Average</span><span class="sxs-lookup"><span data-stu-id="13a92-111">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="13a92-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-112">Example</span></span>  
 <span data-ttu-id="13a92-113">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per individuare il prezzo medio di listino dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="13a92-113">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="13a92-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-114">Example</span></span>  
 <span data-ttu-id="13a92-115">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per individuare il prezzo medio di listino dei prodotti dei singoli stili.</span><span class="sxs-lookup"><span data-stu-id="13a92-115">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="13a92-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-116">Example</span></span>  
 <span data-ttu-id="13a92-117">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per individuare il totale medio dovuto.</span><span class="sxs-lookup"><span data-stu-id="13a92-117">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="13a92-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-118">Example</span></span>  
 <span data-ttu-id="13a92-119">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per ottenere il totale medio dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="13a92-119">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="13a92-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-120">Example</span></span>  
 <span data-ttu-id="13a92-121">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per ottenere gli ordini con il valore medio di `TotalDue` per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="13a92-121">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="13a92-122">Conteggio</span><span class="sxs-lookup"><span data-stu-id="13a92-122">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="13a92-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-123">Example</span></span>  
 <span data-ttu-id="13a92-124">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Count%2A> per restituire i numero di prodotti presenti nella tabella `Product`.</span><span class="sxs-lookup"><span data-stu-id="13a92-124">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the `Product` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#count)]
 [!code-vb[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="13a92-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-125">Example</span></span>  
 <span data-ttu-id="13a92-126">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Count%2A> per restituire un elenco di ID contatto e un elenco degli ordini relativi a ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="13a92-126">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="13a92-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-127">Example</span></span>  
 <span data-ttu-id="13a92-128">In questo esempio i prodotti vengono raggruppati in base al colore e viene usato il metodo <xref:System.Linq.Enumerable.Count%2A> per restituire il numero di prodotti inclusi in ciascun gruppo.</span><span class="sxs-lookup"><span data-stu-id="13a92-128">This example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="13a92-129">LongCount</span><span class="sxs-lookup"><span data-stu-id="13a92-129">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="13a92-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-130">Example</span></span>  
 <span data-ttu-id="13a92-131">In questo esempio si ottiene il conteggio dei contatti come valore long integer.</span><span class="sxs-lookup"><span data-stu-id="13a92-131">This example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="13a92-132">Max</span><span class="sxs-lookup"><span data-stu-id="13a92-132">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="13a92-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-133">Example</span></span>  
 <span data-ttu-id="13a92-134">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Max%2A> per ottenere il totale massimo dovuto.</span><span class="sxs-lookup"><span data-stu-id="13a92-134">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="13a92-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-135">Example</span></span>  
 <span data-ttu-id="13a92-136">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Max%2A> per ottenere il totale massimo dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="13a92-136">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="13a92-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-137">Example</span></span>  
 <span data-ttu-id="13a92-138">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Max%2A> per ottenere gli ordini con il valore massimo di `TotalDue` per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="13a92-138">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="13a92-139">Min</span><span class="sxs-lookup"><span data-stu-id="13a92-139">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="13a92-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-140">Example</span></span>  
 <span data-ttu-id="13a92-141">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Min%2A> per ottenere il totale minimo dovuto.</span><span class="sxs-lookup"><span data-stu-id="13a92-141">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="13a92-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-142">Example</span></span>  
 <span data-ttu-id="13a92-143">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Min%2A> per ottenere il totale minimo dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="13a92-143">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="13a92-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-144">Example</span></span>  
 <span data-ttu-id="13a92-145">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Min%2A> per ottenere gli ordini con il totale minimo dovuto per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="13a92-145">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="13a92-146">Sum</span><span class="sxs-lookup"><span data-stu-id="13a92-146">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="13a92-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-147">Example</span></span>  
 <span data-ttu-id="13a92-148">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Sum%2A> per ottenere il numero totale di quantitativi ordinati presenti nella tabella `SalesOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="13a92-148">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the `SalesOrderDetail` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="13a92-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="13a92-149">Example</span></span>  
 <span data-ttu-id="13a92-150">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Sum%2A> per ottenere il totale dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="13a92-150">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="13a92-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13a92-151">See Also</span></span>  
 [<span data-ttu-id="13a92-152">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="13a92-152">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="13a92-153">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="13a92-153">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="13a92-154">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="13a92-154">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
