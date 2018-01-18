---
title: EXISTS (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 225487f6a0d7ec29689c01dd6355e7ba1aa6883e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="exists-entity-sql"></a>EXISTS (Entity SQL)
Determina se una raccolta è vuota.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione valida che restituisce una raccolta.  
  
 NOT  
 Specifica la negazione del risultato di EXISTS.  
  
## <a name="return-value"></a>Valore restituito  
 `true` se la raccolta non è vuota; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 EXISTS è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra. Per informazioni sulla priorità per il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori sui set, vedere [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore EXISTS per determinare se la raccolta è vuota. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
