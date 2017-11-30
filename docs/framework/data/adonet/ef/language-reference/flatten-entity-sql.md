---
title: FLATTEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 226f7fa14331ee8e2500ac91a665e86928e37f8f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="flatten-entity-sql"></a>FLATTEN (Entity SQL)
Converte una raccolta di raccolte in una raccolta bidimensionale. La nuova raccolta contiene tutti gli stessi elementi di quella vecchia, ma senza una struttura annidata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a>Argomenti  
 `collection`  
 Qualsiasi espressione valida che restituisce una raccolta di valori da inserire in un'unica raccolta bidimensionale.  
  
## <a name="remarks"></a>Note  
 `FLATTEN` è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra. Vedere [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) per informazioni sulla priorità per il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori sui set.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore `FLATTEN` per convertire una raccolta di raccolte in una raccolta bidimensionale. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
