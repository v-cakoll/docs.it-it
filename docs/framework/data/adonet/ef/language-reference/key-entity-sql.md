---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 894a9d41aa3a14ad66b537433aa315823a299f95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150169"
---
# <a name="key-entity-sql"></a>KEY (Entity SQL)
Estrae la chiave di un riferimento o di un'espressione di entità.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a>Osservazioni  
 Una chiave di entità contiene nell'ordine corretto i valori di chiave relativi all'entità o al riferimento all'entità specificato. Poiché più set di entità possono essere basati sullo stesso tipo di entità, è possibile che venga visualizzata la stessa chiave in ogni set. Per ottenere un riferimento univoco, usare `REF`. Il tipo restituito dell'operatore KEY è un tipo di riga che include un campo per ogni chiave dell'entità, nello stesso ordine.  
  
 Nell'esempio seguente all'operatore Key viene passato un riferimento all'entità BadOrder. Viene restituita la parte relativa alla chiave del riferimento in questione, che in questo caso è un tipo di record con un campo esattamente corrispondente alla proprietà `Id` .  
  
```sql  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )
from LOB.Orders as o  
```  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore KEY per estrarre la parte relativa alla chiave di un'espressione con riferimento al tipo. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#KEY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#key)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [CREATEREF](createref-entity-sql.md)
- [Ref](ref-entity-sql.md)
- [DEREF](deref-entity-sql.md)
