---
title: GROUPPARTITION (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 09d4d1e6d2e69d805c316f60e6d6e91d094e68cb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="be735-102">GROUPPARTITION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="be735-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="be735-103">Restituisce una raccolta di valori di argomento che sono estratti dalla partizione di gruppo corrente alla quale è correlata l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="be735-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="be735-104">L'aggregazione `GroupPartition` è un'aggregazione basata sul gruppo e non ha un formato basato sulla raccolta.</span><span class="sxs-lookup"><span data-stu-id="be735-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be735-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be735-105">Syntax</span></span>  
  
```  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="be735-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="be735-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="be735-107">Qualsiasi espressione [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be735-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be735-108">Note</span><span class="sxs-lookup"><span data-stu-id="be735-108">Remarks</span></span>  
 <span data-ttu-id="be735-109">Nella query seguente viene prodotto un elenco di prodotti e una raccolta di quantità nelle righe degli ordini per ogni prodotto:</span><span class="sxs-lookup"><span data-stu-id="be735-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="be735-110">Le due query seguenti sono semanticamente uguali:</span><span class="sxs-lookup"><span data-stu-id="be735-110">The following two queries are semantically equal:</span></span>  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="be735-111">L'operatore `GROUPPARTITION` può essere usato insieme a funzioni di aggregazione definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="be735-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
 <span data-ttu-id="be735-112">`GROUPPARTITION` è un operatore di aggregazione speciale che mantiene un riferimento al set di input raggruppato.</span><span class="sxs-lookup"><span data-stu-id="be735-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="be735-113">Questo riferimento può essere usato ovunque nella query laddove GROUP BY è nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="be735-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="be735-114">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="be735-114">For example,</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="be735-115">Se si usa un GROUP BY normale, i risultati del raggruppamento sono nascosti.</span><span class="sxs-lookup"><span data-stu-id="be735-115">With a regular GROUP BY, the results of the grouping are hidden.</span></span> <span data-ttu-id="be735-116">È possibile usare solo i risultati in una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="be735-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="be735-117">Per vedere i risultati del raggruppamento, è necessario correlarli al set di input tramite una sottoquery.</span><span class="sxs-lookup"><span data-stu-id="be735-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="be735-118">Le due query seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="be735-118">The following two queries are equivalent:</span></span>  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="be735-119">Come illustrato nell'esempio, grazie all'operatore di aggregazione GROUPPARTITION diventa più semplice ottenere un riferimento al set di input dopo il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="be735-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="be735-120">L'operatore GROUPPARTITION può specificare qualsiasi espressione [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nell'operatore di input quando si usa il parametro `expression` .</span><span class="sxs-lookup"><span data-stu-id="be735-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="be735-121">Tutte le espressioni di input seguenti alla partizione di gruppo sono valide:</span><span class="sxs-lookup"><span data-stu-id="be735-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="be735-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="be735-122">Example</span></span>  
 <span data-ttu-id="be735-123">Nell'esempio seguente viene mostrato come usare la clausola GROUPPARTITION con la clausola GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="be735-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="be735-124">La clausola GROUP BY raggruppa entità `SalesOrderHeader` in base a `Contact`.</span><span class="sxs-lookup"><span data-stu-id="be735-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="be735-125">La clausola GROUPPARTITION proietta quindi la proprietà `TotalDue` per ogni gruppo, creando così una raccolta di numeri decimali.</span><span class="sxs-lookup"><span data-stu-id="be735-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]
