---
title: 'Esempi di sintassi delle query basate su metodo: Operatori di aggregazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0e306067-5720-4782-9719-2286570a7e47
ms.openlocfilehash: d9007e4d650c79a636f908a638bb382457f6b29b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250273"
---
# <a name="method-based-query-syntax-examples-aggregate-operators"></a><span data-ttu-id="a29aa-102">Esempi di sintassi delle query basate su metodo: Operatori di aggregazione</span><span class="sxs-lookup"><span data-stu-id="a29aa-102">Method-Based Query Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="a29aa-103">Negli esempi di questo argomento viene illustrato come utilizzare i <xref:System.Linq.Enumerable.Aggregate%2A>metodi <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, e <xref:System.Linq.Enumerable.Sum%2A> per eseguire query sul [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) utilizzando sintassi delle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="a29aa-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="a29aa-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a29aa-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="a29aa-105">Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`</span><span class="sxs-lookup"><span data-stu-id="a29aa-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="a29aa-106">Media</span><span class="sxs-lookup"><span data-stu-id="a29aa-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="a29aa-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-107">Example</span></span>  
 <span data-ttu-id="a29aa-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per individuare il prezzo medio di listino dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="a29aa-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-109">Example</span></span>  
 <span data-ttu-id="a29aa-110">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per individuare il prezzo medio di listino dei prodotti per ogni stile.</span><span class="sxs-lookup"><span data-stu-id="a29aa-110">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-111">Example</span></span>  
 <span data-ttu-id="a29aa-112">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per individuare il totale medio dovuto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-112">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-113">Example</span></span>  
 <span data-ttu-id="a29aa-114">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per ottenere il totale medio dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-114">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-115">Example</span></span>  
 <span data-ttu-id="a29aa-116">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Average%2A> per ottenere gli ordini con il totale medio dovuto per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-116">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="a29aa-117">Conteggio</span><span class="sxs-lookup"><span data-stu-id="a29aa-117">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="a29aa-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-118">Example</span></span>  
 <span data-ttu-id="a29aa-119">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Count%2A> per restituire il numero di prodotti presenti nella tabella Product.</span><span class="sxs-lookup"><span data-stu-id="a29aa-119">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the Product table.</span></span>  
  
 [!code-csharp[DP L2E Examples#Count](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#count)]
 [!code-vb[DP L2E Examples#Count](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-120">Example</span></span>  
 <span data-ttu-id="a29aa-121">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Count%2A> per restituire un elenco di ID contatto e la rispettiva quantità di ordini.</span><span class="sxs-lookup"><span data-stu-id="a29aa-121">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-122">Example</span></span>  
 <span data-ttu-id="a29aa-123">Nell'esempio seguente i prodotti vengono raggruppati in base al colore e viene usato il metodo <xref:System.Linq.Enumerable.Count%2A> per restituire il numero di prodotti inclusi in ciascun gruppo.</span><span class="sxs-lookup"><span data-stu-id="a29aa-123">The following example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="a29aa-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="a29aa-124">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="a29aa-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-125">Example</span></span>  
 <span data-ttu-id="a29aa-126">Nell'esempio seguente viene restituito il conteggio dei contatti come valore long integer.</span><span class="sxs-lookup"><span data-stu-id="a29aa-126">The following example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="a29aa-127">Max</span><span class="sxs-lookup"><span data-stu-id="a29aa-127">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="a29aa-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-128">Example</span></span>  
 <span data-ttu-id="a29aa-129">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Max%2A> per ottenere il totale massimo dovuto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-129">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-130">Example</span></span>  
 <span data-ttu-id="a29aa-131">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Max%2A> per ottenere il totale massimo dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-131">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-132">Example</span></span>  
 <span data-ttu-id="a29aa-133">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Max%2A> per ottenere gli ordini con il totale massimo dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-133">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="a29aa-134">Min</span><span class="sxs-lookup"><span data-stu-id="a29aa-134">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="a29aa-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-135">Example</span></span>  
 <span data-ttu-id="a29aa-136">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Min%2A> per ottenere il totale minimo dovuto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-136">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-137">Example</span></span>  
 <span data-ttu-id="a29aa-138">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Min%2A> per ottenere il totale minimo dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-138">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-139">Example</span></span>  
 <span data-ttu-id="a29aa-140">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Min%2A> per ottenere gli ordini con il totale minimo dovuto per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-140">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="a29aa-141">Sum</span><span class="sxs-lookup"><span data-stu-id="a29aa-141">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="a29aa-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-142">Example</span></span>  
 <span data-ttu-id="a29aa-143">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Sum%2A> per ottenere il numero totale di quantitativi ordinati inclusi nella tabella SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="a29aa-143">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the SalesOrderDetail table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumprojection_mq)]
 [!code-vb[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="a29aa-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="a29aa-144">Example</span></span>  
 <span data-ttu-id="a29aa-145">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Sum%2A> per ottenere il totale dovuto per ogni ID contatto.</span><span class="sxs-lookup"><span data-stu-id="a29aa-145">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="a29aa-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a29aa-146">See also</span></span>

- [<span data-ttu-id="a29aa-147">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="a29aa-147">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
