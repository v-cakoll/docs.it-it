---
title: Restituire la differenza dei set tra due sequenze
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 92513ed33e2afb785edbdd462ba7bc14923aa6b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781153"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="c0545-102">Restituire la differenza dei set tra due sequenze</span><span class="sxs-lookup"><span data-stu-id="c0545-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="c0545-103">Per restituire la differenza dei set tra due sequenze, usare l'operatore <xref:System.Linq.Queryable.Except%2A>.</span><span class="sxs-lookup"><span data-stu-id="c0545-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0545-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0545-104">Example</span></span>  
 <span data-ttu-id="c0545-105">In questo esempio <xref:System.Linq.Queryable.Except%2A> viene usato per restituire una sequenza di tutti i paesi/ `Customers` aree in cui Live, `Employees` ma in cui non è attivo.</span><span class="sxs-lookup"><span data-stu-id="c0545-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="c0545-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] l'operazione <xref:System.Linq.Queryable.Except%2A> è definita correttamente solo sui set,</span><span class="sxs-lookup"><span data-stu-id="c0545-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="c0545-107">mentre la semantica per i tipi multiset non è definita.</span><span class="sxs-lookup"><span data-stu-id="c0545-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0545-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0545-108">See also</span></span>

- [<span data-ttu-id="c0545-109">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="c0545-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="c0545-110">Conversione dell'operatore query standard</span><span class="sxs-lookup"><span data-stu-id="c0545-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
