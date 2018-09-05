---
title: 'Esempi di sintassi di query basate sul metodo: operatori di join'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: ee753f5101f525fc7d86a91f2aa3545d257a2be5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43740283"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="6fea9-102">Esempi di sintassi di query basate sul metodo: operatori di join</span><span class="sxs-lookup"><span data-stu-id="6fea9-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="6fea9-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.Join%2A> e <xref:System.Linq.Enumerable.GroupJoin%2A> metodi per eseguire una query il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) usando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="6fea9-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="6fea9-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6fea9-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6fea9-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="6fea9-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="6fea9-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="6fea9-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="6fea9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fea9-107">Example</span></span>  
 <span data-ttu-id="6fea9-108">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle SalesOrderHeader e SalesOrderDetail per trovare il numero di ordini per cliente.</span><span class="sxs-lookup"><span data-stu-id="6fea9-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="6fea9-109">Questa operazione equivale a un left outer join, che restituisce ogni elemento della prima origine dati (a sinistra), anche se nell'altra origine dati non sono presenti elementi correlati.</span><span class="sxs-lookup"><span data-stu-id="6fea9-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="6fea9-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fea9-110">Example</span></span>  
 <span data-ttu-id="6fea9-111">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle Contact e SalesOrderHeader per trovare il numero di ordini per contatto.</span><span class="sxs-lookup"><span data-stu-id="6fea9-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="6fea9-112">Vengono visualizzati l'ID e il numero di ordini per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="6fea9-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="6fea9-113">Join</span><span class="sxs-lookup"><span data-stu-id="6fea9-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="6fea9-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fea9-114">Example</span></span>  
 <span data-ttu-id="6fea9-115">Nell'esempio seguente viene eseguito un join sulle tabelle Contact e SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="6fea9-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="6fea9-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="6fea9-116">Example</span></span>  
 <span data-ttu-id="6fea9-117">Nell'esempio seguente viene eseguito un join sulle tabelle Contact e SalesOrderHeader, raggruppando i risultati in base all'ID contatto.</span><span class="sxs-lookup"><span data-stu-id="6fea9-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="6fea9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fea9-118">See Also</span></span>  
 [<span data-ttu-id="6fea9-119">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="6fea9-119">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
