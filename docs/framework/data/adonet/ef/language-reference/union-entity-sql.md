---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: a5a20beb0ab55dcbaf2dbbb75801b50ab9ef6722
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319225"
---
# <a name="union-entity-sql"></a>UNION (Entity SQL)
Combina i risultati di due o più query in una singola raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta da combinare con le espressioni ALL della raccolta deve essere dello stesso tipo o di un tipo di base o derivato comune di `expression`.  
  
 UNION  
 Specifica che più raccolte devono essere combinate e restituite come singola raccolta.  
  
 ALL  
 Specifica che più raccolte devono essere combinate e restituite come singola raccolta, inclusi i duplicati. Se non viene specificato, i duplicati vengono rimossi dalla raccolta dei risultati.  
  
## <a name="return-value"></a>Valore restituito  
 Raccolta dello stesso tipo o di un tipo di base o derivato comune di `expression`.  
  
## <a name="remarks"></a>Note  
 UNION è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra. Per informazioni sulla precedenza per gli operatori set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vedere [except](except-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore UNION ALL per combinare i risultati di due query in una singola raccolta. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#UNION](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#union)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
