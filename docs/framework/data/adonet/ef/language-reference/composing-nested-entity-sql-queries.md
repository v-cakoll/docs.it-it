---
title: Composizione di query Entity SQL annidate
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6aab21c4b22e731f3d85a2f444e82bc04906c320
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="87119-102">Composizione di query Entity SQL annidate</span><span class="sxs-lookup"><span data-stu-id="87119-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="87119-103"> è un linguaggio funzionale completo.</span><span class="sxs-lookup"><span data-stu-id="87119-103"> is a rich functional language.</span></span> <span data-ttu-id="87119-104">Il blocco predefinito di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è un'espressione.</span><span class="sxs-lookup"><span data-stu-id="87119-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="87119-105">A differenza dei tradizionali SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non è limitato a un set di risultati tabulari: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta la creazione di espressioni complesse che possono contenere valori letterali, parametri o le espressioni nidificate.</span><span class="sxs-lookup"><span data-stu-id="87119-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="87119-106">Un valore nell'espressione può essere con parametri o composto da un'altra espressione.</span><span class="sxs-lookup"><span data-stu-id="87119-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="87119-107">Espressioni annidate</span><span class="sxs-lookup"><span data-stu-id="87119-107">Nested Expressions</span></span>  
 <span data-ttu-id="87119-108">Un'espressione annidata può essere inserita in una posizione qualsiasi in cui è accettato un valore del tipo restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="87119-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="87119-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="87119-109">For example:</span></span>  
  
```  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="87119-110">Una query annidata può essere inserita in una clausola di proiezione.</span><span class="sxs-lookup"><span data-stu-id="87119-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="87119-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="87119-111">For example:</span></span>  
  
```  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="87119-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] le query annidate devono sempre essere racchiuse tra parentesi:</span><span class="sxs-lookup"><span data-stu-id="87119-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="87119-113">Nell'esempio riportato di seguito viene illustrato come annidare correttamente le espressioni in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [procedura: ordinare l'unione di due query](http://msdn.microsoft.com/en-us/853c583a-eaba-4400-830d-be974e735313).</span><span class="sxs-lookup"><span data-stu-id="87119-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](http://msdn.microsoft.com/en-us/853c583a-eaba-4400-830d-be974e735313).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="87119-114">Query  annidate nella proiezione</span><span class="sxs-lookup"><span data-stu-id="87119-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="87119-115">Le query annidate nella clausola del progetto potrebbero essere tradotte in query del prodotto cartesiano sul server.</span><span class="sxs-lookup"><span data-stu-id="87119-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="87119-116">In alcuni server di back-end, tra cui Server SLQ, questo può provocare l'aumento delle dimensioni della tabella TempDB, con effetti negativi sulle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="87119-116">In some backend servers, including SLQ Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="87119-117">Di seguito è riportato un esempio di questo tipo di query:</span><span class="sxs-lookup"><span data-stu-id="87119-117">The following is an example of such a query:</span></span>  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="87119-118">Ordinamento di query annidate</span><span class="sxs-lookup"><span data-stu-id="87119-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="87119-119">In Entity Framework un'espressione annidata può essere inserita in un punto qualsiasi della query.</span><span class="sxs-lookup"><span data-stu-id="87119-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="87119-120">Poiché Entity SQL rende molto flessibile la scrittura di query, è possibile scrivere una query contenente una serie di query annidate in ordine.</span><span class="sxs-lookup"><span data-stu-id="87119-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="87119-121">L'ordine di una query annidata non viene tuttavia mantenuto.</span><span class="sxs-lookup"><span data-stu-id="87119-121">However, the order of a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a><span data-ttu-id="87119-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87119-122">See Also</span></span>  
 [<span data-ttu-id="87119-123">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="87119-123">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
