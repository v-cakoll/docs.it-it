---
title: Spazi dei nomi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 7f05067c4bdb859f3661f775c2502852b6658522
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319566"
---
# <a name="namespaces-entity-sql"></a>Spazi dei nomi (Entity SQL)
In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono introdotti gli spazi dei nomi per evitare conflitti di nome per gli identificatori globali, ad esempio nomi di tipi, set di entità, funzioni e così via. Il supporto dello spazio dei nomi in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è simile al supporto dello spazio dei nomi nel .NET Framework.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce due tipi di clausola USING: spazi dei nomi qualificati (dove viene fornito un alias più breve per lo spazio dei nomi) e spazi dei nomi non qualificati, come illustrato nell'esempio seguente:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Regole per la risoluzione dei nomi  
 Se non è possibile risolvere un identificatore negli ambiti locali, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta di individuare il nome negli ambiti globali (spazi dei nomi). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta innanzitutto di confrontare l'identificatore (prefisso) con uno degli spazi dei nomi qualificati. Se esiste una corrispondenza, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta di risolvere il resto dell'identificatore nello spazio dei nomi specificato. Se non viene trovata alcuna corrispondenza, viene generata un'eccezione .  
  
 Successivamente, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta di cercare nell'identificatore tutti gli spazi dei nomi non qualificati (specificati nel prologo). Se l'identificatore può essere individuato esattamente in uno spazio dei nomi, viene restituito tale percorso. Se la corrispondenza per l'identificatore è presente in più di uno spazio dei nomi, viene generata un'eccezione. Se non è possibile identificare uno spazio dei nomi per l'identificatore, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passa il nome al successivo ambito esterno (l'oggetto <xref:System.Data.Common.DbCommand> o <xref:System.Data.Common.DbConnection>), come illustrato nell'esempio seguente:  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Differenze rispetto a .NET Framework  
 Nella .NET Framework è possibile utilizzare spazi dei nomi parzialmente qualificati. Ciò non è consentito in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="adonet-usage"></a>Uso di ADO.NET  
 Le query sono espresse attraverso oggetti <xref:System.Data.Common.DbCommand> ADO.NET. Gli oggetti <xref:System.Data.Common.DbCommand> possono essere creati in base a oggetti <xref:System.Data.Common.DbConnection>. Anche gli spazi dei nomi possono essere specificati come parte degli oggetti <xref:System.Data.Common.DbCommand> e <xref:System.Data.Common.DbConnection>. Se [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non è in grado di risolvere un identificatore all'interno della query stessa, gli spazi dei nomi esterni vengono sottoposto a Probe (in base a regole analoghe).  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Panoramica di Entity SQL](entity-sql-overview.md)
