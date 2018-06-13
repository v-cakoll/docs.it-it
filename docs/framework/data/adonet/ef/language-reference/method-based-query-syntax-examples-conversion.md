---
title: 'Esempi di sintassi di query basate sul metodo: conversione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: 6ca770f067a3086f021cd87e226f66716b39e595
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763254"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="79f21-102">Esempi di sintassi di query basate sul metodo: conversione</span><span class="sxs-lookup"><span data-stu-id="79f21-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="79f21-103">Negli esempi in questo argomento viene illustrato come utilizzare il <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> e <xref:System.Linq.Enumerable.ToList%2A> metodi per eseguire una query di [modello Sales di AdventureWorks](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) utilizzando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="79f21-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="79f21-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="79f21-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="79f21-105">Gli esempi in questo argomento usano seguenti `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="79f21-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="79f21-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="79f21-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="79f21-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="79f21-107">Example</span></span>  
 <span data-ttu-id="79f21-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.ToArray%2A> per restituire immediatamente una matrice da una sequenza.</span><span class="sxs-lookup"><span data-stu-id="79f21-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="79f21-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="79f21-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="79f21-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="79f21-110">Example</span></span>  
 <span data-ttu-id="79f21-111">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.ToDictionary%2A> per restituire immediatamente un dizionario da una sequenza e un'espressione chiave correlata.</span><span class="sxs-lookup"><span data-stu-id="79f21-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="79f21-112">ToList</span><span class="sxs-lookup"><span data-stu-id="79f21-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="79f21-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="79f21-113">Example</span></span>  
 <span data-ttu-id="79f21-114">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.ToList%2A> per restituire immediatamente un oggetto <xref:System.Collections.Generic.List%601>, dove `T` è di tipo <xref:System.Data.DataRow>, da una sequenza.</span><span class="sxs-lookup"><span data-stu-id="79f21-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="79f21-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79f21-115">See Also</span></span>  
 [<span data-ttu-id="79f21-116">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="79f21-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
