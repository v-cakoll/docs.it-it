---
title: 'Procedura: filtrare a livello di DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: c04be0bb955cff4bf796d14d45b39cac7ce4352d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354933"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="d654c-102">Procedura: filtrare a livello di DataContext</span><span class="sxs-lookup"><span data-stu-id="d654c-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="d654c-103">È possibile filtrare `EntitySets` al livello `DataContext`.</span><span class="sxs-lookup"><span data-stu-id="d654c-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="d654c-104">Tali filtri si applicano a tutte le query eseguite con quell'istanza di <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="d654c-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d654c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d654c-105">Example</span></span>  
 <span data-ttu-id="d654c-106">Nell'esempio seguente viene usato <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> per filtrare gli ordini precaricati per i clienti in base a `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="d654c-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="d654c-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d654c-107">See Also</span></span>  
 [<span data-ttu-id="d654c-108">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="d654c-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
