---
title: Parametri (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bb631a752bfe0e741b654ec6774a14c82c89157c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="parameters-entity-sql"></a>Parametri (Entity SQL)
I parametri sono variabili definite esternamente a [!INCLUDE[esql](../../../../../../includes/esql-md.md)], generalmente tramite un'API di associazione usata da un linguaggio host. Ogni parametro è associato a un nome e un tipo. I nomi dei parametri sono definiti nelle espressioni di query con il simbolo chiocciola (@) come prefisso. Questo consente di distinguerli dai nomi di proprietà o dagli altri nomi definiti nella query.  
  
 L'API di associazione del linguaggio host fornisce le API per l'associazione dei parametri.  
  
## <a name="example"></a>Esempio  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
