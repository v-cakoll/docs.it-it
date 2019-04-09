---
title: Sicurezza dell'integrazione CLR in SQL Server
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 946401211d515df9ba5b9e38d7cfd10730973b64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165815"
---
# <a name="clr-integration-security-in-sql-server"></a>Sicurezza dell'integrazione CLR in SQL Server
Microsoft SQL Server fornisce l'integrazione del componente CLR di .NET Framework. L'integrazione CLR consente di possibile scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente, aggregati definiti dall'utente e funzioni con valori di tabella di flusso usando qualsiasi linguaggio di .NET Framework, inclusi Microsoft Visual Basic .NET e Microsoft Visual C#.  
  
 CLR supporta un modello di sicurezza per il codice gestito denominato CAS (Code Access Security). In questo modello, le autorizzazioni vengono concesse agli assembly in base all'evidenza fornita dal codice nei metadati. In SQL Server il modello di sicurezza basato su utente di SQL Server si integra con il modello di sicurezza basato su accesso al codice di CLR.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni sull'integrazione di CLR con SQL Server, vedere le risorse seguenti.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Sicurezza per l'accesso al codice](../../../../../docs/framework/misc/code-access-security.md)|Contiene argomenti in cui viene descritta la sicurezza dall'accesso di codice in .NET Framework.|  
|[Sicurezza dell'integrazione con CLR](/sql/relational-databases/clr-integration/security/clr-integration-security)|Viene descritto il modello di sicurezza per il codice gestito in esecuzione in SQL Server|  
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Scenari di sicurezza delle applicazioni in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [Integrazione di Common Language Runtime di SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)
- [Cenni preliminari su ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)
