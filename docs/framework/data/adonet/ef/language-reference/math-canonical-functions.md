---
title: Funzioni matematiche canoniche
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 33c8b500002b46d720533f681807889955de5982
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="math-canonical-functions"></a>Funzioni matematiche canoniche
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] include funzioni canoniche matematiche.  
  
 Nella tabella seguente sono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] matematiche.  
  
|Funzione|Descrizione|  
|--------------|-----------------|  
|`Abs(` `value` `)`|Restituisce il valore assoluto di `value`.<br /><br /> **Argomenti**<br /><br /> Un `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, e `Decimal`.<br /><br /> **Valore restituito**<br /><br /> Tipo di `value`.<br /><br /> **Esempio**<br /><br /> `Abs(-2)`|  
|`Ceiling(` `value` `)`|Restituisce il valore integer più piccolo non minore di `value`.<br /><br /> **Argomenti**<br /><br /> Oggetto `Single`, `Double`, e `Decimal`.<br /><br /> **Valore restituito**<br /><br /> Tipo di `value`.<br /><br /> **Esempio**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
 [!code-sql[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]|  
|`Floor(` `value` `)`|Restituisce il valore integer più grande non maggiore di `value`.<br /><br /> **Argomenti**<br /><br /> Oggetto `Single`, `Double`, e `Decimal`.<br /><br /> **Valore restituito**<br /><br /> Tipo di `value`.<br /><br /> **Esempio**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
 [!code-sql[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]|  
|`Power(` `value`, `exponent``)`|Restituisce il risultato dell'oggetto `value` specificato all'oggetto `exponent` specificato.<br /><br /> **Argomenti**<br /><br /> `value`: Un `Int32, Int64, Double`, o `Decimal`.<br /><br /> `exponent`: Un `Int64``, Double`, o `Decimal`.<br /><br /> **Valore restituito**<br /><br /> Tipo di `value`.<br /><br /> **Esempio**<br /><br /> `Power(748.58,2)`|  
|`Round(` `value` `)`|Restituisce la parte intera di `value` arrotondata al valore integer più vicino.<br /><br /> **Argomenti**<br /><br /> Oggetto `Single`, `Double`, e `Decimal`.<br /><br /> **Valore restituito**<br /><br /> Tipo di `value`.<br /><br /> **Esempio**<br /><br /> `Round(748.58)`|  
|`Round(` `value`, `digits``)`|Restituisce `value`, arrotondato al valore di `digits` specificato più vicino.<br /><br /> **Argomenti**<br /><br /> `value`: `Double` o `Decimal`.<br /><br /> `digits`: `Int16` o `Int32`.<br /><br /> **Valore restituito**<br /><br /> Tipo di `value`.<br /><br /> **Esempio**<br /><br /> `Round(748.58,1)`|  
|`Truncate(` `value`, `digits``)`|Restituisce `value`, troncato al valore di `digits` specificato più vicino.<br /><br /> **Argomenti**<br /><br /> `value`: `Double` o `Decimal`.<br /><br /> `digits`: `Int16` o `Int32`.<br /><br /> **Valore restituito**<br /><br /> Tipo di `value`.<br /><br /> **Esempio**<br /><br /> `Truncate(748.58,1)`|  
  
 Queste funzioni restituiscono `null` se l'input è `null`.  
  
 Una funzionalità equivalente è disponibile nel provider gestito del client Microsoft SQL. Per ulteriori informazioni, vedere [SqlClient per funzioni Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
