---
title: Rilevamento di modifiche con SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: 63d6a17e5aaf3e5d39ed0eda288e75c071be4d73
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44508478"
---
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="61690-102">Rilevamento di modifiche con SqlDependency</span><span class="sxs-lookup"><span data-stu-id="61690-102">Detecting Changes with SqlDependency</span></span>
<span data-ttu-id="61690-103">È possibile associare un oggetto <xref:System.Data.SqlClient.SqlDependency> a <xref:System.Data.SqlClient.SqlCommand> per rilevare quando i risultati della query differiscono da quelli recuperati in origine.</span><span class="sxs-lookup"><span data-stu-id="61690-103">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="61690-104">È inoltre possibile assegnare un delegato all'evento `OnChange` che verrà generato in caso di modifica dei risultati per un comando associato.</span><span class="sxs-lookup"><span data-stu-id="61690-104">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="61690-105">È necessario associare l'oggetto <xref:System.Data.SqlClient.SqlDependency> al comando prima di eseguire il comando stesso.</span><span class="sxs-lookup"><span data-stu-id="61690-105">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="61690-106">È inoltre possibile usare la proprietà `HasChanges` di <xref:System.Data.SqlClient.SqlDependency> per determinare se i risultati della query sono stati modificati rispetto a quando i dati sono stati recuperati inizialmente.</span><span class="sxs-lookup"><span data-stu-id="61690-106">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>  
  
