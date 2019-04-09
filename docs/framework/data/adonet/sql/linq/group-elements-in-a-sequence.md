---
title: Raggruppare elementi in una sequenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d50c8b4-f550-4775-bbb6-eab6e874cb43
ms.openlocfilehash: 5d812ae9b5fd0a796588d3366b8546ef84c982c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089916"
---
# <a name="group-elements-in-a-sequence"></a><span data-ttu-id="e8ad2-102">Raggruppare elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="e8ad2-102">Group Elements in a Sequence</span></span>
<span data-ttu-id="e8ad2-103">L'operatore <xref:System.Linq.Enumerable.GroupBy%2A> consente di raggruppare gli elementi di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-103">The <xref:System.Linq.Enumerable.GroupBy%2A> operator groups the elements of a sequence.</span></span> <span data-ttu-id="e8ad2-104">Negli esempi riportati di seguito viene usato il database Northwind.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-104">The following examples use the Northwind database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8ad2-105">I valori di colonna null nelle query <xref:System.Linq.Enumerable.GroupBy%2A> possono a volte generare una <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-105">Null column values in <xref:System.Linq.Enumerable.GroupBy%2A> queries can sometimes throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="e8ad2-106">Per altre informazioni, vedere la sezione "GroupBy InvalidOperationException" del [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="e8ad2-106">For more information, see the "GroupBy InvalidOperationException" section of [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8ad2-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-107">Example</span></span>  
 <span data-ttu-id="e8ad2-108">Nell'esempio riportato di seguito `Products` viene partizionato per `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-108">The following example partitions `Products` by `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#27](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#27)]
 [!code-vb[DLinqQueryExamples#27](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#27)]  
  
## <a name="example"></a><span data-ttu-id="e8ad2-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-109">Example</span></span>  
 <span data-ttu-id="e8ad2-110">Nell'esempio riportato di seguito viene usata <xref:System.Linq.Enumerable.Max%2A> per trovare il prezzo unitario massimo per ogni `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-110">The following example uses <xref:System.Linq.Enumerable.Max%2A> to find the maximum unit price for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#28](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#28)]
 [!code-vb[DLinqQueryExamples#28](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#28)]  
  
## <a name="example"></a><span data-ttu-id="e8ad2-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-111">Example</span></span>  
 <span data-ttu-id="e8ad2-112">Nell'esempio riportato di seguito viene usata la funzione Average per trovare la media di `UnitPrice` per ogni `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-112">The following example uses Average to find the average `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#29](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#29)]
 [!code-vb[DLinqQueryExamples#29](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="e8ad2-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-113">Example</span></span>  
 <span data-ttu-id="e8ad2-114">Nell'esempio riportato di seguito viene usata <xref:System.Linq.Queryable.Sum%2A> per trovare il totale di `UnitPrice` per ogni `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-114">The following example uses <xref:System.Linq.Queryable.Sum%2A> to find the total `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#30](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#30)]
 [!code-vb[DLinqQueryExamples#30](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="e8ad2-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-115">Example</span></span>  
 <span data-ttu-id="e8ad2-116">Nell'esempio riportato di seguito viene usata <xref:System.Linq.Queryable.Count%2A> per trovare il numero di `Products` rimossi in ogni `CategoryID`.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-116">The following example uses <xref:System.Linq.Queryable.Count%2A> to find the number of discontinued `Products` in each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#31](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#31)]
 [!code-vb[DLinqQueryExamples#31](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="e8ad2-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-117">Example</span></span>  
 <span data-ttu-id="e8ad2-118">Negli esempi riportati di seguito viene usata la clausola `where` seguente per trovare tutte le categorie con almeno 10 prodotti.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-118">The following example uses a following `where` clause to find all categories that have at least 10 products.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#32](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#32)]
 [!code-vb[DLinqQueryExamples#32](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#32)]  
  
## <a name="example"></a><span data-ttu-id="e8ad2-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-119">Example</span></span>  
 <span data-ttu-id="e8ad2-120">Nell'esempio riportato di seguito i prodotti vengono raggruppati per `CategoryID` e `SupplierID`.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-120">The following example groups products by `CategoryID` and `SupplierID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#33](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#33)]
 [!code-vb[DLinqQueryExamples#33](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#33)]  
  
## <a name="example"></a><span data-ttu-id="e8ad2-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-121">Example</span></span>  
 <span data-ttu-id="e8ad2-122">Nell'esempio riportato di seguito vengono restituite due sequenze di prodotti.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-122">The following example returns two sequences of products.</span></span> <span data-ttu-id="e8ad2-123">La prima sequenza contiene prodotti con prezzo unitario minore o uguale a 10.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-123">The first sequence contains products with unit price less than or equal to 10.</span></span> <span data-ttu-id="e8ad2-124">La seconda sequenza contiene prodotti con prezzo unitario maggiore di 10.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-124">The second sequence contains products with unit price greater than 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#34](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#34)]
 [!code-vb[DLinqQueryExamples#34](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#34)]  
  
## <a name="example"></a><span data-ttu-id="e8ad2-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-125">Example</span></span>  
 <span data-ttu-id="e8ad2-126">L'operatore <xref:System.Linq.Queryable.GroupBy%2A> può accettare solo un argomento a chiave singola.</span><span class="sxs-lookup"><span data-stu-id="e8ad2-126">The <xref:System.Linq.Queryable.GroupBy%2A> operator can take only a single key argument.</span></span> <span data-ttu-id="e8ad2-127">Se è necessario raggruppare in base a più chiavi, è necessario creare un tipo anonimo, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e8ad2-127">If you need to group by more than one key, you must create an anonymous type, as in the following example:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#35](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#35)]
 [!code-vb[DLinqQueryExamples#35](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#35)]  
  
## <a name="see-also"></a><span data-ttu-id="e8ad2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8ad2-128">See also</span></span>

- [<span data-ttu-id="e8ad2-129">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="e8ad2-129">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="e8ad2-130">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="e8ad2-130">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
