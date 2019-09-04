---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 10c5ecb2b44c85dccd758cc1cf63a152da045cc1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251076"
---
# <a name="deref-entity-sql"></a>DEREF (Entity SQL)
Consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta.  
  
## <a name="return-value"></a>Valore restituito  
 Valore dell'entità di cui viene risolto il riferimento.  
  
## <a name="remarks"></a>Note  
 L'operatore DEREF consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione. Se `r` , ad esempio, è un riferimento di tipo\<ref T > `Deref(r)` , è un'espressione di `T` tipo che restituisce l'entità a cui fa `r`riferimento. Se il valore di riferimento è Null o è inesatto, ovvero la destinazione del riferimento non esiste, il risultato dell'operatore DEREF è Null.  
  
## <a name="example"></a>Esempio  
 Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore DEREF per dereferenziare un valore di riferimento e viene restituito il risultato di tale operazione. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-primitivetype-results.md)di PrimitiveType.  
  
2. Passare la query seguente come argomento al metodo ExecutePrimitiveTypeQuery:  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [REF](ref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [Tipi strutturati nullable](nullable-structured-types-entity-sql.md)
