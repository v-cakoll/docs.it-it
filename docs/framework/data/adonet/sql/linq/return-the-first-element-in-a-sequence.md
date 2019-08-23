---
title: Restituire il primo elemento di una sequenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 39cf9270b08fce64590fef418bb428c5a781b0e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963803"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="c94ee-102">Restituire il primo elemento di una sequenza</span><span class="sxs-lookup"><span data-stu-id="c94ee-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="c94ee-103">Usare l'operatore <xref:System.Linq.Enumerable.First%2A> per restituire il primo elemento in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="c94ee-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="c94ee-104">Le query che usano <xref:System.Linq.Enumerable.First%2A> vengono eseguite immediatamente.</span><span class="sxs-lookup"><span data-stu-id="c94ee-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="c94ee-105">non supporta l'operatore <xref:System.Linq.Enumerable.Last%2A>.</span><span class="sxs-lookup"><span data-stu-id="c94ee-105">does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c94ee-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c94ee-106">Example</span></span>  
 <span data-ttu-id="c94ee-107">Nel codice seguente viene cercato il primo `Shipper` in una tabella:</span><span class="sxs-lookup"><span data-stu-id="c94ee-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="c94ee-108">Se si esegue questa query sul database di esempio Northwind, i risultati saranno</span><span class="sxs-lookup"><span data-stu-id="c94ee-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="c94ee-109">[https://login.microsoftonline.com/consumers/](`ID = 1, Company = Speedy Express`).</span><span class="sxs-lookup"><span data-stu-id="c94ee-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="c94ee-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="c94ee-110">Example</span></span>  
 <span data-ttu-id="c94ee-111">Nel codice seguente viene cercato il singolo `Customer` con `CustomerID` BONAP.</span><span class="sxs-lookup"><span data-stu-id="c94ee-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="c94ee-112">Se si esegue questa query sul database di esempio Northwind, i risultati saranno `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="c94ee-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="c94ee-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c94ee-113">See also</span></span>

- [<span data-ttu-id="c94ee-114">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="c94ee-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="c94ee-115">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="c94ee-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
