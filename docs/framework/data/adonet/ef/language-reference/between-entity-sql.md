---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 2c411fd7fcac9d98323d5fcfb1874f98bc664991
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225261"
---
# <a name="between-entity-sql"></a>BETWEEN (Entity SQL)
Determina se un'espressione restituisce un valore incluso in un intervallo specificato. Il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] espressione BETWEEN ha la stessa funzionalità come l'espressione BETWEEN Transact-SQL.  
  
## <a name="syntax"></a>Sintassi  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione valida da testare nell'intervallo definito da `begin_expression` e `end_expression`. `expression` deve essere dello stesso tipo di `begin_expression` e `end_expression`.  
  
 `begin_expression`  
 Qualsiasi espressione valida. `begin_expression` deve essere dello stesso tipo di `expression` e `end_expression`. `begin_expression` deve essere minore di `end_expression`, altrimenti il valore restituito sarà negativo.  
  
 `end_expression`  
 Qualsiasi espressione valida. `end_expression` deve essere dello stesso tipo di `expression` e `begin_expression`.  
  
 NOT  
 Specifica la negazione del risultato di BETWEEN.  
  
 AND  
 Segnaposto che indica che l'oggetto `expression` deve essere incluso nell'intervallo specificato da `begin_expression` e `end_expression`.  
  
## <a name="return-value"></a>Valore restituito  
 `true` Se `expression` è incluso nell'intervallo indicato dal `begin_expression` e `end_expression`; in caso contrario, `false`. `null` Se viene restituito `expression` viene `null` o se `begin_expression` oppure `end_expression` è `null`.  
  
## <a name="remarks"></a>Note  
 Per specificare un intervallo esclusivo, utilizzare la maggiore (>) e minore di (<) operatori anziché BETWEEN.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore BETWEEN per determinare se un'espressione restituisce un valore incluso in un intervallo specificato. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
