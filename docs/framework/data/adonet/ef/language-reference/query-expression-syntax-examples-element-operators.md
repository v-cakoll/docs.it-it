---
title: 'Esempi di sintassi di espressione di query: operatori di elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 36823b02d581b47493950b6393bda323b2e8f9b7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749184"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="afd4c-102">Esempi di sintassi di espressione di query: operatori di elemento</span><span class="sxs-lookup"><span data-stu-id="afd4c-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="afd4c-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.First%2A> metodo di query di [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) usando la sintassi di espressione di query.</span><span class="sxs-lookup"><span data-stu-id="afd4c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using the query expression syntax.</span></span> <span data-ttu-id="afd4c-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="afd4c-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="afd4c-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="afd4c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="afd4c-106">First</span><span class="sxs-lookup"><span data-stu-id="afd4c-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="afd4c-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="afd4c-107">Example</span></span>  
 <span data-ttu-id="afd4c-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.First%2A> per restituire il primo contatto il cui nome è "Brooke".</span><span class="sxs-lookup"><span data-stu-id="afd4c-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="afd4c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afd4c-109">See Also</span></span>  
 [<span data-ttu-id="afd4c-110">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="afd4c-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
