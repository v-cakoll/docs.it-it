---
title: 'Esempi di sintassi delle espressioni di query: Operatori di elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 1b73e22e79c665763390561a1e48b2583ec6cd27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215508"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="4badd-102">Esempi di sintassi delle espressioni di query: Operatori di elemento</span><span class="sxs-lookup"><span data-stu-id="4badd-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="4badd-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.First%2A> metodo di query di [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) usando la sintassi di espressione di query.</span><span class="sxs-lookup"><span data-stu-id="4badd-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using the query expression syntax.</span></span> <span data-ttu-id="4badd-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4badd-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4badd-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="4badd-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="4badd-106">First</span><span class="sxs-lookup"><span data-stu-id="4badd-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="4badd-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4badd-107">Example</span></span>  
 <span data-ttu-id="4badd-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.First%2A> per restituire il primo contatto il cui nome è "Brooke".</span><span class="sxs-lookup"><span data-stu-id="4badd-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="4badd-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4badd-109">See also</span></span>

- [<span data-ttu-id="4badd-110">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4badd-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
