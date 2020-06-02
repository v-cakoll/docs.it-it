---
title: Notifiche di query in SQL Server
description: Informazioni su come usare le notifiche di query per notificare alle applicazioni quando i dati sono stati modificati in un database di SQL Server, ad esempio, per aggiornare le visualizzazioni dell'applicazione.
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 1351c83b6cc5837115321d53e8779c0f364c3099
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286223"
---
# <a name="query-notifications-in-sql-server"></a>Notifiche di query in SQL Server
Basate sull'infrastruttura di Service Broker, tali notifiche consentono di comunicare alle applicazioni che i dati sono stati modificati. Questa caratteristica è particolarmente utile per le applicazioni che forniscono una cache di informazioni provenienti da un database, ad esempio un'applicazione Web, e devono essere notificate quando i dati di origine vengono modificati.  
  
 Esistono tre modi per implementare le notifiche delle query tramite ADO.NET:  
  
1. L'implementazione di basso livello viene offerta dalla classe `SqlNotificationRequest` che espone la funzionalità lato server, consentendo di eseguire un comando con una richiesta di notifica.  
  
2. L'implementazione di alto livello viene offerta dalla classe `SqlDependency`, ovvero una classe che offre un'astrazione di alto livello della funzionalità di notifica tra l'applicazione di origine e SQL Server, consentendo di usare una dipendenza per rilevare le modifiche nel server. Nella maggior parte dei casi si tratta del modo più semplice ed efficace per sfruttare la funzionalità di notifica di SQL Server in applicazioni client gestite usando il provider di dati .NET Framework per SQL Server.  
  
3. Inoltre, nelle applicazioni Web create con ASP.NET 2.0 o versioni successive è possibile usare le classi helper `SqlCacheDependency`.  
  
 Le notifiche delle query sono utili per applicazioni che richiedono l'aggiornamento delle visualizzazioni o delle cache in seguito a modifiche dei dati sottostanti. Microsoft SQL Server consente ad applicazioni .NET Framework di inviare un comando a SQL Server e di richiedere che venga generata una notifica se l'esecuzione del comando produrrebbe set di risultati diversi da quelli recuperati inizialmente. Le notifiche generate nel server vengono inviate tramite code in modo da essere elaborate in un secondo momento.  
  
 È possibile impostare le notifiche per le istruzioni SELECT e EXECUTE. Quando si usa un'istruzione EXECUTE, SQL Server registra una notifica del comando eseguito anziché l'istruzione EXECUTE stessa. Il comando deve soddisfare i requisiti e le limitazioni per un'istruzione SELECT. Se un comando che registra una notifica contiene più istruzioni, il motore di database crea una notifica per ogni istruzione del batch.  
  
 Se si sviluppa un'applicazione in cui sono necessarie notifiche di sottosecondo affidabili in caso di modifica dei dati, vedere le sezioni **pianificazione di una strategia efficiente** per le notifiche delle query e **alternative alle notifiche delle query** nell'articolo [pianificazione di notifiche](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) . Per ulteriori informazioni sulle notifiche di query e SQL Server Service Broker, vedere i collegamenti seguenti agli articoli della documentazione di SQL Server.  
  
 **Documentazione di SQL Server**  
  
- [Uso delle notifiche delle query](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
- [Creazione di una query da notificare](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Sviluppo (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
- [Centro informazioni per lo sviluppatore di Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Guida per gli sviluppatori di Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Abilitazione di notifiche di query](enabling-query-notifications.md)  
 Illustra come usare le notifiche delle query, inclusi i requisiti per abilitarle e usarle.  
  
 [SqlDependency in un'applicazione ASP.NET](sqldependency-in-an-aspnet-app.md)  
 Viene illustrato l'uso delle notifiche di query da un'applicazione ASP.NET.  
  
 [Rilevamento delle modifiche con SqlDependency](detecting-changes-with-sqldependency.md)  
 Viene illustrato come rilevare il momento in cui i risultati della query si differenziano da quelli ricevuti in origine.  
  
 [Esecuzione di SqlCommand con SqlNotificationRequest](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Illustra la configurazione di un oggetto <xref:System.Data.SqlClient.SqlCommand> da usare con una notifica delle query.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 Descrive la classe <xref:System.Data.Sql.SqlNotificationRequest> e tutti i relativi membri.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Descrive la classe <xref:System.Data.SqlClient.SqlDependency> e tutti i relativi membri.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Descrive la classe <xref:System.Web.Caching.SqlCacheDependency> e tutti i relativi membri.  
  
## <a name="see-also"></a>Vedere anche

- [SQL Server e ADO.NET](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
