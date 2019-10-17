---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: ba01a978c53b58f7e6c1ac9bc42a97277ac64bbc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319290"
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
Risultato di una clausola WHEN quando restituisce `true`.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>argomenti  
 `when_expression`  
 Qualsiasi espressione booleana valida.  
  
 `then_expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta.  
  
## <a name="remarks"></a>Note  
 Se `when_expression` restituisce il valore `true`, il risultato è l'oggetto `then-expression`corrispondente. Se nessuna delle condizioni WHEN è soddisfatta, viene restituito `else-expression` . Se, tuttavia, non sono presenti `else-expression`, il risultato è null.  
  
 Per un esempio, vedere [case](case-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usata l'espressione CASE per valutare un set di espressioni `Boolean` . La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta in [procedura: eseguire una query che restituisce i risultati di PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a>Vedere anche

- [CASE](case-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
