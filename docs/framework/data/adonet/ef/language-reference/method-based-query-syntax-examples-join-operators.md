---
title: 'Esempi di sintassi di query basate sul metodo: operatori di join'
description: Usare questi esempi per apprendere come usare i metodi join e GroupJoin per eseguire una query su un modello usando la sintassi delle query basate su metodo in LINQ to Entities.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: 3b1445b39bdcd9a9b4d0672be0598233319cb85d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286831"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="91cbf-103">Esempi di sintassi di query basate sul metodo: operatori di join</span><span class="sxs-lookup"><span data-stu-id="91cbf-103">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="91cbf-104">Negli esempi di questo argomento viene illustrato come utilizzare i <xref:System.Linq.Enumerable.Join%2A> <xref:System.Linq.Enumerable.GroupJoin%2A> metodi e per eseguire query sul [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) utilizzando la sintassi delle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="91cbf-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="91cbf-105">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="91cbf-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="91cbf-106">Negli esempi di questo argomento vengono utilizzate le `using` / `Imports` istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="91cbf-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="91cbf-107">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="91cbf-107">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="91cbf-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="91cbf-108">Example</span></span>  
 <span data-ttu-id="91cbf-109">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle SalesOrderHeader e SalesOrderDetail per trovare il numero di ordini per cliente.</span><span class="sxs-lookup"><span data-stu-id="91cbf-109">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="91cbf-110">Questa operazione equivale a un left outer join, che restituisce ogni elemento della prima origine dati (a sinistra), anche se nell'altra origine dati non sono presenti elementi correlati.</span><span class="sxs-lookup"><span data-stu-id="91cbf-110">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="91cbf-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="91cbf-111">Example</span></span>  
 <span data-ttu-id="91cbf-112">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle Contact e SalesOrderHeader per trovare il numero di ordini per contatto.</span><span class="sxs-lookup"><span data-stu-id="91cbf-112">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="91cbf-113">Vengono visualizzati l'ID e il numero di ordini per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="91cbf-113">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="91cbf-114">Join</span><span class="sxs-lookup"><span data-stu-id="91cbf-114">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="91cbf-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="91cbf-115">Example</span></span>  
 <span data-ttu-id="91cbf-116">Nell'esempio seguente viene eseguito un join sulle tabelle Contact e SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="91cbf-116">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="91cbf-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="91cbf-117">Example</span></span>  
 <span data-ttu-id="91cbf-118">Nell'esempio seguente viene eseguito un join sulle tabelle Contact e SalesOrderHeader, raggruppando i risultati in base all'ID contatto.</span><span class="sxs-lookup"><span data-stu-id="91cbf-118">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="91cbf-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91cbf-119">See also</span></span>

- [<span data-ttu-id="91cbf-120">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="91cbf-120">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
