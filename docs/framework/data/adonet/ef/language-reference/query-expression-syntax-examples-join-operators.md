---
title: 'Esempi di sintassi di espressione di query: Operatori di join'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: 3384eb98c8e58563f879b55054077ef801c0ebc7
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827968"
---
# <a name="query-expression-syntax-examples-join-operators"></a><span data-ttu-id="419d4-102">Esempi di sintassi di espressione di query: Operatori di join</span><span class="sxs-lookup"><span data-stu-id="419d4-102">Query Expression Syntax Examples: Join Operators</span></span>
<span data-ttu-id="419d4-103">La creazione di un join è un'operazione importante in query destinate a origini dati che non presentano relazioni esplorabili tra loro, ad esempio le tabelle di database relazionali.</span><span class="sxs-lookup"><span data-stu-id="419d4-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="419d4-104">Per join di due origini dati si intende l'associazione degli oggetti di un'origine dati con oggetti che condividono un attributo comune nell'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="419d4-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="419d4-105">Per altre informazioni, vedere [panoramica degli operatori Query Standard](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="419d4-105">For more information, see [Standard Query Operators Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span></span>  
  
 <span data-ttu-id="419d4-106">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.GroupJoin%2A> e <xref:System.Linq.Enumerable.Join%2A> metodi per eseguire una query il [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) usando la sintassi di espressione di query.</span><span class="sxs-lookup"><span data-stu-id="419d4-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="419d4-107">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="419d4-107">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="419d4-108">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="419d4-108">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="419d4-109">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="419d4-109">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="419d4-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="419d4-110">Example</span></span>  
 <span data-ttu-id="419d4-111">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle SalesOrderHeader e SalesOrderDetail per trovare il numero di ordini per cliente.</span><span class="sxs-lookup"><span data-stu-id="419d4-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="419d4-112">Questa operazione equivale a un left outer join, che restituisce ogni elemento della prima origine dati (a sinistra), anche se nell'altra origine dati non sono presenti elementi correlati.</span><span class="sxs-lookup"><span data-stu-id="419d4-112">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="419d4-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="419d4-113">Example</span></span>  
 <span data-ttu-id="419d4-114">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle Contact e SalesOrderHeader per trovare il numero di ordini per contatto.</span><span class="sxs-lookup"><span data-stu-id="419d4-114">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="419d4-115">Vengono visualizzati l'ID e il numero di ordini per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="419d4-115">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="419d4-116">Join</span><span class="sxs-lookup"><span data-stu-id="419d4-116">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="419d4-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="419d4-117">Example</span></span>  
 <span data-ttu-id="419d4-118">Nell'esempio seguente viene eseguito un join sulle tabelle SalesOrderHeader e SalesOrderDetail per ottenere gli ordini effettuati online dal mese di agosto.</span><span class="sxs-lookup"><span data-stu-id="419d4-118">The following example performs a join over the SalesOrderHeader and SalesOrderDetail tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="419d4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="419d4-119">See also</span></span>
- [<span data-ttu-id="419d4-120">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="419d4-120">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
