---
title: Composizione di query Entity SQL annidate
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: cd41c36853f50597a32d511d455148d649d9eb64
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395550"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="a98c8-102">Composizione di query Entity SQL annidate</span><span class="sxs-lookup"><span data-stu-id="a98c8-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a98c8-103">è un linguaggio funzionale completo.</span><span class="sxs-lookup"><span data-stu-id="a98c8-103">is a rich functional language.</span></span> <span data-ttu-id="a98c8-104">Il blocco predefinito di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è un'espressione.</span><span class="sxs-lookup"><span data-stu-id="a98c8-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="a98c8-105">A differenza di SQL convenzionale, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non è limitato a un set di risultati tabulare: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta la composizione di espressioni complesse che possono avere valori letterali, parametri o espressioni annidate.</span><span class="sxs-lookup"><span data-stu-id="a98c8-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="a98c8-106">Un valore nell'espressione può essere parametrizzato o costituito da un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="a98c8-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="a98c8-107">Espressioni annidate</span><span class="sxs-lookup"><span data-stu-id="a98c8-107">Nested Expressions</span></span>  
 <span data-ttu-id="a98c8-108">Un'espressione annidata può essere inserita in una posizione qualsiasi in cui è accettato un valore del tipo restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="a98c8-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="a98c8-109">Esempio:</span><span class="sxs-lookup"><span data-stu-id="a98c8-109">For example:</span></span>  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="a98c8-110">Una query annidata può essere inserita in una clausola di proiezione.</span><span class="sxs-lookup"><span data-stu-id="a98c8-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="a98c8-111">Esempio:</span><span class="sxs-lookup"><span data-stu-id="a98c8-111">For example:</span></span>  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="a98c8-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] le query annidate devono sempre essere racchiuse tra parentesi:</span><span class="sxs-lookup"><span data-stu-id="a98c8-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="a98c8-113">Nell'esempio seguente viene illustrato come annidare correttamente le espressioni in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [procedura: ordinare l'Unione di due query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a98c8-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="a98c8-114">Query annidate nella proiezione</span><span class="sxs-lookup"><span data-stu-id="a98c8-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="a98c8-115">Le query annidate nella clausola del progetto potrebbero essere tradotte in query del prodotto cartesiano sul server.</span><span class="sxs-lookup"><span data-stu-id="a98c8-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="a98c8-116">In alcuni server back-end, tra cui SQL Server, questo può causare un notevole rischio per la tabella TempDB, che può influire negativamente sulle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="a98c8-116">In some backend servers, including SQL Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="a98c8-117">Di seguito è riportato un esempio di questo tipo di query:</span><span class="sxs-lookup"><span data-stu-id="a98c8-117">The following is an example of such a query:</span></span>  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="a98c8-118">Ordinamento di query annidate</span><span class="sxs-lookup"><span data-stu-id="a98c8-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="a98c8-119">In Entity Framework un'espressione annidata può essere inserita in un punto qualsiasi della query.</span><span class="sxs-lookup"><span data-stu-id="a98c8-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="a98c8-120">Poiché Entity SQL rende molto flessibile la scrittura di query, è possibile scrivere una query contenente una serie di query annidate in ordine.</span><span class="sxs-lookup"><span data-stu-id="a98c8-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="a98c8-121">L'ordine di una query annidata non viene tuttavia mantenuto.</span><span class="sxs-lookup"><span data-stu-id="a98c8-121">However, the order of a nested query is not preserved.</span></span>  
  
```sql  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a><span data-ttu-id="a98c8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a98c8-122">See also</span></span>

- [<span data-ttu-id="a98c8-123">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a98c8-123">Entity SQL Overview</span></span>](entity-sql-overview.md)
