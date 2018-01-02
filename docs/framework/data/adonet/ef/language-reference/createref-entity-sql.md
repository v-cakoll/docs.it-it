---
title: CREATEREF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ad5329e50a5bea933e8fdfdfd473b2d4b9e0b211
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="createref-entity-sql"></a>CREATEREF (Entity SQL)
Consente di creare riferimenti a un'entità in un oggetto EntitySet.  
  
## <a name="syntax"></a>Sintassi  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a>Argomenti  
 `entityset_identifier`  
 Identificatore dell'oggetto EntitySet, non un valore letterale stringa.  
  
 `row_typed_expression`  
 Espressione con tipizzazione di riga che corrisponde alle proprietà chiave del tipo di entità.  
  
## <a name="remarks"></a>Note  
 Dal punto di vista strutturale,`row_typed_expression` deve essere equivalente al tipo di chiave per l'entità. Questo significa che deve avere lo stesso numero di tipi e di campi nello stesso ordine delle chiavi di entità.  
  
 Nell'esempio seguente Orders e BadOrders sono entrambi oggetti EntitySet di tipo Order e si presuppone che Id sia la proprietà di chiave singola di Order. Nell'esempio viene illustrato in che modo è possibile creare un riferimento a un'entità in BadOrders. Si noti che il riferimento può essere inesatto,  ovvero potrebbe non identificare effettivamente un'entità specifica. In casi di questo tipo un'operazione `DEREF` su tale riferimento restituisce un valore Null.  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore CREATEREF per creare riferimenti a un'entità in un set di entità. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
