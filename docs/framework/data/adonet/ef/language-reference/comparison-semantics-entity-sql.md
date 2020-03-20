---
title: Semantica di confronto (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150454"
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
  
- È NULL  
  
- IS NOT NULL (NON È NULL)  
  
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
  
|**Tipo**|**=**<br /><br /> **!=**|**GROUP BY**<br /><br /> **Distinti**|**Unione**<br /><br /> **Intersect**<br /><br /> **Tranne**<br /><br /> **Impostare**<br /><br /> **Sovrapposizioni**|**Pollici**|**< <**<br /><br /> **> >**|**ORDINA PER**|**IS NULL**<br /><br /> **NON È NULL**|  
|-|-|-|-|-|-|-|-|  
|Tipo di entità|Riifd.<sup>1</sup>|Tutte le proprietà<sup>2</sup>|Tutte le proprietà<sup>2</sup>|Tutte le proprietà<sup>2</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Riifd.<sup>1</sup>|  
|Tipo complesso|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|  
|Riga|Tutte le proprietà<sup>4</sup>|Tutte le proprietà<sup>4</sup>|Tutte le proprietà<sup>4</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Tutte le proprietà<sup>4</sup>|Lancio<sup>3</sup>|  
|Tipo primitivo|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|Specifico del provider|  
|Multiset|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|  
|Rif|Sì<sup>5</sup>|Sì<sup>5</sup>|Sì<sup>5</sup>|Sì<sup>5</sup>|Throw|Throw|Sì<sup>5</sup>|  
|Association Rules<br /><br /> type|Lancio<sup>3</sup>|Throw|Throw|Throw|Lancio<sup>3</sup>|Lancio<sup>3</sup>|Lancio<sup>3</sup>|  
  
 <sup>1 : il</sup> nome del I riferimenti delle istanze del tipo di entità specificato vengono confrontati in modo implicito, come illustrato nell'esempio seguente:  
  
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
  
 <sup>2 Il</sup> nome del sistema Le proprietà dei tipi complessi vengono appiattite prima di essere inviate al negozio, in modo che diventino comparabili (a condizione che tutte le loro proprietà siano comparabili). Vedi anche <sup>4.</sup>  
  
 <sup>3 (COM del</sup> nome Il runtime di Entity Framework rileva il caso non supportato e genera un'eccezione significativa senza coinvolgere il provider/archivio.  
  
 <sup>4 DEL psu'</sup> Viene effettuato un tentativo di confrontare tutte le proprietà. Se è presente una proprietà che non è possibile confrontare, ad esempio un tipo text, ntext o image, viene generata un'eccezione nel server.  
  
 5 Del numero <sup>3(</sup> Vengono confrontati tutti i singoli elementi dei riferimenti (inclusi il nome del set di entità e tutte le proprietà chiave del tipo di entità).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su Entity SQL](entity-sql-overview.md)
