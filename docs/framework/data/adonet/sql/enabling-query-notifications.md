---
title: Abilitazione di notifiche di query
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 0c377e02d5be7cb4de41d62b1e3734f790115086
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651219"
---
# <a name="enabling-query-notifications"></a>Abilitazione di notifiche di query
Le applicazioni che usano le notifiche di query dispongono di un set comune di requisiti. L'origine dati dell'utente deve essere configurata correttamente per supportare le notifiche di query SQL e l'utente deve disporre delle autorizzazioni corrette sia sul lato client che sul lato server.  
  
 Per usare le notifiche di query è necessario:  
  
- Abilitare le notifiche di query per il proprio database.  
  
- Assicurarsi che l'identificatore utente usato per connettersi al database disponga delle autorizzazioni necessarie.  
  
- Usare un oggetto <xref:System.Data.SqlClient.SqlCommand> per eseguire un'istruzione SELECT valida con un oggetto notifica associato, sia <xref:System.Data.SqlClient.SqlDependency> o <xref:System.Data.Sql.SqlNotificationRequest>.  
  
- Fornire il codice per eseguire la notifica se i dati monitorati vengono modificati.  
  
## <a name="query-notifications-requirements"></a>Requisiti delle notifiche di query  
 Le notifiche di query sono supportate solo per le istruzioni SELECT che soddisfano un elenco di specifici requisiti. Nella tabella seguente sono forniti i collegamenti alla documentazione sulle notifiche di query e Service Broker disponibili nella documentazione online di SQL Server.  
  
 **Documentazione di SQL Server**  
  
- [Creazione di una Query per la notifica](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))  
  
- [Considerazioni sulla sicurezza per Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))  
  
- [Sicurezza e protezione (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))  
  
- [Considerazioni sulla sicurezza per Notification Services](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))  
  
- [Autorizzazioni di notifica delle query](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))  
  
- [Considerazioni sulle funzionalità internazionali di Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))  
  
- [Considerazioni sulla progettazione di soluzioni (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))  
  
- [Centro informazioni per sviluppatori di Service Broker](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))  
  
- [Guida per sviluppatori (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a>Abilitazione delle notifiche di query per l'esecuzione di codice di esempio  
 Per abilitare Service Broker nel **AdventureWorks** database usando SQL Server Management Studio, eseguire l'istruzione Transact-SQL seguente:  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 Per una corretta esecuzione degli esempi di notifica di query, nel server database devono essere eseguite le seguenti istruzioni Transact-SQL:  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a>Autorizzazioni per le notifiche di query  
 Se si eseguono comandi che richiedono notifiche, è necessario disporre dell'autorizzazione di database SUBSCRIBE QUERY NOTIFICATIONS sul server.  
  
 Per il codice lato client che viene eseguito in una situazione di attendibilità parziale è richiesto il tipo <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 Nel codice seguente viene creato un oggetto <xref:System.Data.SqlClient.SqlClientPermission>, impostando <xref:System.Security.Permissions.PermissionState> su <xref:System.Security.Permissions.PermissionState.Unrestricted>. Il metodo <xref:System.Security.CodeAccessPermission.Demand%2A> forzerà un'eccezione <xref:System.Security.SecurityException> in fase di esecuzione se l'autorizzazione non è stata concessa a tutti i chiamanti della parte superiore dello stack di chiamate.  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a>Scelta di un oggetto di notifica  
 L'API per la notifica di query fornisce due oggetti per l'elaborazione delle notifiche: <xref:System.Data.SqlClient.SqlDependency> e <xref:System.Data.Sql.SqlNotificationRequest>. In genere, la maggior parte delle applicazioni non ASP.NET dovrebbe usare l'oggetto <xref:System.Data.SqlClient.SqlDependency>. Le applicazioni ASP.NET dovrebbero usare il tipo <xref:System.Web.Caching.SqlCacheDependency> di livello più alto, che incapsula il tipo  <xref:System.Data.SqlClient.SqlDependency> e fornisce un framework per l'amministrazione degli oggetti notifica e cache.  
  
### <a name="using-sqldependency"></a>Uso di SqlDependency  
 Per usare il tipo <xref:System.Data.SqlClient.SqlDependency>, è necessario che Service Broker sia abilitato per il database SQL Server usato e che gli utenti dispongano dell'autorizzazioni appropriate ricevere notifiche. Gli oggetti Service Broker, ad esempio la coda delle notifiche, sono predefiniti.  
  
 Inoltre, <xref:System.Data.SqlClient.SqlDependency> avvia automaticamente un thread di lavoro per elaborare le notifiche man mano che queste vengono inviate alla coda e analizza il messaggio Service Broker esponendo le informazioni come dati dell'argomento dell'evento. <xref:System.Data.SqlClient.SqlDependency> deve essere inizializzato chiamando il metodo `Start` per stabilire una dipendenza dal database. Si tratta di un metodo statico che deve essere chiamato una sola volta durante l'inizializzazione dell'applicazione per ciascuna connessione al database richiesta. È quindi necessario chiamare il metodo `Stop` al termine di un'applicazione per ogni connessione della dipendenza effettuata.  
  
### <a name="using-sqlnotificationrequest"></a>Uso di SqlNotificationRequest  
 Al contrario, il tipo <xref:System.Data.Sql.SqlNotificationRequest> richiede l'implementazione dell'intera infrastruttura di ascolto da parte dell'utente. Inoltre, devono essere definiti tutti gli oggetti Service Broker di supporto quali la coda, il servizio e i tipi di messaggio supportati dalla coda. Questo approccio manuale è utile se l'applicazione richiede messaggi o comportamenti di notifica speciali oppure se l'applicazione è parte di un'applicazione Service Broker più grande.  
  
## <a name="see-also"></a>Vedere anche

- [Notifiche di query in SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
