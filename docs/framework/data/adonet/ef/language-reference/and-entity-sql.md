---
title: '&amp;&amp;(E) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: eccad616de287a39c42e986cea84dc22feec7f70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150511"
---
# <a name="ampamp-and-entity-sql"></a>&amp;&amp;(E) (Entity SQL)
Restituisce `true` se entrambe le espressioni sono `true`; in caso contrario, restituisce `false` o `NULL`.  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
boolean_expression AND boolean_expression
```

o  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `boolean_expression`  
 Qualsiasi espressione valida che restituisce un valore Boolean.  
  
## <a name="remarks"></a>Osservazioni  
 L'utilizzo di due caratteri di e commerciale (&&) ha la stessa funzionalità dell'operatore AND.  
  
 Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|FALSE|NULL|  
|`FALSE`|FALSE|FALSE|FALSE|  
|`NULL`|NULL|FALSE|NULL|  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene illustrato come usare l'operatore AND. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
