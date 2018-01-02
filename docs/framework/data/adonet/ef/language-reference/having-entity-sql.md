---
title: HAVING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 92949205801e5bc498fdaaa67c2fa228140a2eb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="having-entity-sql"></a>HAVING (Entity SQL)
Specifica una condizione di ricerca per un gruppo o un'aggregazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a>Argomenti  
 `search_condition`  
 Specifica la condizione di ricerca che il gruppo o l'aggregazione deve soddisfare. Se viene usata assieme alla clausola GROUP BY ALL, la clausola HAVING è prioritaria rispetto a ALL.  
  
## <a name="remarks"></a>Note  
 La clausola HAVING viene usata per specificare una condizione di filtro aggiuntiva sul risultato di un raggruppamento. Se non viene specificata alcuna clausola GROUP BY nell'espressione di query, viene presupposto un gruppo con singolo set implicito.  
  
> [!NOTE]
>  HAVING può essere utilizzato solo con il [selezionare](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) istruzione. Quando [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) non è utilizzato, HAVING si comporta come una clausola WHERE.  
  
 La clausola HAVING funziona come la clausola WHERE eccetto per il fatto che viene applicata dopo l'operazione GROUP BY. Questo significa che la clausola HAVING può fare riferimento solo alle aggregazioni e agli alias di raggruppamento, come illustrato nell'esempio seguente.  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 L'esempio precedente consente di limitare i gruppi esclusivamente a quelli che includono più di un prodotto.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente vengono usati gli operatori HAVING e GROUP BY per specificare una condizione di ricerca per un gruppo o un'aggregazione. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Attenersi alla procedura di [procedura: eseguire una Query che restituisce risultati di PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Espressioni di query](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
