---
title: Caricamento di dati in un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 53f0f5a589a0033c9612f0465dff090ab04e3fc4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794952"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="772f7-102">Caricamento di dati in un dataset</span><span class="sxs-lookup"><span data-stu-id="772f7-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="772f7-103">Prima <xref:System.Data.DataSet> di poter eseguire una query su di esso con LINQ to DataSet, è necessario innanzitutto popolare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="772f7-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="772f7-104">Sono disponibili diversi modi per popolare <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="772f7-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="772f7-105">Ad esempio, è possibile utilizzare [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] per eseguire una query sul database e caricare i risultati <xref:System.Data.DataSet>in.</span><span class="sxs-lookup"><span data-stu-id="772f7-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="772f7-106">Per altre informazioni, vedere [LINQ to SQL](./sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="772f7-106">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="772f7-107">Per caricare i dati in <xref:System.Data.DataSet>, è inoltre usare la classe <xref:System.Data.Common.DataAdapter> per recuperare i dati dal database,</span><span class="sxs-lookup"><span data-stu-id="772f7-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="772f7-108">Questa procedura è illustrata nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="772f7-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="772f7-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="772f7-109">Example</span></span>  
 <span data-ttu-id="772f7-110">In questo esempio viene usato un oggetto <xref:System.Data.Common.DataAdapter> per eseguire una query sul database AdventureWorks relativa alle informazioni sulle vendite dell'anno 2002. I risultati vengono quindi caricati in un oggetto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="772f7-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="772f7-111"><xref:System.Data.DataSet> Una volta popolato, è possibile scrivere query su di esso utilizzando LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="772f7-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="772f7-112">Il `FillDataSet` metodo in questo esempio viene usato nelle query di esempio in [LINQ to DataSet esempi](linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="772f7-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="772f7-113">Per ulteriori informazioni, vedere [esecuzione di query sui set](querying-datasets-linq-to-dataset.md)di dati.</span><span class="sxs-lookup"><span data-stu-id="772f7-113">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="772f7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="772f7-114">See also</span></span>

- [<span data-ttu-id="772f7-115">Panoramica di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="772f7-115">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="772f7-116">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="772f7-116">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="772f7-117">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="772f7-117">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
