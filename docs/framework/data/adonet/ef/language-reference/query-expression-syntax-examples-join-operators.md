---
title: 'Esempi di sintassi delle espressioni di query: Operatori di join'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: e80c50daeb0de7f4a8477786f28441d1495033ea
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249480"
---
# <a name="query-expression-syntax-examples-join-operators"></a><span data-ttu-id="fa5ec-102">Esempi di sintassi delle espressioni di query: Operatori di join</span><span class="sxs-lookup"><span data-stu-id="fa5ec-102">Query Expression Syntax Examples: Join Operators</span></span>
<span data-ttu-id="fa5ec-103">La creazione di un join è un'operazione importante in query destinate a origini dati che non presentano relazioni esplorabili tra loro, ad esempio le tabelle di database relazionali.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="fa5ec-104">Per join di due origini dati si intende l'associazione degli oggetti di un'origine dati con oggetti che condividono un attributo comune nell'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="fa5ec-105">Per ulteriori informazioni, vedere [Cenni preliminari sugli operatori di query standard](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="fa5ec-105">For more information, see [Standard Query Operators Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span></span>  
  
 <span data-ttu-id="fa5ec-106">Negli esempi di questo argomento viene illustrato come utilizzare i <xref:System.Linq.Enumerable.GroupJoin%2A> metodi <xref:System.Linq.Enumerable.Join%2A> e per eseguire query sul [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) utilizzando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="fa5ec-107">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-107">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="fa5ec-108">Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`</span><span class="sxs-lookup"><span data-stu-id="fa5ec-108">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="fa5ec-109">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="fa5ec-109">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="fa5ec-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa5ec-110">Example</span></span>  
 <span data-ttu-id="fa5ec-111">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle SalesOrderHeader e SalesOrderDetail per trovare il numero di ordini per cliente.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="fa5ec-112">Questa operazione equivale a un left outer join, che restituisce ogni elemento della prima origine dati (a sinistra), anche se nell'altra origine dati non sono presenti elementi correlati.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-112">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="fa5ec-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa5ec-113">Example</span></span>  
 <span data-ttu-id="fa5ec-114">Nell'esempio seguente viene eseguita un'operazione <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle Contact e SalesOrderHeader per trovare il numero di ordini per contatto.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-114">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="fa5ec-115">Vengono visualizzati l'ID e il numero di ordini per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-115">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="fa5ec-116">Unisci</span><span class="sxs-lookup"><span data-stu-id="fa5ec-116">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="fa5ec-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa5ec-117">Example</span></span>  
 <span data-ttu-id="fa5ec-118">Nell'esempio seguente viene eseguito un join sulle tabelle SalesOrderHeader e SalesOrderDetail per ottenere gli ordini effettuati online dal mese di agosto.</span><span class="sxs-lookup"><span data-stu-id="fa5ec-118">The following example performs a join over the SalesOrderHeader and SalesOrderDetail tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="fa5ec-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa5ec-119">See also</span></span>

- [<span data-ttu-id="fa5ec-120">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="fa5ec-120">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
