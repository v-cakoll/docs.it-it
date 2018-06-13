---
title: 'Esempi di sintassi di query basate sul metodo: operatori sui set di dati (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 2c95125182a352d3cd2b0b4c51ffac3f74fff5a7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764814"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="ac4b7-102">Esempi di sintassi di query basate sul metodo: operatori sui set di dati (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ac4b7-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="ac4b7-103">Negli esempi in questo argomento viene illustrato come utilizzare il <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, e <xref:System.Linq.Enumerable.Union%2A> operatori per eseguire operazioni di confronto basate su valore su set di righe di dati.[ Il caricamento di dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) vedere [il confronto di DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) per ulteriori informazioni su <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="ac4b7-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) See [Comparing DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="ac4b7-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [durante il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="ac4b7-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="ac4b7-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ac4b7-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ac4b7-106">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="ac4b7-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="ac4b7-107">Per ulteriori informazioni, vedere [procedura: creare un LINQ to DataSet progetto In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="ac4b7-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="ac4b7-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="ac4b7-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="ac4b7-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac4b7-109">Example</span></span>  
 <span data-ttu-id="ac4b7-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Distinct%2A> per rimuovere elementi duplicati in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="ac4b7-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="ac4b7-111">Except</span><span class="sxs-lookup"><span data-stu-id="ac4b7-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="ac4b7-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac4b7-112">Example</span></span>  
 <span data-ttu-id="ac4b7-113">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Except%2A> per restituire i contatti presenti nella prima tabella ma non nella seconda.</span><span class="sxs-lookup"><span data-stu-id="ac4b7-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="ac4b7-114">Intersect</span><span class="sxs-lookup"><span data-stu-id="ac4b7-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="ac4b7-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac4b7-115">Example</span></span>  
 <span data-ttu-id="ac4b7-116">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Intersect%2A> per restituire i contatti presenti in entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="ac4b7-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="ac4b7-117">Unione</span><span class="sxs-lookup"><span data-stu-id="ac4b7-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="ac4b7-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac4b7-118">Example</span></span>  
 <span data-ttu-id="ac4b7-119">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Union%2A> per restituire contatti univoci presenti nelle due tabelle.</span><span class="sxs-lookup"><span data-stu-id="ac4b7-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="ac4b7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac4b7-120">See Also</span></span>  
 [<span data-ttu-id="ac4b7-121">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="ac4b7-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="ac4b7-122">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ac4b7-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="ac4b7-123">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="ac4b7-123">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
