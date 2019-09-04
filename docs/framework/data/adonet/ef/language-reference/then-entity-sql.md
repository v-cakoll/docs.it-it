---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: c64e440e8cd8f86706db69d923ba7085d0cb3b3a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248983"
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
Risultato di una clausola WHEN quando restituisce `true`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `when_expression`  
 Qualsiasi espressione booleana valida.  
  
 `then_expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta.  
  
## <a name="remarks"></a>Note  
 Se `when_expression` restituisce il valore `true`, il risultato è l'oggetto `then-expression`corrispondente. Se nessuna delle condizioni WHEN è soddisfatta, viene restituito `else-expression` . Se, tuttavia, non sono presenti `else-expression`, il risultato è null.  
  
 Per un esempio, vedere [case](case-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usata l'espressione CASE per valutare un set di espressioni `Boolean` . La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-primitivetype-results.md)di PrimitiveType.  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Vedere anche

- [CASE](case-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
