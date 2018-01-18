---
title: Spazi dei nomi (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4df0cc483e922e93a8038da02248b5fdcb2e3471
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="namespaces-entity-sql"></a>Spazi dei nomi (Entity SQL)
In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono introdotti gli spazi dei nomi per evitare conflitti di nome per gli identificatori globali, ad esempio nomi di tipi, set di entità, funzioni e così via. Il supporto dello spazio dei nomi in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è simile per il supporto dello spazio dei nomi di [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce due tipi di clausola USING: spazi dei nomi qualificati (dove viene fornito un alias più breve per lo spazio dei nomi) e spazi dei nomi non qualificati, come illustrato nell'esempio seguente:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Regole per la risoluzione dei nomi  
 Se non è possibile risolvere un identificatore negli ambiti locali, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta di individuare il nome negli ambiti globali (gli spazi dei nomi). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta innanzitutto di confrontare l'identificatore (prefisso) con uno degli spazi dei nomi qualificati. Se esiste una corrispondenza, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta di risolvere il resto dell'identificatore nello spazio dei nomi specificato. Se non viene trovata alcuna corrispondenza, viene generata un'eccezione .  
  
 Successivamente, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta di cercare tutti non qualificati spazi dei nomi (specificati nel prologo) per l'identificatore. Se l'identificatore può essere individuato esattamente in uno spazio dei nomi, viene restituito tale percorso. Se la corrispondenza per l'identificatore è presente in più di uno spazio dei nomi, viene generata un'eccezione. Se nessuno spazio dei nomi può essere identificato per l'identificatore, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passa il nome all'ambito esterno successivo (il <xref:System.Data.Common.DbCommand> o <xref:System.Data.Common.DbConnection> oggetto), come illustrato nell'esempio seguente:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Differenze rispetto a .NET Framework  
 In [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] non è possibile usare spazi dei nomi parzialmente qualificati. Ciò non è consentito in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="adonet-usage"></a>Uso di ADO.NET  
 Le query sono espresse attraverso oggetti <xref:System.Data.Common.DbCommand> ADO.NET. Gli oggetti <xref:System.Data.Common.DbCommand> possono essere creati in base a oggetti <xref:System.Data.Common.DbConnection>. Anche gli spazi dei nomi possono essere specificati come parte degli oggetti <xref:System.Data.Common.DbCommand> e <xref:System.Data.Common.DbConnection>. Se [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non è possibile risolvere un identificatore all'interno della query stessa, gli spazi dei nomi esterni subiscono (in base a regole simili).  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
