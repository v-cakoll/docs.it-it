---
title: Semantica di confronto (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 8d7868b0166f0a18824ec25e6cdf639deec665ac
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833939"
---
# <a name="comparison-semantics-entity-sql"></a>Semantica di confronto (Entity SQL)
L'esecuzione di uno degli operatori [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguenti comporta un confronto tra istanze di tipi:  
  
## <a name="explicit-comparison"></a>Confronto esplicito  
 Operazioni di uguaglianza:  
  
- =  
  
- !=  
  
 Operazioni di ordinamento:  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 Operazioni di impostazione del supporto dei valori Null:  
  
- IS NULL  
  
- IS NOT NULL  
  
## <a name="explicit-distinction"></a>Distinzione esplicita  
 Distinzione di uguaglianza:  
  
- DISTINCT  
  
- GROUP BY  
  
 Distinzione di ordinamento:  
  
- ORDER BY  
  
## <a name="implicit-distinction"></a>Distinzione implicita  
 Predicati e operazioni sui set (uguaglianza):  
  
- UNION  
  
- INTERSECT  
  
- EXCEPT  
  
- SET  
  
- OVERLAPS  
  
 Predicati degli elementi (uguaglianza):  
  
- IN  
  
## <a name="supported-combinations"></a>Combinazioni supportate  
 Nella tabella seguente sono illustrate tutte le combinazioni supportate di operatori di confronto per ognuno dei tipi:  
  
|**Tipo**|**=**<br /><br /> **\!=**|**GROUP BY**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **EXCEPT**<br /><br /> **SET**<br /><br /> **OVERLAPS**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**È NULL**<br /><br /> **NON È NULL**|  
|-|-|-|-|-|-|-|-|  
|Tipo di entità|Ref<sup>1</sup>|Tutte le proprietà<sup>2</sup>|Tutte le proprietà<sup>2</sup>|Tutte le proprietà<sup>2</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Ref<sup>1</sup>|  
|Tipo complesso|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|Riga|Tutte le proprietà<sup>4</sup>|Tutte le proprietà<sup>4</sup>|Tutte le proprietà<sup>4</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Tutte le proprietà<sup>4</sup>|Throw<sup>3</sup>|  
|Tipo primitivo|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|  
|Multiset|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
|Rif|Sì<sup>5</sup>|Sì<sup>5</sup>|Sì<sup>5</sup>|Sì<sup>5</sup>|Throw|Throw|Sì<sup>5</sup>|  
|Associazione<br /><br /> type|Throw<sup>3</sup>|Throw|Throw|Throw|Throw<sup>3</sup>|Throw<sup>3</sup>|Throw<sup>3</sup>|  
  
 <sup>1</sup> I riferimenti delle istanze del tipo di entità specificate vengono confrontati in modo implicito, come illustrato nell'esempio seguente:  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Un'istanza di entità non può essere confrontata con un riferimento esplicito. Se viene eseguito un tentativo di questo tipo, viene generata un'eccezione. La query seguente comporta, ad esempio, la generazione di un'eccezione:  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup> Le proprietà dei tipi complessi sono bidimensionali prima di essere inviate all'archivio, quindi diventano confrontabili (purché tutte le relative proprietà siano confrontabili). Vedere anche <sup>4.</sup>  
  
 <sup>3</sup> Il runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza coinvolgere il provider o l'archivio.  
  
 <sup>4</sup> Viene effettuato un tentativo di confrontare tutte le proprietà. Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.  
  
 <sup>5</sup> Vengono confrontati tutti i singoli elementi dei riferimenti (inclusi il nome del set di entità e tutte le proprietà chiave del tipo di entità).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di Entity SQL](entity-sql-overview.md)
