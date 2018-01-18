---
title: Semantica di confronto (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c6d22b72e05e6293a7fd3bcf7ddfba6e116e441f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="comparison-semantics-entity-sql"></a>Semantica di confronto (Entity SQL)
L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:  
  
## <a name="explicit-comparison"></a>Confronto esplicito  
 Operazioni di uguaglianza:  
  
-   =  
  
-   !=  
  
 Operazioni di ordinamento:  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 Operazioni di impostazione del supporto dei valori Null:  
  
-   IS NULL  
  
-   IS NOT NULL  
  
## <a name="explicit-distinction"></a>Distinzione esplicita  
 Distinzione di uguaglianza:  
  
-   DISTINCT  
  
-   GROUP BY  
  
 Distinzione di ordinamento:  
  
-   ORDER BY  
  
## <a name="implicit-distinction"></a>Distinzione implicita  
 Predicati e operazioni sui set (uguaglianza):  
  
-   UNION  
  
-   INTERSECT  
  
-   EXCEPT  
  
-   SET  
  
-   OVERLAPS  
  
 Predicati degli elementi (uguaglianza):  
  
-   IN  
  
## <a name="supported-combinations"></a>Combinazioni supportate  
 Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:  
  
|**Type**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**È NULL**<br /><br /> **NON È NULL**|  
|-|-|-|-|-|-|-|-|  
|Tipo di entità|Ref<sup>1</sup>|Tutte le proprietà<sup>2</sup>|Tutte le proprietà<sup>2</sup>|Tutte le proprietà<sup>2</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Ref<sup>1</sup>|  
|Tipo complesso|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|  
|Riga|Tutte le proprietà<sup>4</sup>|Tutte le proprietà<sup>4</sup>|Tutte le proprietà<sup>4</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Tutte le proprietà<sup>4</sup>|Generare<sup>3</sup>|  
|Tipo primitivo|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|  
|Multiset|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|  
|Rif|Sì<sup>5</sup>|Sì<sup>5</sup>|Sì<sup>5</sup>|Sì<sup>5</sup>|Throw|Throw|Sì<sup>5</sup>|  
|Associazione<br /><br /> tipo|Generare<sup>3</sup>|Throw|Throw|Throw|Generare<sup>3</sup>|Generare<sup>3</sup>|Generare<sup>3</sup>|  
  
 <sup>1</sup>vengono confrontati in modo implicito i riferimenti delle istanze di tipo di entità specificato, come illustrato nell'esempio seguente:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Un'istanza di entità non può essere confrontata con un riferimento esplicito. Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione. La query seguente comporta, ad esempio, la generazione di un'eccezione:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup>le proprietà dei tipi complessi sono impostate come bidimensionali prima dell'invio all'archivio, in modo che diventino confrontabili (fino a quando tutte le relative proprietà sono confrontabili). Vedere anche <sup>4.</sup>  
  
 <sup>3</sup>runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza ricorrere al provider o all'archivio.  
  
 <sup>4</sup>viene effettuato un tentativo di confrontare tutte le proprietà. Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.  
  
 <sup>5</sup>vengono confrontati tutti i singoli elementi dei riferimenti (che include il nome del set di entità e tutte le proprietà chiave del tipo di entità).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
