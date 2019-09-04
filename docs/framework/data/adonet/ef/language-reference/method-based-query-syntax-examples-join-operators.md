---
title: 'Esempi di sintassi delle query basate su metodo: Operatori di join'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: 2f26f937901debd27cb936d1f642e0a5149b167a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250127"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="3c328-102">Esempi di sintassi delle query basate su metodo: Operatori di join</span><span class="sxs-lookup"><span data-stu-id="3c328-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="3c328-103">Negli esempi di questo argomento viene illustrato come utilizzare i <xref:System.Linq.Enumerable.Join%2A> metodi <xref:System.Linq.Enumerable.GroupJoin%2A> e per eseguire query sul [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) utilizzando la sintassi delle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="3c328-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="3c328-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3c328-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3c328-105">Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`</span><span class="sxs-lookup"><span data-stu-id="3c328-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="3c328-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="3c328-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="3c328-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c328-107">Example</span></span>  
 <span data-ttu-id="3c328-108">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle SalesOrderHeader e SalesOrderDetail per trovare il numero di ordini per cliente.</span><span class="sxs-lookup"><span data-stu-id="3c328-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="3c328-109">Questa operazione equivale a un left outer join, che restituisce ogni elemento della prima origine dati (a sinistra), anche se nell'altra origine dati non sono presenti elementi correlati.</span><span class="sxs-lookup"><span data-stu-id="3c328-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="3c328-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c328-110">Example</span></span>  
 <span data-ttu-id="3c328-111">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle Contact e SalesOrderHeader per trovare il numero di ordini per contatto.</span><span class="sxs-lookup"><span data-stu-id="3c328-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="3c328-112">Vengono visualizzati l'ID e il numero di ordini per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="3c328-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="3c328-113">Unisci</span><span class="sxs-lookup"><span data-stu-id="3c328-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="3c328-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c328-114">Example</span></span>  
 <span data-ttu-id="3c328-115">Nell'esempio seguente viene eseguito un join sulle tabelle Contact e SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="3c328-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="3c328-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c328-116">Example</span></span>  
 <span data-ttu-id="3c328-117">Nell'esempio seguente viene eseguito un join sulle tabelle Contact e SalesOrderHeader, raggruppando i risultati in base all'ID contatto.</span><span class="sxs-lookup"><span data-stu-id="3c328-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="3c328-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c328-118">See also</span></span>

- [<span data-ttu-id="3c328-119">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="3c328-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
