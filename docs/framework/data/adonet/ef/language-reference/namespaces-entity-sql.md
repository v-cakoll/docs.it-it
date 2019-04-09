---
title: Spazi dei nomi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: bef2fa96ce090a600155d68ecc3daea55b675840
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185523"
---
# <a name="namespaces-entity-sql"></a>Spazi dei nomi (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] introduce gli spazi dei nomi per evitare conflitti di nomi per gli identificatori globali, ad esempio i nomi dei tipi, i set di entità, funzioni e così via. Il supporto dello spazio dei nomi in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è simile al supporto dello spazio dei nomi nel [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce due tipi di clausola USING: completo di spazi dei nomi (in cui un alias più breve è fornito per lo spazio dei nomi) e spazi dei nomi non qualificati, come illustrato nell'esempio seguente:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Regole per la risoluzione dei nomi  
 Se un identificatore non può essere risolto negli ambiti locali, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta di individuare il nome negli ambiti globali (gli spazi dei nomi). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] prima di tutto Cerca la corrispondenza con l'identificatore (prefisso) con uno degli spazi dei nomi qualificati. Se non esiste una corrispondenza, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenterà di risolvere il resto dell'identificatore nello spazio dei nomi specificato. Se non viene trovata alcuna corrispondenza, viene generata un'eccezione .  
  
 Successivamente, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta tutte non qualificati gli spazi dei nomi (specificati nel prologo) per l'identificatore di ricerca. Se l'identificatore può essere individuato esattamente in uno spazio dei nomi, viene restituito tale percorso. Se la corrispondenza per l'identificatore è presente in più di uno spazio dei nomi, viene generata un'eccezione. Se nessuno spazio dei nomi può essere identificato per l'identificatore [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passa il nome all'ambito esterno successivo (la <xref:System.Data.Common.DbCommand> o <xref:System.Data.Common.DbConnection> oggetto), come illustrato nell'esempio seguente:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Differenze rispetto a .NET Framework  
 In [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] non è possibile usare spazi dei nomi parzialmente qualificati. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Ciò non è consentito.  
  
## <a name="adonet-usage"></a>Uso di ADO.NET  
 Le query sono espresse attraverso oggetti <xref:System.Data.Common.DbCommand> ADO.NET. <xref:System.Data.Common.DbCommand> gli oggetti possono essere compilati su <xref:System.Data.Common.DbConnection> oggetti. Anche gli spazi dei nomi possono essere specificati come parte degli oggetti <xref:System.Data.Common.DbCommand> e <xref:System.Data.Common.DbConnection>. Se [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non è possibile risolvere un identificatore all'interno della query stessa, gli spazi dei nomi esterni viene eseguito il probe (basato su regole simili).  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Cenni preliminari su Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
