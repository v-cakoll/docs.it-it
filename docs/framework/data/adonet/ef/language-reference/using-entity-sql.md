---
title: USING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d1a47102c7057918c981b53f920afef09b20afad
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="using-entity-sql"></a>USING (Entity SQL)
Specifica gli spazi dei nomi usati in un'espressione di query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>Argomenti  
 `alias`  
 Specifica un alias più breve con cui qualificare uno spazio dei nomi.  
  
 `namespace`  
 Qualsiasi spazio dei nomi valido.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore USING per specificare gli spazi dei nomi usati in un'espressione di query. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Attenersi alla procedura di [procedura: eseguire una Query che restituisce risultati di PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Spazi dei nomi](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
