---
title: Notifiche di query in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 854407d2e6d1341d5917cc78664c1f653e55fa35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="43118-102">Notifiche di query in SQL Server</span><span class="sxs-lookup"><span data-stu-id="43118-102">Query Notifications in SQL Server</span></span>
<span data-ttu-id="43118-103">Basate sull'infrastruttura Service Broker, le notifiche di query consentono di inviare notifiche alle applicazioni quando i dati vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="43118-103">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="43118-104">Questa funzionalità è particolarmente utile per le applicazioni che forniscono una cache di informazioni da un database, ad esempio un'applicazione Web, e che richiedono una notifica quando i dati di origine vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="43118-104">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="43118-105">Sono disponibili tre metodi per implementare le notifiche di query usando ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="43118-105">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1.  <span data-ttu-id="43118-106">L'implementazione di basso livello è fornita dalla classe `SqlNotificationRequest` che espone la funzionalità sul lato server e consente di eseguire un comando con una richiesta di notifica.</span><span class="sxs-lookup"><span data-stu-id="43118-106">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2.  <span data-ttu-id="43118-107">L'implementazione di alto livello è fornita dalla classe `SqlDependency`, che consente un'astrazione di alto livello della funzionalità di notifica tra l'applicazione di origine e SQL Server, permettendo di usare una dipendenza per rilevare le modifiche nel server.</span><span class="sxs-lookup"><span data-stu-id="43118-107">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="43118-108">Nella maggior parte dei casi si tratta del modo più semplice ed efficace per sfruttare la funzionalità di notifica di SQL Server in applicazioni client gestite usando il provider di dati .NET Framework per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43118-108">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3.  <span data-ttu-id="43118-109">Nelle applicazioni Web compilate con ASP.NET 2.0 o versione successiva è inoltre possibile usare le classi helper `SqlCacheDependency`.</span><span class="sxs-lookup"><span data-stu-id="43118-109">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="43118-110">Le notifiche di query vengono usate per applicazioni che richiedono l'aggiornamento delle visualizzazioni o delle cache in seguito a modifiche dei dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="43118-110">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="43118-111">Microsoft SQL Server consente ad applicazioni .NET Framework di inviare un comando a SQL Server e di richiedere che venga generata una notifica se l'esecuzione del comando produrrebbe set di risultati diversi da quelli recuperati inizialmente.</span><span class="sxs-lookup"><span data-stu-id="43118-111">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="43118-112">Le notifiche generate nel server vengono inviate tramite code per l'elaborazione successiva.</span><span class="sxs-lookup"><span data-stu-id="43118-112">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="43118-113">È possibile impostare le notifiche per le istruzioni SELECT ed EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="43118-113">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="43118-114">Quando si usa un'istruzione EXECUTE, SQL Server registra una notifica per il comando eseguito anziché per l'istruzione EXECUTE stessa.</span><span class="sxs-lookup"><span data-stu-id="43118-114">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="43118-115">Il comando deve soddisfare i requisiti e le limitazioni previste per un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="43118-115">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="43118-116">Quando un comando che registra una notifica contiene più di un'istruzione, il Motore di database crea una notifica per ogni istruzione inclusa nel batch.</span><span class="sxs-lookup"><span data-stu-id="43118-116">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="43118-117">Se si sviluppa un'applicazione in cui è necessario notifiche frazioni di secondo affidabili quando i dati, rivedere le sezioni **pianificazione di una strategia di notifiche di Query efficienti** e **alternative alle Query Le notifiche** nel [pianificazione per le notifiche](http://go.microsoft.com/fwlink/?LinkId=211984) argomento nella documentazione Online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43118-117">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](http://go.microsoft.com/fwlink/?LinkId=211984) topic in SQL Server Books Online.</span></span> <span data-ttu-id="43118-118">Per altre informazioni sulle notifiche di query e su SQL Server Service Broker, vedere i collegamenti seguenti agli argomenti della documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43118-118">For more information about Query Notifications and SQL Server Service Broker, see the following links to topics in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="43118-119">**Documentazione online di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="43118-119">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="43118-120">Notifiche di Query</span><span class="sxs-lookup"><span data-stu-id="43118-120">Using Query Notifications</span></span>](http://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [<span data-ttu-id="43118-121">Creazione di una Query da notificare</span><span class="sxs-lookup"><span data-stu-id="43118-121">Creating a Query for Notification</span></span>](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="43118-122">Service Broker</span><span class="sxs-lookup"><span data-stu-id="43118-122">Service Broker</span></span>](http://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [<span data-ttu-id="43118-123">Centro informazioni per sviluppatori di Service Broker</span><span class="sxs-lookup"><span data-stu-id="43118-123">Service Broker Developer InfoCenter</span></span>](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="43118-124">Sviluppo (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="43118-124">Development (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a><span data-ttu-id="43118-125">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="43118-125">In This Section</span></span>  
 [<span data-ttu-id="43118-126">Abilitazione di notifiche di Query</span><span class="sxs-lookup"><span data-stu-id="43118-126">Enabling Query Notifications</span></span>](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 <span data-ttu-id="43118-127">Viene descritto come usare le notifiche di query, compresi i requisiti per l'abilitazione e l'uso.</span><span class="sxs-lookup"><span data-stu-id="43118-127">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="43118-128">SqlDependency in un'applicazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43118-128">SqlDependency in an ASP.NET Application</span></span>](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="43118-129">Viene illustrato come usare le notifiche di query da un'applicazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="43118-129">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="43118-130">Il rilevamento delle modifiche con SqlDependency</span><span class="sxs-lookup"><span data-stu-id="43118-130">Detecting Changes with SqlDependency</span></span>](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="43118-131">Viene illustrato come rilevare i casi in cui i risultati delle query saranno diversi da quelli ricevuti in origine.</span><span class="sxs-lookup"><span data-stu-id="43118-131">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="43118-132">Esecuzione di SqlCommand con SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="43118-132">SqlCommand Execution with a SqlNotificationRequest</span></span>](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="43118-133">Viene illustrata la configurazione di un oggetto <xref:System.Data.SqlClient.SqlCommand> da usare con una notifica di query.</span><span class="sxs-lookup"><span data-stu-id="43118-133">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="43118-134">Riferimento</span><span class="sxs-lookup"><span data-stu-id="43118-134">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="43118-135">Vengono descritti la classe <xref:System.Data.Sql.SqlNotificationRequest> e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="43118-135">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="43118-136">Vengono descritti la classe <xref:System.Data.SqlClient.SqlDependency> e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="43118-136">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="43118-137">Vengono descritti la classe <xref:System.Web.Caching.SqlCacheDependency> e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="43118-137">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43118-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43118-138">See Also</span></span>  
 [<span data-ttu-id="43118-139">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="43118-139">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="43118-140">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="43118-140">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
