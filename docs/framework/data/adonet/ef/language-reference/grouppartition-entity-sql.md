---
title: GROUPPARTITION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 19df566c254a3f3202eb3554ab43ee0d7c944181
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833756"
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="e93cd-102">GROUPPARTITION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e93cd-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="e93cd-103">Restituisce una raccolta di valori di argomento che sono estratti dalla partizione di gruppo corrente alla quale è correlata l'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="e93cd-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="e93cd-104">L'aggregazione `GroupPartition` è un'aggregazione basata sul gruppo e non ha un formato basato sulla raccolta.</span><span class="sxs-lookup"><span data-stu-id="e93cd-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e93cd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e93cd-105">Syntax</span></span>  
  
```sql  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="e93cd-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e93cd-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e93cd-107">Qualsiasi espressione [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e93cd-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e93cd-108">Note</span><span class="sxs-lookup"><span data-stu-id="e93cd-108">Remarks</span></span>  
 <span data-ttu-id="e93cd-109">Nella query seguente viene prodotto un elenco di prodotti e una raccolta di quantità nelle righe degli ordini per ogni prodotto:</span><span class="sxs-lookup"><span data-stu-id="e93cd-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="e93cd-110">Le due query seguenti sono semanticamente uguali:</span><span class="sxs-lookup"><span data-stu-id="e93cd-110">The following two queries are semantically equal:</span></span>  
  
```sql  
SELECT p, Sum(GroupPartition(ol.Quantity)) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
SELET p, Sum(ol.Quantity) FROM LOB.OrderLines AS ol
  group by ol.Product as p  
```  
  
 <span data-ttu-id="e93cd-111">L'operatore `GROUPPARTITION` può essere usato insieme a funzioni di aggregazione definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e93cd-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
<span data-ttu-id="e93cd-112">`GROUPPARTITION` è un operatore di aggregazione speciale che mantiene un riferimento al set di input raggruppato.</span><span class="sxs-lookup"><span data-stu-id="e93cd-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="e93cd-113">Questo riferimento può essere usato ovunque nella query laddove GROUP BY è nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="e93cd-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="e93cd-114">Esempio:</span><span class="sxs-lookup"><span data-stu-id="e93cd-114">For example:</span></span>
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="e93cd-115">Con un normale `GROUP BY`, i risultati del raggruppamento sono nascosti.</span><span class="sxs-lookup"><span data-stu-id="e93cd-115">With a regular `GROUP BY`, the results of the grouping are hidden.</span></span> <span data-ttu-id="e93cd-116">È possibile usare solo i risultati in una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="e93cd-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="e93cd-117">Per vedere i risultati del raggruppamento, è necessario correlarli al set di input tramite una sottoquery.</span><span class="sxs-lookup"><span data-stu-id="e93cd-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="e93cd-118">Le due query seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="e93cd-118">The following two queries are equivalent:</span></span>  
  
```sql  
SELET p, (SELECT q FROM GroupPartition(ol.Quantity) AS q) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
SELECT p, (SELECT ol.Quantity AS q FROM LOB.OrderLines AS ol2 WHERE ol2.Product = p) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="e93cd-119">Come illustrato nell'esempio, grazie all'operatore di aggregazione GROUPPARTITION diventa più semplice ottenere un riferimento al set di input dopo il raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="e93cd-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="e93cd-120">L'operatore GROUPPARTITION può specificare qualsiasi espressione [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nell'operatore di input quando si usa il parametro `expression` .</span><span class="sxs-lookup"><span data-stu-id="e93cd-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="e93cd-121">Tutte le espressioni di input seguenti alla partizione di gruppo sono valide:</span><span class="sxs-lookup"><span data-stu-id="e93cd-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```sql  
SELECT groupkey, GroupPartition(b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(1) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(a + b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition({a + b}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition({42}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition(b > a) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="e93cd-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="e93cd-122">Example</span></span>  
 <span data-ttu-id="e93cd-123">Nell'esempio seguente viene mostrato come usare la clausola GROUPPARTITION con la clausola GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="e93cd-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="e93cd-124">La clausola GROUP BY raggruppa entità `SalesOrderHeader` in base a `Contact`.</span><span class="sxs-lookup"><span data-stu-id="e93cd-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="e93cd-125">La clausola GROUPPARTITION proietta quindi la proprietà `TotalDue` per ogni gruppo, creando così una raccolta di numeri decimali.</span><span class="sxs-lookup"><span data-stu-id="e93cd-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#Collection_GroupPartition](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#collection_grouppartition)]
