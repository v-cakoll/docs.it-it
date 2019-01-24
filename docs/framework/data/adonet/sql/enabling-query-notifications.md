---
title: Abilitazione di notifiche di query
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: be9cae6f702b72306875246e874b99e7c79eb113
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743036"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="7c0c1-102">Abilitazione di notifiche di query</span><span class="sxs-lookup"><span data-stu-id="7c0c1-102">Enabling Query Notifications</span></span>
<span data-ttu-id="7c0c1-103">Le applicazioni che usano le notifiche di query dispongono di un set comune di requisiti.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="7c0c1-104">L'origine dati dell'utente deve essere configurata correttamente per supportare le notifiche di query SQL e l'utente deve disporre delle autorizzazioni corrette sia sul lato client che sul lato server.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="7c0c1-105">Per usare le notifiche di query è necessario:</span><span class="sxs-lookup"><span data-stu-id="7c0c1-105">To use query notifications you must:</span></span>  
  
-   <span data-ttu-id="7c0c1-106">Abilitare le notifiche di query per il proprio database.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-106">Enable query notifications for your database.</span></span>  
  
-   <span data-ttu-id="7c0c1-107">Assicurarsi che l'identificatore utente usato per connettersi al database disponga delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
-   <span data-ttu-id="7c0c1-108">Usare un oggetto <xref:System.Data.SqlClient.SqlCommand> per eseguire un'istruzione SELECT valida con un oggetto notifica associato, sia <xref:System.Data.SqlClient.SqlDependency> o <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
-   <span data-ttu-id="7c0c1-109">Fornire il codice per eseguire la notifica se i dati monitorati vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="7c0c1-110">Requisiti delle notifiche di query</span><span class="sxs-lookup"><span data-stu-id="7c0c1-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="7c0c1-111">Le notifiche di query sono supportate solo per le istruzioni SELECT che soddisfano un elenco di specifici requisiti.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="7c0c1-112">Nella tabella seguente sono forniti i collegamenti alla documentazione sulle notifiche di query e Service Broker disponibili nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="7c0c1-113">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="7c0c1-113">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="7c0c1-114">Creazione di una Query per la notifica</span><span class="sxs-lookup"><span data-stu-id="7c0c1-114">Creating a Query for Notification</span></span>](https://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="7c0c1-115">Considerazioni sulla sicurezza per Service Broker</span><span class="sxs-lookup"><span data-stu-id="7c0c1-115">Security Considerations for Service Broker</span></span>](https://msdn.microsoft.com/library/ms166059.aspx)  
  
