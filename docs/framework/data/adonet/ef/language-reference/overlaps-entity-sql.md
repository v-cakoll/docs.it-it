---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: bdee9281fd406a3d029d3a10536cbdd48d2f7a58
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319419"
---
# <a name="overlaps-entity-sql"></a>OVERLAPS (Entity SQL)
Determina se due raccolte includono elementi comuni.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta da confrontare con la raccolta restituita da un'altra espressione di query. Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `expression`.  
  
## <a name="return-value"></a>Valore restituito  
 `true` se le due raccolte includono elementi comuni; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 SOVRAPPOSIZIONI fornisce un equivalente dal punto di vista funzionale a quanto segue:  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 OVERLAPS è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra. Per informazioni sulla precedenza per gli operatori set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vedere [except](except-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore OVERLAPS per determinare se due raccolte hanno un valore comune. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
