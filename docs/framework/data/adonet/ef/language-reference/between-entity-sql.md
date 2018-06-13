---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: bab31ca0a6fd37f5179412b7a4936d564620135e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761772"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Determina se un'espressione restituisce un valore incluso in un intervallo specificato. Il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tra espressione ha la stessa funzionalità espressione BETWEEN Transact-SQL.  
  
## <a name="syntax"></a>Sintassi  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione valida da testare nell'intervallo definito da `begin_expression` e `end_expression`. `expression` deve essere dello stesso tipo sia di `begin_expression` che di `end_expression`.  
  
 `begin_expression`  
 Qualsiasi espressione valida. `begin_expression` deve essere dello stesso tipo sia di `expression` che di `end_expression`. `begin_expression` deve essere minore di `end_expression`; in caso contrario, il valore restituito sarà negativo.  
  
 `end_expression`  
 Qualsiasi espressione valida. `end_expression` deve essere dello stesso tipo sia di `expression` che di `begin_expression`.  
  
 NOT  
 Specifica la negazione del risultato di BETWEEN.  
  
 AND  
 Segnaposto che indica che l'oggetto `expression` deve essere incluso nell'intervallo specificato da `begin_expression` e `end_expression`.  
  
## <a name="return-value"></a>Valore restituito  
 `true` se `expression` si trova tra l'intervallo indicato da `begin_expression` e `end_expression`; in caso contrario, `false`. Verrà restituito `null` se `expression` è `null` o se `begin_expression` o `end_expression` è `null`.  
  
## <a name="remarks"></a>Note  
 Per specificare un intervallo esclusivo, usare gli operatori "maggiore di" (>) e "minore di" (<), anziché BETWEEN.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore BETWEEN per determinare se un'espressione restituisce un valore incluso in un intervallo specificato. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
