---
title: Paging (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
ms.openlocfilehash: dcde0b74bb3ec845dba4ddfe0a5e389e46bd1c8a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64641758"
---
# <a name="paging-entity-sql"></a>Paging (Entity SQL)
Paging fisico può essere eseguito utilizzando il [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) e [limite](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sottoclausole nel [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clausola. Per eseguire il paging fisico in modo deterministico, è consigliabile usare SKIP e LIMIT. Se si desidera solo limitare il numero di righe nel risultato in modo non deterministico, è necessario utilizzare [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md). TOP e SKIP/LIMIT si escludono a vicenda.  
  
## <a name="top-overview"></a>Panoramica su TOP  
 La clausola SELECT può includere una sottoclausola TOP facoltativa dopo il modificatore ALL/DISTINCT facoltativo. La sottoclausola TOP specifica che verrà restituito solo il primo rowset del risultato della query. Per altre informazioni, vedere [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md).  
  
## <a name="skip-and-limit-overview"></a>Panoramica su SKIP e LIMIT  
 SKIP e LIMIT fanno parte della clausola ORDER BY. Se una sottoclausola dell'espressione SKIP è presente in una clausola ORDER BY, i risultati verranno ordinati in base alla specifica di ordinamento e il set di risultati includerà le righe a partire dalla riga immediatamente successiva all'espressione SKIP. SKIP 5, ad esempio, consente di ignorare le prime cinque righe e restituisce le righe a partire dalla sesta in avanti. Se una sottoclausola dell'espressione LIMIT è presente in una clausola ORDER BY, la query verrà ordinata in base alla specifica di ordinamento e il numero risultante di righe sarà limitato dall'espressione LIMIT. LIMIT 5, ad esempio, limiterà il set di risultati a cinque istanze o righe. SKIP e LIMIT non devono essere usate insieme. Con la clausola ORDER BY è possibile usare solo SKIP o LIMIT. Per altre informazioni, vedere i seguenti argomenti:  
  
- [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
- [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Procedura: Spostarsi tra i risultati della Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
