---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 76999bcbbb3b63fd945d2048734c58d97de8baea
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249231"
---
# <a name="set-entity-sql"></a>SET (Entity SQL)
L'espressione SET viene usata per convertire una raccolta di oggetti in un set restituendo una nuova raccolta da cui sono stati rimossi tutti i duplicati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta.  
  
## <a name="remarks"></a>Note  
 L'espressione set `SET(c)` equivale, dal punto di vista logico,  all'istruzione Select seguente:  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra. Vedere [ad eccezione](except-entity-sql.md) delle informazioni di precedenza [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per gli operatori sui set.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usata l'espressione SET per convertire una raccolta di oggetti in un set. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-primitivetype-results.md)di PrimitiveType.  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
