---
title: Cenni preliminari sulla sicurezza in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ff0a78a852bdbf2fa1eb075273cad317c21fb182
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="overview-of-sql-server-security"></a>Cenni preliminari sulla sicurezza in SQL Server
Una strategia di difesa in profondità, basata su livelli sovrapposti di sicurezza, costituisce il modo migliore per fronteggiare i rischi per la sicurezza. SQL Server offre un'architettura di sicurezza progettata per consentire ad amministratori e sviluppatori di database di creare applicazioni di database protette e contrastare minacce. Ogni versione di SQL Server è stata migliorata rispetto alle versioni precedenti grazie all'introduzione di nuove funzionalità. La sicurezza non può essere limitata a una o più nuove funzionalità. Ogni applicazione presenta infatti speciali requisiti di sicurezza. Gli sviluppatori devono pertanto individuare la combinazione di funzionalità più appropriate per contrastare le minacce note e prevedere eventuali minacce future.  
  
 Un'istanza di SQL Server contiene una raccolta gerarchica di entità, a partire dal server. Ogni server contiene più database, ciascuno dei quali contiene una raccolta di oggetti a protezione diretta. Ogni entità a protezione diretta di SQL Server sono associate *autorizzazioni* che possono essere concesse a un *principale*, ovvero un singolo utente, gruppo o un processo concesso l'accesso a SQL Server. Il framework di sicurezza di SQL Server gestisce l'accesso alle entità a protezione diretta tramite *autenticazione* e *autorizzazione*.  
  
-   L'autenticazione è il processo di accesso a SQL Server, in base al quale un'entità di sicurezza richiede l'accesso inviando credenziali che vengono valutate dal server. L'autenticazione consente di stabilire l'identità dell'utente o del processo da autenticare.  
  
-   L'autorizzazione è il processo che consente di determinare le risorse ad accesso diretto accessibili a un'entità di sicurezza e le operazioni consentite a tali risorse.  
  
 Negli argomenti in questa sezione vengono illustrati gli elementi fondamentali della sicurezza di SQL Server e vengono forniti collegamenti agli argomenti completi della versione pertinente della documentazione online di SQL Server.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Autenticazione in SQL Server](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 Vengono descritti gli account di accesso e l'autenticazione di SQL Server e vengono forniti i collegamenti a ulteriori risorse.  
  
 [Ruoli server e database in SQL Server](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 Vengono descritti i ruoli predefiniti del database e del server, i ruoli personalizzati del database, nonché gli account predefiniti e vengono forniti i collegamenti a ulteriori risorse.  
  
 [Proprietà e separazione tra schemi e utenti in SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 Vengono illustrate la proprietà degli oggetti e la distinzione tra schema e utente e vengono forniti i collegamenti a ulteriori risorse.  
  
 [Autorizzazioni in SQL Server](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 Viene spiegato come concedere autorizzazioni usando il principio dei privilegi minimi e vengono forniti i collegamenti a ulteriori risorse.  
  
 [Crittografia dei dati in SQL Server](../../../../../docs/framework/data/adonet/sql/data-encryption-in-sql-server.md)  
 Vengono descritte le opzioni di crittografia dei dati disponibili in SQL Server e vengono forniti i collegamenti a ulteriori risorse.  
  
 [Sicurezza dell'integrazione CLR in SQL Server](../../../../../docs/framework/data/adonet/sql/clr-integration-security-in-sql-server.md)  
 Vengono forniti i collegamenti alle risorse sulla sicurezza relative all'integrazione CLR.  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Sicurezza di SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [Scenari di sicurezza delle applicazioni in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
