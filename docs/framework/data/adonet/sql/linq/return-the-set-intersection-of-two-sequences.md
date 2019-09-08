---
title: Restituire l'intersezione tra set di due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 944d0b2efe1e74f901a493d1c3202d0f180d599d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792709"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="d9f4e-102">Restituire l'intersezione tra set di due sequenze</span><span class="sxs-lookup"><span data-stu-id="d9f4e-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="d9f4e-103">Per restituire l'intersezione di due sequenze, usare l'operatore <xref:System.Linq.Queryable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="d9f4e-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9f4e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9f4e-104">Example</span></span>  
 <span data-ttu-id="d9f4e-105">In questo esempio <xref:System.Linq.Queryable.Intersect%2A> viene usato per restituire una sequenza di tutti i paesi/aree `Customers` in `Employees` cui sono presenti sia che Live.</span><span class="sxs-lookup"><span data-stu-id="d9f4e-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="d9f4e-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] l'operazione <xref:System.Linq.Queryable.Intersect%2A> è definita correttamente solo sui set,</span><span class="sxs-lookup"><span data-stu-id="d9f4e-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="d9f4e-107">mentre la semantica per i tipi multiset non è definita.</span><span class="sxs-lookup"><span data-stu-id="d9f4e-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f4e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9f4e-108">See also</span></span>

- [<span data-ttu-id="d9f4e-109">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="d9f4e-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="d9f4e-110">Conversione dell'operatore query standard</span><span class="sxs-lookup"><span data-stu-id="d9f4e-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