-   [<span data-ttu-id="7c0c1-116">Sicurezza e protezione (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="7c0c1-116">Security and Protection (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522911.aspx)  
  
-   [<span data-ttu-id="7c0c1-117">Considerazioni sulla sicurezza per Notification Services</span><span class="sxs-lookup"><span data-stu-id="7c0c1-117">Security Considerations for Notifications Services</span></span>](https://msdn.microsoft.com/library/ms172604.aspx)  
  
-   [<span data-ttu-id="7c0c1-118">Autorizzazioni di notifica delle query</span><span class="sxs-lookup"><span data-stu-id="7c0c1-118">Query Notification Permissions</span></span>](https://msdn.microsoft.com/library/ms188311.aspx)  
  
-   [<span data-ttu-id="7c0c1-119">Considerazioni sulle funzionalità internazionali di Service Broker</span><span class="sxs-lookup"><span data-stu-id="7c0c1-119">International Considerations for Service Broker</span></span>](https://msdn.microsoft.com/library/ms166028.aspx)  
  
-   [<span data-ttu-id="7c0c1-120">Considerazioni sulla progettazione di soluzioni (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="7c0c1-120">Solution Design Considerations (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522899.aspx)  
  
-   [<span data-ttu-id="7c0c1-121">Centro informazioni per sviluppatori di Service Broker</span><span class="sxs-lookup"><span data-stu-id="7c0c1-121">Service Broker Developer InfoCenter</span></span>](https://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="7c0c1-122">Guida per sviluppatori (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="7c0c1-122">Developer's Guide (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="7c0c1-123">Abilitazione delle notifiche di query per l'esecuzione di codice di esempio</span><span class="sxs-lookup"><span data-stu-id="7c0c1-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="7c0c1-124">Per abilitare Service Broker nel **AdventureWorks** database usando SQL Server Management Studio, eseguire l'istruzione Transact-SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="7c0c1-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="7c0c1-125">Per una corretta esecuzione degli esempi di notifica di query, nel server database devono essere eseguite le seguenti istruzioni Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="7c0c1-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="7c0c1-126">Autorizzazioni per le notifiche di query</span><span class="sxs-lookup"><span data-stu-id="7c0c1-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="7c0c1-127">Se si eseguono comandi che richiedono notifiche, è necessario disporre dell'autorizzazione di database SUBSCRIBE QUERY NOTIFICATIONS sul server.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="7c0c1-128">Per il codice lato client che viene eseguito in una situazione di attendibilità parziale è richiesto il tipo <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="7c0c1-129">Nel codice seguente viene creato un oggetto <xref:System.Data.SqlClient.SqlClientPermission>, impostando <xref:System.Security.Permissions.PermissionState> su <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="7c0c1-130">Il metodo <xref:System.Security.CodeAccessPermission.Demand%2A> forzerà un'eccezione <xref:System.Security.SecurityException> in fase di esecuzione se l'autorizzazione non è stata concessa a tutti i chiamanti della parte superiore dello stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="7c0c1-131">Scelta di un oggetto di notifica</span><span class="sxs-lookup"><span data-stu-id="7c0c1-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="7c0c1-132">L'API per la notifica di query fornisce due oggetti per l'elaborazione delle notifiche: <xref:System.Data.SqlClient.SqlDependency> e <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="7c0c1-133">In genere, la maggior parte delle applicazioni non ASP.NET dovrebbe usare l'oggetto <xref:System.Data.SqlClient.SqlDependency>.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="7c0c1-134">Le applicazioni ASP.NET dovrebbero usare il tipo <xref:System.Web.Caching.SqlCacheDependency> di livello più alto, che incapsula il tipo  <xref:System.Data.SqlClient.SqlDependency> e fornisce un framework per l'amministrazione degli oggetti notifica e cache.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="7c0c1-135">Uso di SqlDependency</span><span class="sxs-lookup"><span data-stu-id="7c0c1-135">Using SqlDependency</span></span>  
 <span data-ttu-id="7c0c1-136">Per usare il tipo <xref:System.Data.SqlClient.SqlDependency>, è necessario che Service Broker sia abilitato per il database SQL Server usato e che gli utenti dispongano dell'autorizzazioni appropriate ricevere notifiche.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="7c0c1-137">Gli oggetti Service Broker, ad esempio la coda delle notifiche, sono predefiniti.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="7c0c1-138">Inoltre, <xref:System.Data.SqlClient.SqlDependency> avvia automaticamente un thread di lavoro per elaborare le notifiche man mano che queste vengono inviate alla coda e analizza il messaggio Service Broker esponendo le informazioni come dati dell'argomento dell'evento.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="7c0c1-139"><xref:System.Data.SqlClient.SqlDependency> deve essere inizializzato chiamando il metodo `Start` per stabilire una dipendenza dal database.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="7c0c1-140">Si tratta di un metodo statico che deve essere chiamato una sola volta durante l'inizializzazione dell'applicazione per ciascuna connessione al database richiesta.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="7c0c1-141">È quindi necessario chiamare il metodo `Stop` al termine di un'applicazione per ogni connessione della dipendenza effettuata.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="7c0c1-142">Uso di SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="7c0c1-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="7c0c1-143">Al contrario, il tipo <xref:System.Data.Sql.SqlNotificationRequest> richiede l'implementazione dell'intera infrastruttura di ascolto da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="7c0c1-144">Inoltre, devono essere definiti tutti gli oggetti Service Broker di supporto quali la coda, il servizio e i tipi di messaggio supportati dalla coda.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="7c0c1-145">Questo approccio manuale è utile se l'applicazione richiede messaggi o comportamenti di notifica speciali oppure se l'applicazione è parte di un'applicazione Service Broker più grande.</span><span class="sxs-lookup"><span data-stu-id="7c0c1-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0c1-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c0c1-146">See also</span></span>
- [<span data-ttu-id="7c0c1-147">Notifiche di query in SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c0c1-147">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [<span data-ttu-id="7c0c1-148">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="7c0c1-148">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
