---
title: 'Esempi di sintassi delle query basate su metodo: Partizionamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
ms.openlocfilehash: eaf98dc21499817446efca2f10edf7faea15761c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760519"
---
# <a name="method-based-query-syntax-examples-partitioning"></a><span data-ttu-id="8d4b4-102">Esempi di sintassi delle query basate su metodo: Partizionamento</span><span class="sxs-lookup"><span data-stu-id="8d4b4-102">Method-Based Query Syntax Examples: Partitioning</span></span>
<span data-ttu-id="8d4b4-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.Skip%2A>, e <xref:System.Linq.Enumerable.Take%2A> metodi per eseguire una query il [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) usando la sintassi di espressione di query.</span><span class="sxs-lookup"><span data-stu-id="8d4b4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="8d4b4-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8d4b4-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8d4b4-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="8d4b4-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="8d4b4-106">Skip</span><span class="sxs-lookup"><span data-stu-id="8d4b4-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="8d4b4-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d4b4-107">Example</span></span>  
 <span data-ttu-id="8d4b4-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Skip%2A> per ottenere tutti i contatti della tabella Contact ad eccezione dei primi cinque.</span><span class="sxs-lookup"><span data-stu-id="8d4b4-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="8d4b4-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d4b4-109">Example</span></span>  
 <span data-ttu-id="8d4b4-110">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Skip%2A> per ottenere tutti gli indirizzi di Seattle ad eccezione dei primi due.</span><span class="sxs-lookup"><span data-stu-id="8d4b4-110">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="8d4b4-111">Take</span><span class="sxs-lookup"><span data-stu-id="8d4b4-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="8d4b4-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d4b4-112">Example</span></span>  
 <span data-ttu-id="8d4b4-113">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Take%2A> per ottenere solo i primi cinque contatti della tabella Contact.</span><span class="sxs-lookup"><span data-stu-id="8d4b4-113">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="8d4b4-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d4b4-114">Example</span></span>  
 <span data-ttu-id="8d4b4-115">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Take%2A> per ottenere i primi tre indirizzi di Seattle.</span><span class="sxs-lookup"><span data-stu-id="8d4b4-115">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="8d4b4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d4b4-116">See also</span></span>

- [<span data-ttu-id="8d4b4-117">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8d4b4-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
