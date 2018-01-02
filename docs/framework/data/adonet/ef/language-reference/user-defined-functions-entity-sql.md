---
title: Funzioni definite dall'utente (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bf0592a3e88f4e8142f1fb0aeb1e7364d818d4ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="user-defined-functions-entity-sql"></a>Funzioni definite dall'utente (Entity SQL)
Nelle query Entity SQL sono supportate le chiamate a funzioni definite dall'utente. È possibile definire queste funzioni inline con la query (vedere [procedura: chiamare una funzione definita dall'utente](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) o come parte del modello concettuale (vedere [procedura: definire funzioni personalizzate nel modello concettuale](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)). Funzioni del modello concettuale sono definite come un comando Entity SQL nel [DefiningExpression](http://msdn.microsoft.com/en-us/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) elemento di un [funzione](http://msdn.microsoft.com/en-us/dc3beca7-55cf-4977-8db0-5064cdbab134) elemento nel modello concettuale.  
  
 Entity SQL consente di definire delle funzioni nel comando di query stesso. Il [funzione](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operatore consente di definire le funzioni inline. È possibile definire più funzioni in un singolo comando e queste funzioni possono avere lo stesso nome purché le rispettive firme siano univoche. Per altre informazioni, vedere [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
