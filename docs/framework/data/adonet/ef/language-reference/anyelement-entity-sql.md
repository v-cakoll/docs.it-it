---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 4dcbb80a9a850d193bfa88265a27a43c26869afe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196157"
---
# <a name="anyelement-entity-sql"></a>ANYELEMENT (Entity SQL)
Estrae un elemento da una raccolta multivalore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta da cui estrarre un elemento.  
  
## <a name="return-value"></a>Valore restituito  
 Singolo elemento nella raccolta o elemento arbitrario se nella raccolta ne è presente più di uno; se la raccolta è vuota, restituisce `null`. Se `collection` è una raccolta di tipo `Collection<T>`, quindi `ANYELEMENT(collection)` è un'espressione valida che produce un'istanza del tipo `T`.  
  
## <a name="remarks"></a>Note  
 ANYELEMENT estrae un elemento arbitrario da una raccolta multivalore. Nell'esempio seguente viene ad esempio eseguito un tentativo di estrarre un elemento singleton dal set `Customers`.  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a>Esempio  
 Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore ANYELEMENT per estrarre un elemento da una raccolta multivalore. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Tipi strutturati nullable](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
