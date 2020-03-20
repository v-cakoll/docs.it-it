---
title: CASE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 58b21d3be8e13a0a2204a4fd6d355f734207c509
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150467"
---
# <a name="case-entity-sql"></a>CASE (Entity SQL)
Valuta un set di espressioni `Boolean` per determinare il risultato.  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
CASE  
     WHEN Boolean_expression THEN result_expression
    [ ...n ]
     [
    ELSE else_result_expression
     ]
END  
```  
  
## <a name="arguments"></a>Argomenti  
 `n`  
 Segnaposto che indica la possibilità di usare più clausole WHEN `Boolean_expression` THEN `result_expression` .  
  
 THEN `result_expression`  
 È l'espressione restituita quando `Boolean_expression` restituisce `true`. `result expression` è qualsiasi espressione valida.  
  
 ELSE `else_result_expression`  
 Espressione restituita se nessuna operazione di confronto restituisce `true`. Se questo argomento viene omesso e nessuna operazione di confronto restituisce `true`, CASE restituisce null. `else_result_expression` è qualsiasi espressione valida. A `else_result_expression` e a ogni occorrenza di `result_expression` deve essere associato lo stesso tipo di dati o un tipo di dati convertibile in modo implicito.  
  
 WHEN `Boolean_expression`  
 È l'espressione `Boolean` valutata quando viene usato il formato CASE cercato. `Boolean_expression` è una qualsiasi espressione `Boolean` valida.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce il tipo con precedenza maggiore dal set di tipi in `result_expression` e nell'oggetto facoltativo `else_result_expression`.  
  
## <a name="remarks"></a>Osservazioni  
 L'espressione [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case è simile all'espressione case Transact-SQLTransact-SQL . È possibile usare l'espressione case per eseguire una serie di test condizionali per determinare quale espressione restituirà il risultato appropriato. Questa forma dell'espressione case si applica a una serie di una o più espressioni `Boolean` per determinare l'espressione risultante corretta.  
  
 La funzione CASE restituisce `Boolean_expression` per ogni clausola WHEN nell'ordine specificato e restituisce `result_expression` del primo oggetto `Boolean_expression` che restituisce `true`. Le espressioni rimanenti non vengono valutate. Se nessun oggetto `Boolean_expression` restituisce `true`, il motore di database restituisce `else_result_expression` se è stata specificata una clausola ELSE. In caso contrario, viene restituito un valore null.  
  
 Un'istruzione CASE non può restituire un multiset.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usata l'espressione CASE per valutare un set di espressioni `Boolean` per determinare il risultato. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura descritta in [Procedura: eseguire una query che restituisca risultati PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Vedere anche

- [Poi](then-entity-sql.md)
- [Selezionare](select-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
