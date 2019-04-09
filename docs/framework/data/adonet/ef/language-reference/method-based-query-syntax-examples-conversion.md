---
title: 'Esempi di sintassi delle query basate su metodo: Conversione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: bf6c889fff2635cd50597e72151c46fbb4d9b97d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150618"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="ad17e-102">Esempi di sintassi delle query basate su metodo: Conversione</span><span class="sxs-lookup"><span data-stu-id="ad17e-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="ad17e-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> e <xref:System.Linq.Enumerable.ToList%2A> metodi per eseguire una query il [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) usando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="ad17e-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="ad17e-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ad17e-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ad17e-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="ad17e-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="ad17e-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="ad17e-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="ad17e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad17e-107">Example</span></span>  
 <span data-ttu-id="ad17e-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.ToArray%2A> per restituire immediatamente una matrice da una sequenza.</span><span class="sxs-lookup"><span data-stu-id="ad17e-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="ad17e-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="ad17e-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="ad17e-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad17e-110">Example</span></span>  
 <span data-ttu-id="ad17e-111">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.ToDictionary%2A> per restituire immediatamente un dizionario da una sequenza e un'espressione chiave correlata.</span><span class="sxs-lookup"><span data-stu-id="ad17e-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="ad17e-112">ToList</span><span class="sxs-lookup"><span data-stu-id="ad17e-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="ad17e-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad17e-113">Example</span></span>  
 <span data-ttu-id="ad17e-114">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.ToList%2A> per restituire immediatamente un oggetto <xref:System.Collections.Generic.List%601>, dove `T` è di tipo <xref:System.Data.DataRow>, da una sequenza.</span><span class="sxs-lookup"><span data-stu-id="ad17e-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="ad17e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad17e-115">See also</span></span>

- [<span data-ttu-id="ad17e-116">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ad17e-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
