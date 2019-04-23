---
title: 'Esempi di sintassi delle query basate su metodo: Operatori di conversione (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: e50707155d509b8300966cbba8ee885492e5b815
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108641"
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a><span data-ttu-id="63ab1-102">Esempi di sintassi delle query basate su metodo: Operatori di conversione (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="63ab1-102">Method-Based Query Syntax Examples: Conversion Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="63ab1-103">Negli esempi di questo argomento viene illustrato l'uso dei metodi <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> e <xref:System.Linq.Enumerable.ToList%2A> per eseguire immediatamente un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="63ab1-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 <span data-ttu-id="63ab1-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="63ab1-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="63ab1-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="63ab1-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="63ab1-106">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="63ab1-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="63ab1-107">Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="63ab1-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="toarray"></a><span data-ttu-id="63ab1-108">ToArray</span><span class="sxs-lookup"><span data-stu-id="63ab1-108">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="63ab1-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="63ab1-109">Example</span></span>  
 <span data-ttu-id="63ab1-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.ToArray%2A> per valutare immediatamente una sequenza in una matrice.</span><span class="sxs-lookup"><span data-stu-id="63ab1-110">This example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="63ab1-111">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="63ab1-111">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="63ab1-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="63ab1-112">Example</span></span>  
 <span data-ttu-id="63ab1-113">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.ToDictionary%2A> per valutare immediatamente una sequenza e un'espressione chiave correlata in un dizionario.</span><span class="sxs-lookup"><span data-stu-id="63ab1-113">This example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="63ab1-114">ToList</span><span class="sxs-lookup"><span data-stu-id="63ab1-114">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="63ab1-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="63ab1-115">Example</span></span>  
 <span data-ttu-id="63ab1-116">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.ToList%2A> per valutare immediatamente una sequenza in un oggetto <xref:System.Collections.Generic.List%601>, dove `T` è di tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="63ab1-116">This example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="63ab1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63ab1-117">See also</span></span>

- [<span data-ttu-id="63ab1-118">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="63ab1-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="63ab1-119">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="63ab1-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="63ab1-120">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="63ab1-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="63ab1-121">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63ab1-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
