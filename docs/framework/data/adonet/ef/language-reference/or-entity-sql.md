---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 6437b17fe1c1277701f06988ef6c02f4caf70e62
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319466"
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)
Combina due espressioni `Boolean` .  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
boolean_expression OR boolean_expression  
-- or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>argomenti  
 `boolean_expression`  
 Qualsiasi espressione valida che restituisce un valore `Boolean`.  
  
## <a name="return-value"></a>Valore restituito  
 `true` se una delle condizioni è `true`; in caso contrario `false`.  
  
## <a name="remarks"></a>Note  
 OR è un operatore logico [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usato per combinare due condizioni. Quando in un'istruzione si usa più di un operatore logico, gli operatori OR vengono valutati dopo gli operatori AND. È tuttavia possibile modificare l'ordine di valutazione tramite l'uso delle parentesi.  
  
 La doppia barra verticale&#124;&#124;() ha la stessa funzionalità dell'operatore o.  
  
 Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|true|true|  
|`FALSE`|true|false|NULL|  
|`NULL`|true|NULL|NULL|  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore OR per combinare due espressioni `Boolean` . La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
