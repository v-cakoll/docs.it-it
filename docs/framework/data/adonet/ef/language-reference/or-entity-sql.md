---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: d089bcec56ff13ddcd5250a63aee6a00d0c3ef11
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760311"
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)
Combina due espressioni `Boolean` .  
  
## <a name="syntax"></a>Sintassi  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `boolean_expression`  
 Qualsiasi espressione valida che restituisce un valore `Boolean`.  
  
## <a name="return-value"></a>Valore restituito  
 `true` se una delle condizioni è `true`; in caso contrario `false`.  
  
## <a name="remarks"></a>Note  
 OR è un operatore logico [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usato per combinare due condizioni. Quando in un'istruzione si usa più di un operatore logico, gli operatori OR vengono valutati dopo gli operatori AND. È tuttavia possibile modificare l'ordine di valutazione tramite l'uso delle parentesi.  
  
 Doppia barra verticale (&#124;&#124;) hanno la stessa funzionalità dell'operatore OR.  
  
 Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore OR per combinare due espressioni `Boolean` . La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
