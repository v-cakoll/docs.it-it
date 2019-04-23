---
title: 'Procedura: Eseguire una query per ottenere informazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: aedf89f1e570b34d31050fabb91842cefe351488
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162842"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="392a8-102">Procedura: Eseguire una query per ottenere informazioni</span><span class="sxs-lookup"><span data-stu-id="392a8-102">How to: Query for Information</span></span>
<span data-ttu-id="392a8-103">Le query in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] usano la stessa sintassi delle query in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="392a8-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="392a8-104">L'unica differenza è che gli oggetti cui viene fatto riferimento [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query vengono mappate agli elementi in un database.</span><span class="sxs-lookup"><span data-stu-id="392a8-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="392a8-105">Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="392a8-105">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="392a8-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL equivalenti e inviate al server per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="392a8-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="392a8-107">Alcune funzionalità delle query [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] potrebbero richiedere un'attenzione speciale nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="392a8-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="392a8-108">Per altre informazioni, vedere [concetti relatici alle Query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="392a8-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="392a8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="392a8-109">Example</span></span>  
 <span data-ttu-id="392a8-110">La query seguente consente di richiedere un elenco di clienti nell'area londinese.</span><span class="sxs-lookup"><span data-stu-id="392a8-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="392a8-111">In questo esempio `Customers` è una tabella nel database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="392a8-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="392a8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="392a8-112">See also</span></span>

- [<span data-ttu-id="392a8-113">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="392a8-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="392a8-114">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="392a8-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="392a8-115">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="392a8-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
