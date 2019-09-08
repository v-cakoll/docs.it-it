---
title: Notifiche di query in SQL Server
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 94171c8dac59fc17b0dd699d87fc043651fa5b7a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791763"
---
# <a name="query-notifications-in-sql-server"></a>Notifiche di query in SQL Server
Basate sull'infrastruttura Service Broker, le notifiche di query consentono di inviare notifiche alle applicazioni quando i dati vengono modificati. Questa funzionalità è particolarmente utile per le applicazioni che forniscono una cache di informazioni da un database, ad esempio un'applicazione Web, e che richiedono una notifica quando i dati di origine vengono modificati.  
  
 Sono disponibili tre metodi per implementare le notifiche di query usando ADO.NET:  
  
1. L'implementazione di basso livello è fornita dalla classe `SqlNotificationRequest` che espone la funzionalità sul lato server e consente di eseguire un comando con una richiesta di notifica.  
  
2. L'implementazione di alto livello è fornita dalla classe `SqlDependency`, che consente un'astrazione di alto livello della funzionalità di notifica tra l'applicazione di origine e SQL Server, permettendo di usare una dipendenza per rilevare le modifiche nel server. Nella maggior parte dei casi si tratta del modo più semplice ed efficace per sfruttare la funzionalità di notifica di SQL Server in applicazioni client gestite usando il provider di dati .NET Framework per SQL Server.  
  
3. Nelle applicazioni Web compilate con ASP.NET 2.0 o versione successiva è inoltre possibile usare le classi helper `SqlCacheDependency`.  
  
 Le notifiche di query vengono usate per applicazioni che richiedono l'aggiornamento delle visualizzazioni o delle cache in seguito a modifiche dei dati sottostanti. Microsoft SQL Server consente ad applicazioni .NET Framework di inviare un comando a SQL Server e di richiedere che venga generata una notifica se l'esecuzione del comando produrrebbe set di risultati diversi da quelli recuperati inizialmente. Le notifiche generate nel server vengono inviate tramite code per l'elaborazione successiva.  
  
 È possibile impostare le notifiche per le istruzioni SELECT ed EXECUTE. Quando si usa un'istruzione EXECUTE, SQL Server registra una notifica per il comando eseguito anziché per l'istruzione EXECUTE stessa. Il comando deve soddisfare i requisiti e le limitazioni previste per un'istruzione SELECT. Quando un comando che registra una notifica contiene più di un'istruzione, il Motore di database crea una notifica per ogni istruzione inclusa nel batch.  
  
 Se si sta sviluppando un'applicazione in cui sono necessarie notifiche di sottosecondo affidabili in caso di modifica dei dati, vedere le sezioni **pianificazione di una strategia efficiente** per le notifiche delle query e **alternative alle notifiche delle query** nella [pianificazione di ](https://go.microsoft.com/fwlink/?LinkId=211984)Argomento delle notifiche in documentazione online di SQL Server. Per altre informazioni sulle notifiche di query e su SQL Server Service Broker, vedere i collegamenti seguenti agli argomenti della documentazione online di SQL Server.  
  
 **Documentazione di SQL Server**  
  
- [Utilizzo delle notifiche di query](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))  
  
- [Creazione di una query per la notifica](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Sviluppo (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))  
  
- [Centro informazioni per sviluppatori Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Guida per gli sviluppatori (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="in-this-section"></a>In questa sezione  
 [Abilitazione di notifiche di query](enabling-query-notifications.md)  
 Viene descritto come usare le notifiche di query, compresi i requisiti per l'abilitazione e l'uso.  
  
 [SqlDependency in un'applicazione ASP.NET](sqldependency-in-an-aspnet-app.md)  
 Viene illustrato come usare le notifiche di query da un'applicazione ASP.NET.  
  
 [Rilevamento di modifiche con SqlDependency](detecting-changes-with-sqldependency.md)  
 Viene illustrato come rilevare i casi in cui i risultati delle query saranno diversi da quelli ricevuti in origine.  
  
 [Esecuzione di SqlCommand con SqlNotificationRequest](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 Viene illustrata la configurazione di un oggetto <xref:System.Data.SqlClient.SqlCommand> da usare con una notifica di query.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 Vengono descritti la classe <xref:System.Data.Sql.SqlNotificationRequest> e tutti i relativi membri.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 Vengono descritti la classe <xref:System.Data.SqlClient.SqlDependency> e tutti i relativi membri.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 Vengono descritti la classe <xref:System.Web.Caching.SqlCacheDependency> e tutti i relativi membri.  
  
## <a name="see-also"></a>Vedere anche

- [SQL Server e ADO.NET](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
