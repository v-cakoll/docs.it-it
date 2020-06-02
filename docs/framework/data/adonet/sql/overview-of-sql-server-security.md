---
title: Cenni preliminari sulla sicurezza in SQL Server
description: Informazioni sull'architettura di sicurezza SQL Server per comprendere quali funzionalità e funzionalità contrastano le minacce note e per anticipare le minacce future.
ms.date: 03/30/2017
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
ms.openlocfilehash: c423a408e607c51c048ad08b91122a1fe06e31b2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286275"
---
# <a name="overview-of-sql-server-security"></a>Cenni preliminari sulla sicurezza in SQL Server
Una strategia di difesa in profondità, basata su livelli sovrapposti di sicurezza, costituisce il modo migliore per fronteggiare i rischi per la sicurezza. SQL Server offre un'architettura di sicurezza progettata per consentire ad amministratori e sviluppatori di database di creare applicazioni di database protette e contrastare minacce. Ogni versione di SQL Server è stata migliorata rispetto alle versioni precedenti grazie all'introduzione di nuove funzionalità. La sicurezza non può essere limitata a una o più nuove funzionalità. Ogni applicazione presenta infatti speciali requisiti di sicurezza. Gli sviluppatori devono pertanto individuare la combinazione di funzionalità più appropriate per contrastare le minacce note e prevedere eventuali minacce future.  
  
 Un'istanza di SQL Server contiene una raccolta gerarchica di entità, a partire dal server. Ogni server contiene più database, ciascuno dei quali contiene una raccolta di oggetti a protezione diretta. Ogni SQL Server entità a protezione diretta dispone di *autorizzazioni* associate che possono essere concesse a un' *entità*, ovvero un singolo, un gruppo o un processo a cui viene concesso l'accesso a SQL Server. Il Framework di sicurezza di SQL Server gestisce l'accesso alle entità a protezione diretta tramite *l'autenticazione* e l' *autorizzazione*.  
  
- L'autenticazione è il processo di accesso a SQL Server, in base al quale un'entità di sicurezza richiede l'accesso inviando credenziali che vengono valutate dal server. L'autenticazione consente di stabilire l'identità dell'utente o del processo da autenticare.  
  
- L'autorizzazione è il processo volto a determinare le risorse a protezione diretta accessibili per un'entità di sicurezza e quali operazioni sono consentite per le risorse.  
  
 Negli argomenti in questa sezione vengono illustrati gli elementi fondamentali della sicurezza di SQL Server e vengono forniti collegamenti agli argomenti completi della versione pertinente della documentazione online di SQL Server.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Autenticazione in SQL Server](authentication-in-sql-server.md)  
 Vengono descritti gli account di accesso e l'autenticazione in SQL Server e vengono specificati collegamenti a risorse aggiuntive.  
  
 [Ruoli server e database in SQL Server](server-and-database-roles-in-sql-server.md)  
 Vengono descritti i ruoli predefiniti del database e del server, i ruoli personalizzati del database, nonché gli account predefiniti e vengono forniti i collegamenti a ulteriori risorse.  
  
 [Proprietà e separazione tra schemi e utenti in SQL Server](ownership-and-user-schema-separation-in-sql-server.md)  
 Vengono illustrate la proprietà degli oggetti e la distinzione tra schema e utente e vengono forniti i collegamenti a ulteriori risorse.  
  
 [Autorizzazioni in SQL Server](authorization-and-permissions-in-sql-server.md)  
 Viene spiegato come concedere autorizzazioni usando il principio dei privilegi minimi e vengono forniti i collegamenti a ulteriori risorse.  
  
 [Crittografia dei dati in SQL Server](data-encryption-in-sql-server.md)  
 Vengono descritte le opzioni di crittografia dei dati disponibili in SQL Server e vengono forniti i collegamenti a ulteriori risorse.  
  
 [Sicurezza dell'integrazione CLR in SQL Server](clr-integration-security-in-sql-server.md)  
 Vengono forniti i collegamenti alle risorse sulla sicurezza relative all'integrazione CLR.  
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../securing-ado-net-applications.md)
- [Sicurezza SQL Server](sql-server-security.md)
- [Scenari di sicurezza delle applicazioni in SQL Server](application-security-scenarios-in-sql-server.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
