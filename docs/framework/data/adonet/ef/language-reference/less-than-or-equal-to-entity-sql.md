---
title: < = (minore o uguale a) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: b3c8fef47b06b9fdd0a1619a9e56d3d916d9dd2d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319641"
---
# <a name="-less-than-or-equal-to-entity-sql"></a>\<= (minore o uguale a) (Entity SQL)
Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
expression <= expression  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Qualsiasi espressione valida. Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.  
  
## <a name="result-types"></a>Tipi di risultati  
 `true` se l'espressione a sinistra ha un valore minore o uguale a quella a destra; in caso contrario, `false`.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore di confronto <= per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#LESS_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less_or_equals)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
