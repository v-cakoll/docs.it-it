---
title: SqlDependency in un'applicazione ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: a93cb9da44985fa29a4975875564b384117ce76f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938461"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="dbaa5-102">SqlDependency in un'applicazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="dbaa5-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="dbaa5-103">Nell'esempio riportato in questa sezione viene illustrato l'uso di <xref:System.Data.SqlClient.SqlDependency> in modo indiretto sfruttando l'oggetto <xref:System.Web.Caching.SqlCacheDependency> di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="dbaa5-104">L'oggetto <xref:System.Web.Caching.SqlCacheDependency> usa un oggetto <xref:System.Data.SqlClient.SqlDependency> per ascoltare le notifiche e aggiornare correttamente la cache.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dbaa5-105">Il codice di esempio presuppone che siano state abilitate le notifiche delle query eseguendo gli script in Abilitazione delle [notifiche delle query](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="dbaa5-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="dbaa5-106">Informazioni sull'applicazione di esempio</span><span class="sxs-lookup"><span data-stu-id="dbaa5-106">About the Sample Application</span></span>  
 <span data-ttu-id="dbaa5-107">Nell'applicazione di esempio viene utilizzata una singola pagina Web ASP.NET per visualizzare le informazioni sul prodotto dal database AdventureWorks <xref:System.Web.UI.WebControls.GridView> SQL Server in un controllo.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="dbaa5-108">Durante il caricamento della pagina, il codice scrive l'ora corrente in un controllo <xref:System.Web.UI.WebControls.Label>.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="dbaa5-109">Viene quindi definito un oggetto <xref:System.Web.Caching.SqlCacheDependency> e vengono impostate le proprietà nell'oggetto <xref:System.Web.Caching.Cache> per archiviare i dati della cache per un massimo di tre minuti.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="dbaa5-110">Viene quindi eseguita la connessione al database e vengono recuperati i dati.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="dbaa5-111">Quando viene caricata la pagina e l'applicazione è in esecuzione, ASP.NET recupererà i dati dalla cache, come è possibile verificare osservando che l'ora della pagina rimane invariata.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="dbaa5-112">Se i dati da monitorare cambiano, ASP.NET invalida la cache e ripopola il controllo `GridView` con nuovi dati, aggiornando l'ora visualizzata nel controllo `Label`.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="dbaa5-113">Creazione dell'applicazione di esempio</span><span class="sxs-lookup"><span data-stu-id="dbaa5-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="dbaa5-114">Per creare ed eseguire l'applicazione di esempio, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="dbaa5-114">Follow these steps to create and run the sample application:</span></span>  
  
1. <span data-ttu-id="dbaa5-115">Creare un nuovo sito Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-115">Create a new ASP.NET Web site.</span></span>  
  
2. <span data-ttu-id="dbaa5-116">Aggiungere un controllo <xref:System.Web.UI.WebControls.Label> e un controllo <xref:System.Web.UI.WebControls.GridView> alla pagina Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3. <span data-ttu-id="dbaa5-117">Aprire il modulo di classe della pagina e aggiungere le direttive seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbaa5-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. <span data-ttu-id="dbaa5-118">Aggiungere il codice seguente nell'evento `Page_Load` della pagina:</span><span class="sxs-lookup"><span data-stu-id="dbaa5-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. <span data-ttu-id="dbaa5-119">Aggiungere due metodi di supporto, `GetConnectionString` e `GetSQL`.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="dbaa5-120">La stringa di connessione definita usa la sicurezza integrata.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="dbaa5-121">È necessario verificare che l'account in uso disponga delle autorizzazioni necessarie per il database e che nel database di esempio, **AdventureWorks**, siano abilitate le notifiche.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span>
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="dbaa5-122">Verifica dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="dbaa5-122">Testing the Application</span></span>  
 <span data-ttu-id="dbaa5-123">L'applicazione memorizza nella cache i dati visualizzati sul form Web e li aggiorna ogni tre minuti in assenza di attività.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-123">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="dbaa5-124">Se il database viene modificato, la cache viene immediatamente aggiornata.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-124">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="dbaa5-125">Eseguire l'applicazione da Visual Studio per caricare la pagina nel browser.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-125">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="dbaa5-126">L'ora di aggiornamento della cache visualizzata indica quando la cache è stata aggiornata per l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-126">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="dbaa5-127">Attendere tre minuti e quindi aggiornare la pagina, in modo da causare un evento postback.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-127">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="dbaa5-128">Notare che l'ora visualizzata nella pagina è cambiata.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-128">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="dbaa5-129">Se si aggiorna la pagina prima dei tre minuti, l'ora visualizzata nella pagina rimarrà la stessa.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-129">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="dbaa5-130">A questo punto aggiornare i dati nel database, usando un comandi UPDATE Transact-SQL, quindi aggiornare la pagina.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-130">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="dbaa5-131">Adesso l'ora visualizzata indica che la cache è stata aggiornata automaticamente con i nuovi dati del database.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-131">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="dbaa5-132">Notare che, anche se la cache è stata aggiornata, l'ora visualizzata nella pagina non cambia finché non si verifica un evento postback.</span><span class="sxs-lookup"><span data-stu-id="dbaa5-132">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbaa5-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbaa5-133">See also</span></span>

- [<span data-ttu-id="dbaa5-134">Notifiche di query in SQL Server</span><span class="sxs-lookup"><span data-stu-id="dbaa5-134">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [<span data-ttu-id="dbaa5-135">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="dbaa5-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
