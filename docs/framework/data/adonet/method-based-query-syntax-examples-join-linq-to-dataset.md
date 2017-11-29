---
title: 'Esempi di sintassi di query basate sul metodo: join (LINQ to DataSet)'
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
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b1f32c5fcedf9bd11e44cb9c8d6e6dddf205b865
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a><span data-ttu-id="67828-102">Esempi di sintassi di query basate sul metodo: join (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="67828-102">Method-Based Query Syntax Examples: Join (LINQ to DataSet)</span></span>
<span data-ttu-id="67828-103">La creazione di un join è un'operazione importante in query destinate a origini dati che non presentano relazioni esplorabili tra loro, ad esempio le tabelle di database relazionali.</span><span class="sxs-lookup"><span data-stu-id="67828-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="67828-104">Per join di due origini dati si intende l'associazione degli oggetti di un'origine dati con oggetti che condividono un attributo comune nell'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="67828-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="67828-105">Per ulteriori informazioni, vedere [Cenni preliminari sugli operatori di Query Standard](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="67828-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
 <span data-ttu-id="67828-106">Negli esempi di questo argomento viene illustrato l'uso del metodo <xref:System.Linq.Enumerable.Join%2A> per eseguire una query su <xref:System.Data.DataSet> usando la sintassi delle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="67828-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> method to query a <xref:System.Data.DataSet> using the method query syntax.</span></span>  
  
 <span data-ttu-id="67828-107">Il `FillDataSet` metodo usato in questi esempi è specificato nel [durante il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="67828-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="67828-108">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="67828-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="67828-109">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="67828-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="67828-110">Per ulteriori informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="67828-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="join"></a><span data-ttu-id="67828-111">Join</span><span class="sxs-lookup"><span data-stu-id="67828-111">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="67828-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="67828-112">Example</span></span>  
 <span data-ttu-id="67828-113">In questo esempio viene eseguito un join sulle tabelle `Contact` e `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="67828-113">This example performs a join over the `Contact` and `SalesOrderHeader` tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="67828-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="67828-114">Example</span></span>  
 <span data-ttu-id="67828-115">In questo esempio viene eseguito un join sulle tabelle `Contact` e `SalesOrderHeader`, raggruppando i risultati in base a ID contatto.</span><span class="sxs-lookup"><span data-stu-id="67828-115">This example performs a join over the `Contact` and `SalesOrderHeader` tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="67828-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67828-116">See Also</span></span>  
 [<span data-ttu-id="67828-117">Caricamento di dati in un set di dati</span><span class="sxs-lookup"><span data-stu-id="67828-117">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="67828-118">LINQ to DataSet esempi</span><span class="sxs-lookup"><span data-stu-id="67828-118">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="67828-119">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="67828-119">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 [<span data-ttu-id="67828-120">Esempi di join</span><span class="sxs-lookup"><span data-stu-id="67828-120">Join Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=187357)  
 [<span data-ttu-id="67828-121">Esempi di set di dati</span><span class="sxs-lookup"><span data-stu-id="67828-121">Dataset Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=187358)
