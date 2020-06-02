---
title: Rilevamento di modifiche con SqlDependency
description: Associare un oggetto SqlDependency a un SqlCommand per rilevare quando i risultati della query sono diversi da quelli originariamente recuperati in ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: b196d42477e1778c45df64b1390502645fdd649d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286468"
---
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="aaeaf-103">Rilevamento di modifiche con SqlDependency</span><span class="sxs-lookup"><span data-stu-id="aaeaf-103">Detecting Changes with SqlDependency</span></span>

<span data-ttu-id="aaeaf-104">Un oggetto <xref:System.Data.SqlClient.SqlDependency> può essere associato a un <xref:System.Data.SqlClient.SqlCommand> per scoprire quando i risultati della query presentano delle differenze rispetto a quelli recuperati in origine.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-104">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="aaeaf-105">È anche possibile assegnare un delegato all'evento `OnChange`, che verrà attivato quando i risultati cambiano per un comando associato.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-105">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="aaeaf-106">Prima di eseguire il comando, è necessario associare <xref:System.Data.SqlClient.SqlDependency> al comando.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-106">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="aaeaf-107">È inoltre possibile usare la proprietà `HasChanges` di <xref:System.Data.SqlClient.SqlDependency> per determinare se i risultati della query sono cambiati dopo il primo recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-107">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="aaeaf-108">Considerazioni relative alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="aaeaf-108">Security Considerations</span></span>

<span data-ttu-id="aaeaf-109">L'infrastruttura di dipendenza si basa su un <xref:System.Data.SqlClient.SqlConnection> aperto quando si chiama <xref:System.Data.SqlClient.SqlDependency.Start%2A> per ricevere le notifiche relative alla modifica dei dati sottostanti per un determinato comando.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-109">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="aaeaf-110">La possibilità per un client di avviare la chiamata a `SqlDependency.Start` viene controllata usando <xref:System.Data.SqlClient.SqlClientPermission> e gli attributi di sicurezza dall'accesso di codice.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-110">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="aaeaf-111">Per altre informazioni, vedere [Abilitazione di notifiche di query](enabling-query-notifications.md) e [sicurezza dall'accesso di codice e ADO.NET](../code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="aaeaf-111">For more information, see [Enabling Query Notifications](enabling-query-notifications.md) and [Code Access Security and ADO.NET](../code-access-security.md).</span></span>

### <a name="example"></a><span data-ttu-id="aaeaf-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="aaeaf-112">Example</span></span>

<span data-ttu-id="aaeaf-113">Nei passaggi seguenti viene illustrato come dichiarare una dipendenza, eseguire un comando e ricevere una notifica quando il set di risultati cambia:</span><span class="sxs-lookup"><span data-stu-id="aaeaf-113">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>

1. <span data-ttu-id="aaeaf-114">Attivar una connessione `SqlDependency` al server.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-114">Initiate a `SqlDependency` connection to the server.</span></span>

2. <span data-ttu-id="aaeaf-115">Creare gli oggetti <xref:System.Data.SqlClient.SqlConnection> e <xref:System.Data.SqlClient.SqlCommand> per connettersi al server e definire un'istruzione Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-115">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>

3. <span data-ttu-id="aaeaf-116">Creare un nuovo oggetto `SqlDependency`, o usarne uno esistente, e associarlo all'oggetto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-116">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="aaeaf-117">Internamente viene creato un oggetto <xref:System.Data.Sql.SqlNotificationRequest> che viene poi associato all'oggetto comando in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-117">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="aaeaf-118">Questa richiesta di notifica contiene un identificatore interno che identifica in modo univoco l'oggetto `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-118">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="aaeaf-119">Avvia anche il listener client, se non è già attivo.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-119">It also starts the client listener if it is not already active.</span></span>

4. <span data-ttu-id="aaeaf-120">Sottoscrivere un gestore eventi per l'evento `OnChange` dell'oggetto `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-120">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>

5. <span data-ttu-id="aaeaf-121">Eseguire il comando usando uno dei metodi `Execute` dell'oggetto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-121">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="aaeaf-122">Poiché il comando è associato all'oggetto notifica, il server riconosce che deve generare una notifica e le informazioni sulla coda punteranno alla coda delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-122">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>

6. <span data-ttu-id="aaeaf-123">Interrompere la connessione `SqlDependency` al server.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-123">Stop the `SqlDependency` connection to the server.</span></span>

<span data-ttu-id="aaeaf-124">Se un utente successivamente modifica i dati sottostanti, Microsoft SQL Server rileva la presenza di una notifica in sospeso per tale modifica e invia una notifica, che viene elaborata e inoltrata al client usando l'oggetto `SqlConnection` sottostante creato con la chiamata a `SqlDependency.Start`.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-124">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="aaeaf-125">Il listener client riceve il messaggio di invalidamento,</span><span class="sxs-lookup"><span data-stu-id="aaeaf-125">The client listener receives the invalidation message.</span></span> <span data-ttu-id="aaeaf-126">quindi individua l'oggetto `SqlDependency` associato e genera l'evento `OnChange`.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-126">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>

<span data-ttu-id="aaeaf-127">Il frammento di codice seguente illustra lo schema progettuale da usare per creare un'applicazione di esempio.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-127">The following code fragment shows the design pattern you would use to create a sample application.</span></span>

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
        ' Maintain the refernce in a class member.
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

## <a name="see-also"></a><span data-ttu-id="aaeaf-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaeaf-128">See also</span></span>

- [<span data-ttu-id="aaeaf-129">Notifiche di query in SQL Server</span><span class="sxs-lookup"><span data-stu-id="aaeaf-129">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="aaeaf-130">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aaeaf-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
