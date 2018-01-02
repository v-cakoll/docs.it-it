---
title: Paging (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4aefa7bf9d70f704d24ecd60d4958c96ed412eaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="paging-entity-sql"></a>Paging (Entity SQL)
Il paging fisico può essere eseguito tramite il [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) e [limite](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sottoclausole nel [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clausola. Per eseguire il paging fisico in modo deterministico, è consigliabile usare SKIP e LIMIT. Se si desidera solo limitare il numero di righe nel risultato in modo non deterministico, è necessario utilizzare [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md). TOP e SKIP/LIMIT si escludono a vicenda.  
  
## <a name="top-overview"></a>Panoramica su TOP  
 La clausola SELECT può includere una sottoclausola TOP facoltativa dopo il modificatore ALL/DISTINCT facoltativo. La sottoclausola TOP specifica che verrà restituito solo il primo rowset del risultato della query. Per ulteriori informazioni, vedere [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## <a name="skip-and-limit-overview"></a>Panoramica su SKIP e LIMIT  
 SKIP e LIMIT fanno parte della clausola ORDER BY. Se una sottoclausola dell'espressione SKIP è presente in una clausola ORDER BY, i risultati verranno ordinati in base alla specifica di ordinamento e il set di risultati includerà le righe a partire dalla riga immediatamente successiva all'espressione SKIP. SKIP 5, ad esempio, consente di ignorare le prime cinque righe e restituisce le righe a partire dalla sesta in avanti. Se una sottoclausola dell'espressione LIMIT è presente in una clausola ORDER BY, la query verrà ordinata in base alla specifica di ordinamento e il numero risultante di righe sarà limitato dall'espressione LIMIT. LIMIT 5, ad esempio, limiterà il set di risultati a cinque istanze o righe. SKIP e LIMIT non devono essere usate insieme. Con la clausola ORDER BY è possibile usare solo SKIP o LIMIT. Per altre informazioni, vedere i seguenti argomenti:  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Procedura: spostarsi tra Query i risultati](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)
