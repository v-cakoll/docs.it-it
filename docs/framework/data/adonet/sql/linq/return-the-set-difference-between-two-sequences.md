---
title: Restituire la differenza dei set tra due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 7edc60c7ab8510aadd9ac273529a88adeb41352a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124280"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="c5750-102">Restituire la differenza dei set tra due sequenze</span><span class="sxs-lookup"><span data-stu-id="c5750-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="c5750-103">Per restituire la differenza dei set tra due sequenze, usare l'operatore <xref:System.Linq.Queryable.Except%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5750-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5750-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5750-104">Example</span></span>  
 <span data-ttu-id="c5750-105">In questo esempio viene usato <xref:System.Linq.Queryable.Except%2A> per restituire una sequenza di tutti i paesi in cui sono presenti `Customers` ma non `Employees`.</span><span class="sxs-lookup"><span data-stu-id="c5750-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="c5750-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] l'operazione <xref:System.Linq.Queryable.Except%2A> è definita correttamente solo sui set,</span><span class="sxs-lookup"><span data-stu-id="c5750-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="c5750-107">mentre la semantica per i tipi multiset non è definita.</span><span class="sxs-lookup"><span data-stu-id="c5750-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5750-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5750-108">See also</span></span>

- [<span data-ttu-id="c5750-109">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="c5750-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="c5750-110">Conversione dell'operatore query standard</span><span class="sxs-lookup"><span data-stu-id="c5750-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
