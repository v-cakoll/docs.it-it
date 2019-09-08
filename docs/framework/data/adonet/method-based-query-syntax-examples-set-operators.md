---
title: 'Esempi di sintassi delle query basate su metodo: Operatori sui set (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 481c0ed7e39b8f958ccdae01e4589d54b3ff2446
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783584"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="8a507-102">Esempi di sintassi delle query basate su metodo: Operatori sui set (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="8a507-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="8a507-103">Negli esempi di questo argomento viene illustrato come utilizzare gli <xref:System.Linq.Enumerable.Distinct%2A>operatori <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, e <xref:System.Linq.Enumerable.Union%2A> per eseguire operazioni di confronto basate su valore su set di righe di dati.[ Caricamento di dati in un set di dati](loading-data-into-a-dataset.md) vedere confronto di oggetti [DataRows](comparing-datarows-linq-to-dataset.md) per ulteriori informazioni su <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="8a507-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](loading-data-into-a-dataset.md) See [Comparing DataRows](comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="8a507-104">Il `FillDataSet` metodo utilizzato in questi esempi viene specificato nel [caricamento di dati in un DataSet](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="8a507-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="8a507-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8a507-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8a507-106">Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`</span><span class="sxs-lookup"><span data-stu-id="8a507-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="8a507-107">Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet in Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="8a507-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="8a507-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="8a507-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="8a507-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a507-109">Example</span></span>  
 <span data-ttu-id="8a507-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Distinct%2A> per rimuovere elementi duplicati in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="8a507-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="8a507-111">Eccezione</span><span class="sxs-lookup"><span data-stu-id="8a507-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="8a507-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a507-112">Example</span></span>  
 <span data-ttu-id="8a507-113">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Except%2A> per restituire i contatti presenti nella prima tabella ma non nella seconda.</span><span class="sxs-lookup"><span data-stu-id="8a507-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="8a507-114">Interseca</span><span class="sxs-lookup"><span data-stu-id="8a507-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="8a507-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a507-115">Example</span></span>  
 <span data-ttu-id="8a507-116">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Intersect%2A> per restituire i contatti presenti in entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="8a507-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="8a507-117">Unione</span><span class="sxs-lookup"><span data-stu-id="8a507-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="8a507-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a507-118">Example</span></span>  
 <span data-ttu-id="8a507-119">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Union%2A> per restituire contatti univoci presenti nelle due tabelle.</span><span class="sxs-lookup"><span data-stu-id="8a507-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="8a507-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a507-120">See also</span></span>

- [<span data-ttu-id="8a507-121">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="8a507-121">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="8a507-122">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="8a507-122">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="8a507-123">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="8a507-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="8a507-124">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a507-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
