---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 41036e629837bd5861368df545bed9423eac5b23
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251289"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Determina se un'espressione restituisce un valore incluso in un intervallo specificato. L' [!INCLUDE[esql](../../../../../../includes/esql-md.md)] espressione between ha la stessa funzionalità dell'espressione Transact-SQL between.  
  
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
 Per specificare un intervallo esclusivo, utilizzare gli operatori maggiore di (>) e minore di (<) anziché tra.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore BETWEEN per determinare se un'espressione restituisce un valore incluso in un intervallo specificato. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
