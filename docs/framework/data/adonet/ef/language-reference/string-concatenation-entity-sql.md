---
title: + (Concatenazione di stringhe) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 9c078e193eeecd4d331c5e3c04c66dee2c4a1daa
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319318"
---
# <a name="-string-concatenation-entity-sql"></a>+ (concatenazione di stringhe) (Entity SQL)
Concatena due stringhe.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Qualsiasi espressione valida dei tipi di dati EDM.String. Entrambe le espressioni devono essere dello stesso tipo di dati oppure un'espressione deve poter essere convertita in modo implicito nel tipo di dati dell'altra espressione.  
  
## <a name="result-types"></a>Tipi di risultati  
 Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti. Per ulteriori informazioni sull'innalzamento di tipo implicito, vedere [System Type](type-system-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore + per concatenare due stringhe. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta in [procedura: eseguire una query che restituisce i risultati di PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Tipi del modello concettuale (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