## <a name="security-considerations"></a><span data-ttu-id="61690-107">Considerazioni sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="61690-107">Security Considerations</span></span>  
 <span data-ttu-id="61690-108">L'infrastruttura della dipendenza si basa su un oggetto <xref:System.Data.SqlClient.SqlConnection> che viene aperto quando viene chiamato <xref:System.Data.SqlClient.SqlDependency.Start%2A> per ricevere le notifiche relative alla modifica dei dati sottostanti per un comando specificato.</span><span class="sxs-lookup"><span data-stu-id="61690-108">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="61690-109">Per controllare se un client è in grado di avviare la chiamata a `SqlDependency.Start`, vengono usati <xref:System.Data.SqlClient.SqlClientPermission> e gli attributi della sicurezza dall'accesso di codice.</span><span class="sxs-lookup"><span data-stu-id="61690-109">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="61690-110">Per altre informazioni, vedere [abilitazione le notifiche di Query](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) e [Code Access Security and ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="61690-110">For more information, see [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) and [Code Access Security and ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="61690-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="61690-111">Example</span></span>  
 <span data-ttu-id="61690-112">Nella procedura seguente viene illustrato come dichiarare una dipendenza, eseguire un comando e ricevere una notifica in caso di modifica del set di risultati:</span><span class="sxs-lookup"><span data-stu-id="61690-112">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>  
  
1.  <span data-ttu-id="61690-113">Avviare una connessione `SqlDependency` al server.</span><span class="sxs-lookup"><span data-stu-id="61690-113">Initiate a `SqlDependency` connection to the server.</span></span>  
  
2.  <span data-ttu-id="61690-114">Creare gli oggetti <xref:System.Data.SqlClient.SqlConnection> e <xref:System.Data.SqlClient.SqlCommand> per la connessione al server e definire un'istruzione Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="61690-114">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="61690-115">Creare un nuovo oggetto `SqlDependency` oppure usarne uno esistente e associarlo all'oggetto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="61690-115">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="61690-116">Internamente, questa procedura consente di creare un oggetto <xref:System.Data.Sql.SqlNotificationRequest> e associarlo all'oggetto comando se necessario.</span><span class="sxs-lookup"><span data-stu-id="61690-116">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="61690-117">Questa richiesta di notifica contiene un identificatore interno che identifica in modo univoco l'oggetto `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="61690-117">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="61690-118">In tal modo viene inoltre avviato il listener del client, se non è già attivo.</span><span class="sxs-lookup"><span data-stu-id="61690-118">It also starts the client listener if it is not already active.</span></span>  
  
4.  <span data-ttu-id="61690-119">Sottoscrivere un gestore eventi all'evento `OnChange` dell'oggetto `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="61690-119">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>  
  
5.  <span data-ttu-id="61690-120">Eseguire il comando con uno dei metodi `Execute` dell'oggetto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="61690-120">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="61690-121">Poiché il comando è associato all'oggetto notifica, il server riconosce la necessità di generare una notifica e le informazioni della coda faranno riferimento alla coda delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="61690-121">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>  
  
6.  <span data-ttu-id="61690-122">Interrompere la connessione `SqlDependency` al server.</span><span class="sxs-lookup"><span data-stu-id="61690-122">Stop the `SqlDependency` connection to the server.</span></span>  
  
 <span data-ttu-id="61690-123">Se un qualsiasi utente modifica successivamente i dati sottostanti, in Microsoft SQL Server viene rilevata una notifica in sospeso per una tale modifica, pertanto viene inviata una notifica, che viene elaborata e inoltrata al client tramite l'oggetto `SqlConnection` sottostante creato mediante la chiamata a `SqlDependency.Start`.</span><span class="sxs-lookup"><span data-stu-id="61690-123">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="61690-124">Il listener del client riceve il messaggio di invalidazione,</span><span class="sxs-lookup"><span data-stu-id="61690-124">The client listener receives the invalidation message.</span></span> <span data-ttu-id="61690-125">quindi individua l'oggetto `SqlDependency` associato e attiva l'evento `OnChange`.</span><span class="sxs-lookup"><span data-stu-id="61690-125">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>  
  
 <span data-ttu-id="61690-126">Nel frammento di codice seguente è illustrato il modello di progettazione da usare per creare un'applicazione di esempio.</span><span class="sxs-lookup"><span data-stu-id="61690-126">The following code fragment shows the design pattern you would use to create a sample application.</span></span>  
  
```vb  
Sub Initialization()  
    ' Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName)  
End Sub  
  
Sub SomeMethod()   
    ' Assume connection is an open SqlConnection.  
    ' Create a new SqlCommand object.  
    Using command As New SqlCommand( _  
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _  
      connection)  
  
        ' Create a dependency and associate it with the SqlCommand.  
        Dim dependency As New SqlDependency(command)  
        ' Maintain the refence in a class member.  
        ' Subscribe to the SqlDependency event.  
        AddHandler dependency.OnChange, AddressOf OnDependencyChange  
  
        ' Execute the command.  
        Using reader = command.ExecuteReader()  
            ' Process the DataReader.  
        End Using  
    End Using  
End Sub   
  
' Handler method  
Sub OnDependencyChange(ByVal sender As Object, _  
    ByVal e As SqlNotificationEventArgs)   
    ' Handle the event (for example, invalidate this cache entry).  
End Sub  
  
Sub Termination()  
    ' Release the dependency  
    SqlDependency.Stop(connectionString, queueName)  
End Sub  
```  
  
```csharp  
void Initialization()  
{  
    // Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName);  
}  
  
void SomeMethod()  
{  
    // Assume connection is an open SqlConnection.  
  
    // Create a new SqlCommand object.  
    using (SqlCommand command=new SqlCommand(  
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",   
        connection))  
    {  
  
        // Create a dependency and associate it with the SqlCommand.  
        SqlDependency dependency=new SqlDependency(command);  
        // Maintain the reference in a class member.  
  
        // Subscribe to the SqlDependency event.  
        dependency.OnChange+=new  
           OnChangeEventHandler(OnDependencyChange);  
  
        // Execute the command.  
        using (SqlDataReader reader = command.ExecuteReader())  
        {  
            // Process the DataReader.  
        }  
    }  
}  
  
// Handler method  
void OnDependencyChange(object sender,   
   SqlNotificationEventArgs e )  
{  
  // Handle the event (for example, invalidate this cache entry).  
}  
  
void Termination()  
{  
    // Release the dependency.  
    SqlDependency.Stop(connectionString, queueName);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="61690-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61690-127">See Also</span></span>  
 [<span data-ttu-id="61690-128">Notifiche di query in SQL Server</span><span class="sxs-lookup"><span data-stu-id="61690-128">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="61690-129">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="61690-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
