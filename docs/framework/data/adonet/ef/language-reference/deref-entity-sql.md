---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 27fc23a2be47ea00eff20aa8d2f559af5ae90387
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833897"
---
# <a name="deref-entity-sql"></a>DEREF (Entity SQL)
Consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
SELECT DEREF ( o.expression ) FROM Table AS o;
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta.  
  
## <a name="return-value"></a>Valore restituito  
 Valore dell'entità di cui viene risolto il riferimento.  
  
## <a name="remarks"></a>Note  
 L'operatore DEREF consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione. Se, ad esempio, `r` è un riferimento di tipo ref @ no__t-1T >, `Deref(r)` è un'espressione di tipo `T` che restituisce l'entità a cui fa riferimento `r`. Se il valore di riferimento è Null o è inesatto, ovvero la destinazione del riferimento non esiste, il risultato dell'operatore DEREF è Null.  
  
## <a name="example"></a>Esempio  
 Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore DEREF per dereferenziare un valore di riferimento e viene restituito il risultato di tale operazione. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura descritta in [How per: Eseguire una query che restituisce i risultati di PrimitiveType @ no__t-0.  
  
2. Passare la query seguente come argomento al metodo ExecutePrimitiveTypeQuery:  
  
 [!code-sql[DP EntityServices Concepts#DEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#deref)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [REF](ref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [Tipi strutturati nullable](nullable-structured-types-entity-sql.md)
