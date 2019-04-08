---
title: Restituire il primo elemento di una sequenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: dca917b3c12b0f9923cc9ea34a2568c412a09831
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081833"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="de448-102">Restituire il primo elemento di una sequenza</span><span class="sxs-lookup"><span data-stu-id="de448-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="de448-103">Usare l'operatore <xref:System.Linq.Enumerable.First%2A> per restituire il primo elemento in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="de448-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="de448-104">Le query che usano <xref:System.Linq.Enumerable.First%2A> vengono eseguite immediatamente.</span><span class="sxs-lookup"><span data-stu-id="de448-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="de448-105">non supporta il <xref:System.Linq.Enumerable.Last%2A> operatore.</span><span class="sxs-lookup"><span data-stu-id="de448-105">does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de448-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="de448-106">Example</span></span>  
 <span data-ttu-id="de448-107">Nel codice seguente viene cercato il primo `Shipper` in una tabella:</span><span class="sxs-lookup"><span data-stu-id="de448-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="de448-108">Se si esegue questa query sul database di esempio Northwind, i risultati saranno</span><span class="sxs-lookup"><span data-stu-id="de448-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 `ID = 1, Company = Speedy Express`<span data-ttu-id="de448-109">.</span><span class="sxs-lookup"><span data-stu-id="de448-109">.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="de448-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="de448-110">Example</span></span>  
 <span data-ttu-id="de448-111">Nel codice seguente viene cercato il singolo `Customer` con `CustomerID` BONAP.</span><span class="sxs-lookup"><span data-stu-id="de448-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="de448-112">Se si esegue questa query sul database di esempio Northwind, i risultati saranno `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="de448-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="de448-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de448-113">See also</span></span>

- [<span data-ttu-id="de448-114">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="de448-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="de448-115">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="de448-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
