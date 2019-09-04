---
title: + (Concatenazione di stringhe) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: ef482a1206dea98cfb5a0ba5071acc130ef0cd18
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249024"
---
# <a name="-string-concatenation-entity-sql"></a>+ (concatenazione di stringhe) (Entity SQL)
Concatena due stringhe.  
  
## <a name="syntax"></a>Sintassi  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione valida dei tipi di dati EDM.String. Entrambe le espressioni devono essere dello stesso tipo di dati oppure un'espressione deve poter essere convertita in modo implicito nel tipo di dati dell'altra espressione.  
  
## <a name="result-types"></a>Tipi di risultati  
 Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti. Per ulteriori informazioni sull'innalzamento di tipo implicito, vedere [System Type](type-system-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore + per concatenare due stringhe. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-primitivetype-results.md)di PrimitiveType.  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Tipi del modello concettuale (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
