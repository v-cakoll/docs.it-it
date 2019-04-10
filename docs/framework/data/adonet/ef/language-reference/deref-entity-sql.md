---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 1ba562ba6542e6ab0d62f1f8348434ae4f4c9b13
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305182"
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
 L'operatore DEREF consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione. Ad esempio, se `r` è un riferimento di tipo ref\<T >, `Deref(r)` è un'espressione di tipo `T` che restituisce l'entità fa riferimento `r`. Se il valore di riferimento è Null o è inesatto, ovvero la destinazione del riferimento non esiste, il risultato dell'operatore DEREF è Null.  
  
## <a name="example"></a>Esempio  
 Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore DEREF per dereferenziare un valore di riferimento e viene restituito il risultato di tale operazione. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Passare la query seguente come argomento al metodo ExecutePrimitiveTypeQuery:  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
- [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [Tipi strutturati nullable](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
