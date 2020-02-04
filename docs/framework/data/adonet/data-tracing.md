---
title: Traccia dei dati
ms.date: 03/30/2017
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
ms.openlocfilehash: 2b2a33739619ba09e56d4cc9ce99c51423678918
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980223"
---
# <a name="data-tracing-in-adonet"></a>Traccia dati in ADO.NET

ADO.NET include funzionalità di analisi dei dati incorporate supportate dai provider di dati .NET per SQL Server, Oracle, OLE DB e ODBC, nonché il <xref:System.Data.DataSet>ADO.NET e i protocolli di rete SQL Server.

L'analisi delle chiamate API di accesso ai dati consente di diagnosticare i seguenti problemi:

- Mancata corrispondenza di schema tra il programma client e il database.

- Database non disponibile o problemi nella libreria di rete.

- Sintassi SQL non corretta definita a livello di codice o generata da un'applicazione.

- Logica di programmazione non corretta.

- Problemi risultanti dall'interazione tra più componenti ADO.NET o tra ADO.NET e i componenti dell'utente.

Per supportare tecnologie di traccia diverse, questa funzionalità è estensibile, pertanto uno sviluppatore può tracciare un problema a qualsiasi livello dello stack dell'applicazione. Sebbene la funzionalità di analisi non sia esclusiva di ADO.NET, i provider Microsoft usano l'analisi generalizzata e le API della strumentazione.

Per ulteriori informazioni sull'impostazione e sulla configurazione della traccia gestita in ADO.NET, vedere [traccia dell'accesso ai dati](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10)).

## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>Accesso alle informazioni diagnostiche nel registro di eventi esteso

Nella .NET Framework provider di dati per SQL Server, la traccia di accesso ai dati ([traccia di accesso ai dati](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10))) è stata aggiornata per semplificare la correlazione degli eventi client con informazioni di diagnostica, ad esempio errori di connessione, dal buffer circolare della connettività del server e dalle informazioni sulle prestazioni dell'applicazione nel log degli eventi estesi. Per informazioni sulla lettura del log degli eventi estesi, vedere [visualizzare i dati della sessione eventi](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh710068(v=sql.110)).

Per le operazioni di connessione, ADO.NET invierà un ID della connessione client. Se la connessione non riesce, è possibile accedere al buffer circolare della connettività ([risoluzione dei problemi di connettività in SQL Server 2008 con il buffer circolare della connettività](https://docs.microsoft.com/archive/blogs/sql_protocols/connectivity-troubleshooting-in-sql-server-2008-with-the-connectivity-ring-buffer)) e individuare il campo `ClientConnectionID` e ottenere informazioni di diagnostica sull'errore di connessione. Gli ID della connessione client vengono registrati nel buffer circolare solo se si verifica un errore. Se una connessione non riesce prima di inviare il pacchetto di preaccesso, non verrà generato alcun ID connessione client. L'ID connessione client è un GUID a 16 byte. È anche possibile trovare l'ID di connessione client nell'output di destinazione di eventi estesi, se l'azione `client_connection_id` viene aggiunta agli eventi in una sessione di eventi estesi. È possibile abilitare l'analisi di accesso ai dati ed eseguire di nuovo il comando di connessione e osservare il campo `ClientConnectionID` nell'analisi di accesso ai dati, se si necessita di ulteriore assistenza per la diagnostica dei driver del client.

È possibile ottenere l'ID di connessione cliente a livello di codice usando la proprietà `SqlConnection.ClientConnectionID`.

`ClientConnectionID` è disponibile per un oggetto di <xref:System.Data.SqlClient.SqlConnection> che stabilisce correttamente una connessione. Se un tentativo di connessione non riesce, `ClientConnectionID` può essere disponibile tramite `SqlException.ToString`.

ADO.NET invia inoltre un ID di attività specifico del thread. L'ID attività viene acquisito nelle sessioni di eventi estesi se le sessioni vengono avviate con l'opzione TRACK_CAUSALITY abilitata. Per i problemi di prestazioni con una connessione attiva, è possibile ottenere un ID attività dell'analisi di accesso ai dati del client (campo di`ActivityID` ) e quindi individuare gli ID attività nell'output di eventi estesi. L'ID attività negli eventi estesi è un GUID a 16 byte, non lo stesso del GUID per l'ID connessione client, aggiunto con un numero di sequenza a quattro byte. Il numero di sequenze rappresenta l'ordine di una richiesta all'interno di un thread e indica un ordinamento relativo del batch e delle istruzioni RPC per il thread. `ActivityID` viene attualmente inviato facoltativamente per le istruzioni batch SQL e le richieste RPC quando è abilitata l'analisi di accesso ai dati e il diciottesimo bit della parola di configurazione dell'analisi di accesso ai dati è ON.

Di seguito è riportato un esempio che usa Transact-SQL per avviare una sessione di eventi estesi che verrà archiviata in un buffer circolare e registrerà l'ID attività inviato da un client sulle operazioni RPC e batch.

```sql
create event session MySession on server
add event connectivity_ring_buffer_recorded,
add event sql_statement_starting (action (client_connection_id)),
add event sql_statement_completed (action (client_connection_id)),
add event rpc_starting (action (client_connection_id)),
add event rpc_completed (action (client_connection_id))
add target ring_buffer with (track_causality=on)
```

## <a name="see-also"></a>Vedere anche

- [Traccia di rete in .NET Framework](../../network-programming/network-tracing.md)
- [Traccia e strumentazione di applicazioni](../../debug-trace-profile/tracing-and-instrumenting-applications.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
