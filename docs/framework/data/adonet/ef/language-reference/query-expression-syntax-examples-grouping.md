---
title: 'Esempi di sintassi delle espressioni di query: Raggruppamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: 0a4aa57ba709852c30223598b9d1af146eaf6013
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211998"
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="f5c0c-102">Esempi di sintassi delle espressioni di query: Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="f5c0c-102">Query Expression Syntax Examples: Grouping</span></span>
<span data-ttu-id="f5c0c-103">Gli esempi in questo argomento illustrano come usare il `GroupBy` metodo di query di [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) usando la sintassi di espressione di query.</span><span class="sxs-lookup"><span data-stu-id="f5c0c-103">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="f5c0c-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f5c0c-104">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f5c0c-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="f5c0c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="f5c0c-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5c0c-106">Example</span></span>  
 <span data-ttu-id="f5c0c-107">Nell'esempio seguente vengono restituiti oggetti `Address` raggruppati in base al codice postale.</span><span class="sxs-lookup"><span data-stu-id="f5c0c-107">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="f5c0c-108">I risultati vengono proiettati in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="f5c0c-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="f5c0c-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5c0c-109">Example</span></span>  
 <span data-ttu-id="f5c0c-110">Nell'esempio seguente vengono restituiti oggetti `Contact` raggruppati in base alla prima lettera del cognome del contatto.</span><span class="sxs-lookup"><span data-stu-id="f5c0c-110">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="f5c0c-111">I risultati sono anche ordinati in base alla prima lettera del cognome e proiettati in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="f5c0c-111">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="f5c0c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5c0c-112">Example</span></span>  
 <span data-ttu-id="f5c0c-113">Nell'esempio seguente vengono restituiti oggetti `SalesOrderHeader` raggruppati in base all'ID cliente.</span><span class="sxs-lookup"><span data-stu-id="f5c0c-113">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="f5c0c-114">Viene restituito anche il numero di vendite per ogni cliente.</span><span class="sxs-lookup"><span data-stu-id="f5c0c-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="f5c0c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5c0c-115">See also</span></span>

- [<span data-ttu-id="f5c0c-116">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="f5c0c-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
