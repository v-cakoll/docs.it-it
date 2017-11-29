---
title: 'Method-Based Query Syntax Examples: Partitioning (LINQ'
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
ms.assetid: a582c53f-f203-44ae-a797-d7f169a4fbb5
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 342c085becb0e14d7c57a9e67e21210e98415f2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="method-based-query-syntax-examples-partitioning-linq"></a><span data-ttu-id="9bba4-102">Method-Based Query Syntax Examples: Partitioning (LINQ</span><span class="sxs-lookup"><span data-stu-id="9bba4-102">Method-Based Query Syntax Examples: Partitioning (LINQ</span></span>
<span data-ttu-id="9bba4-103">Negli esempi di questo argomento viene illustrato l'uso dei metodi <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.TakeWhile%2A> per eseguire una query su <xref:System.Data.DataSet> usando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="9bba4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A>, and <xref:System.Linq.Enumerable.TakeWhile%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="9bba4-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [durante il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="9bba4-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="9bba4-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9bba4-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="9bba4-106">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="9bba4-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="9bba4-107">Per ulteriori informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="9bba4-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="skip"></a><span data-ttu-id="9bba4-108">Skip</span><span class="sxs-lookup"><span data-stu-id="9bba4-108">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="9bba4-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bba4-109">Example</span></span>  
 <span data-ttu-id="9bba4-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Skip%2A> per ottenere tutti i contatti ad eccezione dei primi cinque della tabella `Contact`.</span><span class="sxs-lookup"><span data-stu-id="9bba4-110">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="9bba4-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bba4-111">Example</span></span>  
 <span data-ttu-id="9bba4-112">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Skip%2A> per ottenere tutti gli indirizzi di Seattle ad eccezione dei primi due.</span><span class="sxs-lookup"><span data-stu-id="9bba4-112">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="skipwhile"></a><span data-ttu-id="9bba4-113">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="9bba4-113">SkipWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="9bba4-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bba4-114">Example</span></span>  
 <span data-ttu-id="9bba4-115">In questo esempio vengono usati i metodi <xref:System.Linq.Enumerable.OrderBy%2A> e <xref:System.Linq.Enumerable.SkipWhile%2A> per restituire i prodotti della tabella `Product` il cui prezzo di listino è maggiore di 300.00.</span><span class="sxs-lookup"><span data-stu-id="9bba4-115">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.SkipWhile%2A> methods to return products from the `Product` table with a list price greater than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipwhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipwhilesimple_mq)]  
  
## <a name="take"></a><span data-ttu-id="9bba4-116">Take</span><span class="sxs-lookup"><span data-stu-id="9bba4-116">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="9bba4-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bba4-117">Example</span></span>  
 <span data-ttu-id="9bba4-118">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Take%2A> per ottenere solo i primi cinque contatti della tabella `Contact`.</span><span class="sxs-lookup"><span data-stu-id="9bba4-118">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="9bba4-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bba4-119">Example</span></span>  
 <span data-ttu-id="9bba4-120">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Take%2A> per ottenere i primi tre indirizzi di Seattle.</span><span class="sxs-lookup"><span data-stu-id="9bba4-120">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="takewhile"></a><span data-ttu-id="9bba4-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="9bba4-121">TakeWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="9bba4-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="9bba4-122">Example</span></span>  
 <span data-ttu-id="9bba4-123">In questo esempio vengono usati i metodi <xref:System.Linq.Enumerable.OrderBy%2A> e <xref:System.Linq.Enumerable.TakeWhile%2A> per restituire i prodotti della tabella `Product` il cui prezzo di listino è minore di 300.00.</span><span class="sxs-lookup"><span data-stu-id="9bba4-123">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.TakeWhile%2A> to return products from the `Product` table with a list price less than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takewhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takewhilesimple_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="9bba4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bba4-124">See Also</span></span>  
 [<span data-ttu-id="9bba4-125">Caricamento di dati in un set di dati</span><span class="sxs-lookup"><span data-stu-id="9bba4-125">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="9bba4-126">LINQ to DataSet esempi</span><span class="sxs-lookup"><span data-stu-id="9bba4-126">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="9bba4-127">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="9bba4-127">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
