---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 84b846e3db86c664bc42363f3d983a1001f5c318
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833811"
---
# <a name="flatten-entity-sql"></a>FLATTEN (Entity SQL)
Converte una raccolta di raccolte in una raccolta bidimensionale. La nuova raccolta contiene tutti gli stessi elementi di quella vecchia, ma senza una struttura annidata.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a>Argomenti  
 `collection`  
 Qualsiasi espressione valida che restituisce una raccolta di valori da inserire in un'unica raccolta bidimensionale.  
  
## <a name="remarks"></a>Osservazioni  
 `FLATTEN` è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra. Vedere [ad eccezione](except-entity-sql.md) delle informazioni di precedenza per gli operatori set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore `FLATTEN` per convertire una raccolta di raccolte in una raccolta bidimensionale. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
