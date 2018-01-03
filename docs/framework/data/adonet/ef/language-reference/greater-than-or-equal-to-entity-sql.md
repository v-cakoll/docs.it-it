---
title: '&gt;= (maggiore o uguale a) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 89e24b3e1a4b707ca60d798889538eb1bcd6a3bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="gt-greater-than-or-equal-to-entity-sql"></a>&gt;= (maggiore o uguale a) (Entity SQL)
Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra.  
  
## <a name="syntax"></a>Sintassi  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione valida. Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.  
  
## <a name="result-types"></a>Tipi di risultati  
 `true` se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra; in caso contrario, `false`.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore di confronto >= per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
