---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 8c93e68095a0e0ff63532f53152f166d6c3d047c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150093"
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)
Combina due espressioni `Boolean` .  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
boolean_expression OR boolean_expression  
-- or
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `boolean_expression`  
 Qualsiasi espressione valida che restituisce un valore `Boolean`.  
  
## <a name="return-value"></a>Valore restituito  
 `true` se una delle condizioni è `true`; in caso contrario `false`.  
  
## <a name="remarks"></a>Osservazioni  
 OR è un operatore logico [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usato per combinare due condizioni. Quando un'istruzione include più operatori logici, gli operatori OR vengono valutati dopo gli operatori AND. È tuttavia possibile modificare l'ordine di valutazione tramite l'utilizzo delle parentesi.  
  
 Le barre verticali doppie (&#124;&#124;) hanno la stessa funzionalità dell'operatore OR.  
  
 Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore OR per combinare due espressioni `Boolean` . La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
