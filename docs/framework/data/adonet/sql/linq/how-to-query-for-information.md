---
title: 'Procedura: eseguire una query per ottenere informazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 3380b486da33a5dc083ed51f6705e666978df197
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634651"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="25397-102">Procedura: eseguire una query per ottenere informazioni</span><span class="sxs-lookup"><span data-stu-id="25397-102">How to: Query for Information</span></span>
<span data-ttu-id="25397-103">Le query in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizzano la stessa sintassi delle query in LINQ.</span><span class="sxs-lookup"><span data-stu-id="25397-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="25397-104">L'unica differenza è che agli oggetti a cui viene fatto riferimento nelle query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping agli elementi in un database.</span><span class="sxs-lookup"><span data-stu-id="25397-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="25397-105">Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="25397-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="25397-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL equivalenti e inviate al server per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="25397-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="25397-107">Alcune funzionalità delle query LINQ potrebbero richiedere particolare attenzione nelle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25397-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="25397-108">Per altre informazioni, vedere [concetti relativi alle query](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="25397-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="25397-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="25397-109">Example</span></span>  
 <span data-ttu-id="25397-110">La query seguente consente di richiedere un elenco di clienti nell'area londinese.</span><span class="sxs-lookup"><span data-stu-id="25397-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="25397-111">In questo esempio `Customers` è una tabella nel database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="25397-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="25397-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25397-112">See also</span></span>

- [<span data-ttu-id="25397-113">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="25397-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="25397-114">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="25397-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="25397-115">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="25397-115">Querying the Database</span></span>](querying-the-database.md)
