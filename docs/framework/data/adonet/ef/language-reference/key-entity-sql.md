---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 9cd3276583741f2b0261cb8a0e55f4185d20100e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319339"
---
# <a name="key-entity-sql"></a>KEY (Entity SQL)
Estrae la chiave di un riferimento o di un'espressione di entità.  
  
## <a name="syntax"></a>Sintassi  
  
```  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a>Note  
 Una chiave di entità contiene nell'ordine corretto i valori di chiave relativi all'entità o al riferimento all'entità specificato. Poiché più set di entità possono essere basati sullo stesso tipo di entità, è possibile che venga visualizzata la stessa chiave in ogni set. Per ottenere un riferimento univoco, usare `REF`. Il tipo restituito dell'operatore KEY è un tipo di riga che include un campo per ogni chiave dell'entità, nello stesso ordine.  
  
 Nell'esempio seguente all'operatore Key viene passato un riferimento all'entità BadOrder. Viene restituita la parte relativa alla chiave del riferimento in questione, che in questo caso è un tipo di record con un campo esattamente corrispondente alla proprietà `Id` .  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore KEY per estrarre la parte relativa alla chiave di un'espressione con riferimento al tipo. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
- [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
