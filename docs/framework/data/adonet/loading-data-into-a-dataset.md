---
title: Caricamento di dati in un dataset
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
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 471a13b5d209def227bf8bc57b1551550b76a0c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="c60ec-102">Caricamento di dati in un dataset</span><span class="sxs-lookup"><span data-stu-id="c60ec-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="c60ec-103">Per poter eseguire query su un oggetto <xref:System.Data.DataSet> con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], è prima necessario popolarlo.</span><span class="sxs-lookup"><span data-stu-id="c60ec-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="c60ec-104">Sono disponibili diversi modi per popolare <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c60ec-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c60ec-105">Ad esempio, è possibile utilizzare [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] per eseguire query sul database e caricare i risultati nel <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c60ec-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c60ec-106">Per altre informazioni, vedere [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="c60ec-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="c60ec-107">Per caricare i dati in <xref:System.Data.DataSet>, è inoltre usare la classe <xref:System.Data.Common.DataAdapter> per recuperare i dati dal database,</span><span class="sxs-lookup"><span data-stu-id="c60ec-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="c60ec-108">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c60ec-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c60ec-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c60ec-109">Example</span></span>  
 <span data-ttu-id="c60ec-110">In questo esempio viene usato un oggetto <xref:System.Data.Common.DataAdapter> per eseguire una query sul database AdventureWorks relativa alle informazioni sulle vendite dell'anno 2002. I risultati vengono quindi caricati in un oggetto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c60ec-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c60ec-111">Dopo aver popolato <xref:System.Data.DataSet>, è possibile scrivere query da eseguire su di esso con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c60ec-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="c60ec-112">Il `FillDataSet` metodo in questo esempio viene utilizzato nella query di esempio in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="c60ec-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="c60ec-113">Per ulteriori informazioni, vedere [query su DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="c60ec-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="c60ec-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c60ec-114">See Also</span></span>  
 [<span data-ttu-id="c60ec-115">Panoramica di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="c60ec-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)  
 [<span data-ttu-id="c60ec-116">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="c60ec-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="c60ec-117">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="c60ec-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
