---
title: '!= (diverso da) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: 3f6f66d38eb9650e1adb06fa3ef5edbccf110374
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319505"
---
# <a name="-not-equal-to-entity-sql"></a>!= (diverso da) (Entity SQL)
Consente di confrontare due espressioni per determinare se l'espressione a sinistra è diversa da quella a destra. L'operatore !=(diverso da) equivale dal punto di vista funzionale all'operatore <>.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
expression != expression  
-- or  
expression <> expression  
```  
  
## <a name="arguments"></a>argomenti  
 `expression`  
 Qualsiasi espressione valida. Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.  
  
## <a name="result-types"></a>Tipi di risultati  
 `true` se l'espressione a sinistra è diversa da quella a destra; in caso contrario, `false`.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore != per confrontare due espressioni e determinare se l'espressione a sinistra è diversa da quella a destra. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#NOT_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not_equals)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
