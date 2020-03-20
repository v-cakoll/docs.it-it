---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: a0f5dd19c439861451b1e88c3ae35f9f265288fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150493"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Determina se un'espressione restituisce un valore incluso in un intervallo specificato. L'espressione [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN ha la stessa funzionalità dell'espressione Transact-SQL BETWEEN.  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
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
  
## <a name="remarks"></a>Osservazioni  
 Per specificare un intervallo esclusivo, utilizzare gli operatori maggiore di (>) e minore di (<) anziché BETWEEN.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore BETWEEN per determinare se un'espressione restituisce un valore incluso in un intervallo specificato. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
