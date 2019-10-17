---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 9d4cdeac317509fd61741a19276a6764a1c2bfce
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319346"
---
# <a name="set-entity-sql"></a>SET (Entity SQL)
L'espressione SET viene usata per convertire una raccolta di oggetti in un set restituendo una nuova raccolta da cui sono stati rimossi tutti i duplicati.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta.  
  
## <a name="remarks"></a>Note  
 L'espressione set `SET(c)` equivale, dal punto di vista logico,  all'istruzione Select seguente:  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra. Vedere [ad eccezione](except-entity-sql.md) delle informazioni di precedenza per gli operatori set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usata l'espressione SET per convertire una raccolta di oggetti in un set. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta in [procedura: eseguire una query che restituisce i risultati di PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
