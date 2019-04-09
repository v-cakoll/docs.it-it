---
title: Restituire l'intersezione tra set di due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 07f48ab7ef1095ba80b1a955a4bd1ea602a75aa8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205908"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="7b533-102">Restituire l'intersezione tra set di due sequenze</span><span class="sxs-lookup"><span data-stu-id="7b533-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="7b533-103">Per restituire l'intersezione di due sequenze, usare l'operatore <xref:System.Linq.Queryable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="7b533-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b533-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b533-104">Example</span></span>  
 <span data-ttu-id="7b533-105">In questo esempio viene usato <xref:System.Linq.Queryable.Intersect%2A> per restituire una sequenza di tutti i paesi in cui sono presenti sia `Customers` che `Employees`.</span><span class="sxs-lookup"><span data-stu-id="7b533-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="7b533-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] l'operazione <xref:System.Linq.Queryable.Intersect%2A> è definita correttamente solo sui set,</span><span class="sxs-lookup"><span data-stu-id="7b533-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="7b533-107">mentre la semantica per i tipi multiset non è definita.</span><span class="sxs-lookup"><span data-stu-id="7b533-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b533-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b533-108">See also</span></span>

- [<span data-ttu-id="7b533-109">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="7b533-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="7b533-110">Conversione dell'operatore query standard</span><span class="sxs-lookup"><span data-stu-id="7b533-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
