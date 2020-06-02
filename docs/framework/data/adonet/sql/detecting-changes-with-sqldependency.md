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
# <a name="detecting-changes-with-sqldependency"></a>Rilevamento di modifiche con SqlDependency

Un oggetto <xref:System.Data.SqlClient.SqlDependency> può essere associato a un <xref:System.Data.SqlClient.SqlCommand> per scoprire quando i risultati della query presentano delle differenze rispetto a quelli recuperati in origine. È anche possibile assegnare un delegato all'evento `OnChange`, che verrà attivato quando i risultati cambiano per un comando associato. Prima di eseguire il comando, è necessario associare <xref:System.Data.SqlClient.SqlDependency> al comando. È inoltre possibile usare la proprietà `HasChanges` di <xref:System.Data.SqlClient.SqlDependency> per determinare se i risultati della query sono cambiati dopo il primo recupero dei dati.

## <a name="security-considerations"></a>Considerazioni relative alla sicurezza

L'infrastruttura di dipendenza si basa su un <xref:System.Data.SqlClient.SqlConnection> aperto quando si chiama <xref:System.Data.SqlClient.SqlDependency.Start%2A> per ricevere le notifiche relative alla modifica dei dati sottostanti per un determinato comando. La possibilità per un client di avviare la chiamata a `SqlDependency.Start` viene controllata usando <xref:System.Data.SqlClient.SqlClientPermission> e gli attributi di sicurezza dall'accesso di codice. Per altre informazioni, vedere [Abilitazione di notifiche di query](enabling-query-notifications.md) e [sicurezza dall'accesso di codice e ADO.NET](../code-access-security.md).

### <a name="example"></a>Esempio

Nei passaggi seguenti viene illustrato come dichiarare una dipendenza, eseguire un comando e ricevere una notifica quando il set di risultati cambia:

1. Attivar una connessione `SqlDependency` al server.

2. Creare gli oggetti <xref:System.Data.SqlClient.SqlConnection> e <xref:System.Data.SqlClient.SqlCommand> per connettersi al server e definire un'istruzione Transact-SQL.

3. Creare un nuovo oggetto `SqlDependency`, o usarne uno esistente, e associarlo all'oggetto `SqlCommand`. Internamente viene creato un oggetto <xref:System.Data.Sql.SqlNotificationRequest> che viene poi associato all'oggetto comando in base alle esigenze. Questa richiesta di notifica contiene un identificatore interno che identifica in modo univoco l'oggetto `SqlDependency`. Avvia anche il listener client, se non è già attivo.

4. Sottoscrivere un gestore eventi per l'evento `OnChange` dell'oggetto `SqlDependency`.

5. Eseguire il comando usando uno dei metodi `Execute` dell'oggetto `SqlCommand`. Poiché il comando è associato all'oggetto notifica, il server riconosce che deve generare una notifica e le informazioni sulla coda punteranno alla coda delle dipendenze.

6. Interrompere la connessione `SqlDependency` al server.

Se un utente successivamente modifica i dati sottostanti, Microsoft SQL Server rileva la presenza di una notifica in sospeso per tale modifica e invia una notifica, che viene elaborata e inoltrata al client usando l'oggetto `SqlConnection` sottostante creato con la chiamata a `SqlDependency.Start`. Il listener client riceve il messaggio di invalidamento, quindi individua l'oggetto `SqlDependency` associato e genera l'evento `OnChange`.

Il frammento di codice seguente illustra lo schema progettuale da usare per creare un'applicazione di esempio.

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

## <a name="see-also"></a>Vedere anche

- [Notifiche di query in SQL Server](query-notifications-in-sql-server.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
