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
# <a name="grouppartition-entity-sql"></a>GROUPPARTITION (Entity SQL)
Restituisce una raccolta di valori di argomento che sono estratti dalla partizione di gruppo corrente alla quale è correlata l'aggregazione. L'aggregazione `GroupPartition` è un'aggregazione basata sul gruppo e non ha un formato basato sulla raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .  
  
## <a name="remarks"></a>Note  
 Nella query seguente viene prodotto un elenco di prodotti e una raccolta di quantità nelle righe degli ordini per ogni prodotto:  
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
```  
  
 Le due query seguenti sono semanticamente uguali:  
  
```sql  
SELECT p, Sum(GroupPartition(ol.Quantity)) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
SELET p, Sum(ol.Quantity) FROM LOB.OrderLines AS ol
  group by ol.Product as p  
```  
  
 L'operatore `GROUPPARTITION` può essere usato insieme a funzioni di aggregazione definite dall'utente.  
  
`GROUPPARTITION` è un operatore di aggregazione speciale che mantiene un riferimento al set di input raggruppato. Questo riferimento può essere usato ovunque nella query laddove GROUP BY è nell'ambito. Esempio:
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 Con un normale `GROUP BY`, i risultati del raggruppamento sono nascosti. È possibile usare solo i risultati in una funzione di aggregazione. Per vedere i risultati del raggruppamento, è necessario correlarli al set di input tramite una sottoquery. Le due query seguenti sono equivalenti:  
  
```sql  
SELET p, (SELECT q FROM GroupPartition(ol.Quantity) AS q) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
SELECT p, (SELECT ol.Quantity AS q FROM LOB.OrderLines AS ol2 WHERE ol2.Product = p) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 Come illustrato nell'esempio, grazie all'operatore di aggregazione GROUPPARTITION diventa più semplice ottenere un riferimento al set di input dopo il raggruppamento.  
  
 L'operatore GROUPPARTITION può specificare qualsiasi espressione [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nell'operatore di input quando si usa il parametro `expression` .  
  
 Tutte le espressioni di input seguenti alla partizione di gruppo sono valide:  
  
```sql  
SELECT groupkey, GroupPartition(b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(1) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(a + b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition({a + b}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition({42}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition(b > a) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene mostrato come usare la clausola GROUPPARTITION con la clausola GROUP BY. La clausola GROUP BY raggruppa entità `SalesOrderHeader` in base a `Contact`. La clausola GROUPPARTITION proietta quindi la proprietà `TotalDue` per ogni gruppo, creando così una raccolta di numeri decimali.  
  
 [!code-sql[DP EntityServices Concepts#Collection_GroupPartition](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#collection_grouppartition)]
