---
title: '&gt; (maggiore di) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: 1449af09022a9e11be1f3627023318270adf0121
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736929"
---
# <a name="gt-greater-than-entity-sql"></a>&gt; (maggiore di) (Entity SQL)
Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore di quella a destra.  
  
## <a name="syntax"></a>Sintassi  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione valida. Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.  
  
## <a name="result-types"></a>Tipi di risultati  
 `true` se l'espressione a sinistra ha un valore maggiore di quella a destra; in caso contrario, `false`.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore di confronto > per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore maggiore di quella a destra. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a>Vedere anche
- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
