---
title: "Procedura: Chiamare funzioni inline definite dall'utente"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: e9808856543e20b8904be812b15b32154eab56e2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782113"
---
# <a name="how-to-call-user-defined-functions-inline"></a><span data-ttu-id="48198-102">Procedura: Chiamare funzioni inline definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="48198-102">How to: Call User-Defined Functions Inline</span></span>
<span data-ttu-id="48198-103">Anche se è possibile chiamare le funzioni inline definite dall'utente, le funzioni incluse in una query la cui esecuzione è rinviata non vengono eseguite finche non verrà eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="48198-103">Although you can call user-defined functions inline, functions that are included in a query whose execution is deferred are not executed until the query is executed.</span></span> <span data-ttu-id="48198-104">Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="48198-104">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="48198-105">Quando si chiama la stessa funzione al di fuori di una query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea una semplice query dall'espressione della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="48198-105">When you call the same function outside a query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates a simple query from the method call expression.</span></span> <span data-ttu-id="48198-106">Di seguito è riportata la sintassi SQL, in cui il parametro `@p0` è associato alla costante passata:</span><span class="sxs-lookup"><span data-stu-id="48198-106">The following is the SQL syntax (the parameter `@p0` is bound to the constant passed in):</span></span>  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 <span data-ttu-id="48198-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene creato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="48198-107">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates the following:</span></span>  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="48198-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="48198-108">Example</span></span>  
 <span data-ttu-id="48198-109">Nella query seguente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è possibile visualizzare una chiamata inline al metodo `ReverseCustName`generato della funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="48198-109">In the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query, you can see an inline call to the generated user-defined function method `ReverseCustName`.</span></span> <span data-ttu-id="48198-110">La funzione non viene eseguita immediatamente poiché l'esecuzione della query è rinviata.</span><span class="sxs-lookup"><span data-stu-id="48198-110">The function is not executed immediately because query execution is deferred.</span></span> <span data-ttu-id="48198-111">Il codice SQL compilato per questa query viene convertito in una chiamata alla funzione definita dall'utente nel database. Vedere il codice SQL che segue la query.</span><span class="sxs-lookup"><span data-stu-id="48198-111">The SQL built for this query translates to a call to the user-defined function in the database (see the SQL code following the query).</span></span>  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a><span data-ttu-id="48198-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48198-112">See also</span></span>

- [<span data-ttu-id="48198-113">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="48198-113">User-Defined Functions</span></span>](user-defined-functions.md)
