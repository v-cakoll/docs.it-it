---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: b3fc2484e80b637ed5841375985f7bae476bbbf7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150200"
---
# <a name="isnull-entity-sql"></a>ISNULL (Entity SQL)
Consente di determinare se un'espressione di query è null.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione di query valida. Non può trattarsi di una raccolta, includere membri di una raccolta o essere un tipo di record con proprietà di un tipo di raccolta.  
  
 NOT  
 Nega il risultato EDM.Boolean di IS NULL.  
  
## <a name="return-value"></a>Valore restituito  
 `true` se `expression` restituisce null; in caso contrario, `false`.  
  
## <a name="remarks"></a>Osservazioni  
 Usare `IS NULL` per determinare se l'elemento di un outer join è null:  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 Usare `IS NULL` per determinare se un membro ha un valore effettivo:  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 Nella tabella seguente viene illustrato il comportamento di `IS NULL` con alcuni modelli. Tutte le eccezioni vengono generate sul lato client prima che il provider venga richiamato:  
  
|Modello|Comportamento|  
|-------------|--------------|  
|null IS NULL|Restituisce `true`.|  
|TREAT (null AS EntityType) IS NULL|Restituisce `true`.|  
|TREAT (null AS ComplexType) IS NULL|Genera un errore.|  
|TREAT (null AS RowType) IS NULL|Genera un errore.|  
|EntityType IS NULL|Restituisce `true` o `false`.|  
|ComplexType IS NULL|Genera un errore.|  
|RowType IS NULL|Genera un errore.|  
  
## <a name="example"></a>Esempio  
 La [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query seguente utilizza l'operatore IS NOT NULL per determinare se un'espressione di query non è null. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
