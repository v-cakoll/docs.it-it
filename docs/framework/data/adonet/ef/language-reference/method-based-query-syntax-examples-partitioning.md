---
title: 'Esempi di sintassi di Query basate sul metodo: Partizionamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
ms.openlocfilehash: 2155d0cb9aa47e5940974db92077b51f8139e09d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536074"
---
# <a name="method-based-query-syntax-examples-partitioning"></a><span data-ttu-id="83b30-102">Esempi di sintassi di Query basate sul metodo: Partizionamento</span><span class="sxs-lookup"><span data-stu-id="83b30-102">Method-Based Query Syntax Examples: Partitioning</span></span>
<span data-ttu-id="83b30-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.Skip%2A>, e <xref:System.Linq.Enumerable.Take%2A> metodi per eseguire una query il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) usando la sintassi di espressione di query.</span><span class="sxs-lookup"><span data-stu-id="83b30-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="83b30-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="83b30-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="83b30-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="83b30-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="83b30-106">Skip</span><span class="sxs-lookup"><span data-stu-id="83b30-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="83b30-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="83b30-107">Example</span></span>  
 <span data-ttu-id="83b30-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Skip%2A> per ottenere tutti i contatti della tabella Contact ad eccezione dei primi cinque.</span><span class="sxs-lookup"><span data-stu-id="83b30-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="83b30-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="83b30-109">Example</span></span>  
 <span data-ttu-id="83b30-110">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Skip%2A> per ottenere tutti gli indirizzi di Seattle ad eccezione dei primi due.</span><span class="sxs-lookup"><span data-stu-id="83b30-110">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="83b30-111">Take</span><span class="sxs-lookup"><span data-stu-id="83b30-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="83b30-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="83b30-112">Example</span></span>  
 <span data-ttu-id="83b30-113">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Take%2A> per ottenere solo i primi cinque contatti della tabella Contact.</span><span class="sxs-lookup"><span data-stu-id="83b30-113">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="83b30-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="83b30-114">Example</span></span>  
 <span data-ttu-id="83b30-115">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Take%2A> per ottenere i primi tre indirizzi di Seattle.</span><span class="sxs-lookup"><span data-stu-id="83b30-115">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="83b30-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83b30-116">See also</span></span>
- [<span data-ttu-id="83b30-117">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="83b30-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
