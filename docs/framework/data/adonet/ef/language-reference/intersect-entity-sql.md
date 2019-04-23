---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: 85b0abb03161b2df0cfc4ddf6cafc92fb7de9d95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296979"
---
# <a name="intersect-entity-sql"></a>INTERSECT (Entity SQL)
Restituisce una raccolta di tutti i valori distinti restituiti da entrambe le espressioni di query a sinistra e a destra dell'operando INTERSECT. Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `expression`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta da confrontare con la raccolta restituita da un'altra espressione di query.  
  
## <a name="return-value"></a>Valore restituito  
 Raccolta dello stesso tipo o di un tipo di base o derivato comune di `expression`.  
  
## <a name="remarks"></a>Note  
 INTERSECT è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra. Per informazioni sulla priorità per la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori sui set, vedere [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore INTERSECT per restituire una raccolta di tutti i valori distinti restituiti da entrambe le espressioni di query a sinistra e a destra dell'operando INTERSECT. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#INTERSECT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#intersect)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
