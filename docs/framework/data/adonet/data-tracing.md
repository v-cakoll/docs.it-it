---
title: Traccia dati in ADO.NET
ms.date: 03/30/2017
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
ms.openlocfilehash: 037db6f4e5695e00401c81e1490953efe2fc9b99
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522420"
---
# <a name="data-tracing-in-adonet"></a>Traccia dati in ADO.NET
ADO.NET dotato di funzionalità di analisi di dati incorporati che è supportata dal provider di dati .NET per SQL Server, Oracle, OLE DB e ODBC, nonché ADO.NET <xref:System.Data.DataSet>e i protocolli di rete SQL Server.  
  
 L'analisi delle chiamate API di accesso ai dati consente di diagnosticare i seguenti problemi:  
  
-   Mancata corrispondenza di schema tra il programma client e il database.  
  
-   Database non disponibile o problemi nella libreria di rete.  
  
-   Sintassi SQL non corretta definita a livello di codice o generata da un'applicazione.  
  
-   Logica di programmazione non corretta.  
  
-   Problemi risultanti dall'interazione tra più componenti ADO.NET o tra ADO.NET e i componenti dell'utente.  
  
 Per supportare tecnologie di traccia diverse, questa funzionalità è estensibile, pertanto uno sviluppatore può tracciare un problema a qualsiasi livello dello stack dell'applicazione. Sebbene la funzionalità di analisi non sia esclusiva di ADO.NET, i provider Microsoft usano l'analisi generalizzata e le API della strumentazione.  
  
 Per altre informazioni sull'impostazione e configurazione dell'analisi gestita in ADO.NET, vedere [Tracing Data Access](https://msdn.microsoft.com/library/hh880086.aspx).  
  
## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>Accesso alle informazioni diagnostiche nel registro di eventi esteso  
 Nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server, accesso ai dati traccia ([traccia di accesso ai dati](https://msdn.microsoft.com/library/hh880086.aspx)) è stata aggiornata per semplificare la più facile correlare gli eventi client con informazioni di diagnostica, ad esempio gli errori di connessione dal connettività del server circolare del buffer e l'applicazione informazioni sulle prestazioni nel registro eventi esteso. Per informazioni sulla lettura del registro eventi esteso, vedere [visualizzare i dati della sessione eventi](https://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx).  
  
 Per le operazioni di connessione, ADO.NET invierà un ID della connessione client. Se la connessione non riesce, è possibile accedere al buffer circolare ([risoluzione dei problemi di connettività in SQL Server 2008 con il Buffer circolare della connettività](https://go.microsoft.com/fwlink/?LinkId=207752)) e individuare il `ClientConnectionID` campo e ottenere informazioni diagnostiche Errore di connessione. Gli ID della connessione client vengono registrati nel buffer circolare solo se si verifica un errore. Se la connessione non riesce prima di inviare il pacchetto di preaccesso, non verrà generato un ID di connessione client. L'ID di connessione client è un GUID a 16 byte. È anche possibile trovare l'ID di connessione client nell'output di destinazione di eventi estesi, se l'azione `client_connection_id` viene aggiunta agli eventi in una sessione di eventi estesi. È possibile abilitare l'analisi di accesso ai dati ed eseguire di nuovo il comando di connessione e osservare il campo `ClientConnectionID` nell'analisi di accesso ai dati, se si necessita di ulteriore assistenza per la diagnostica dei driver del client.  
  
 È possibile ottenere l'ID di connessione cliente a livello di codice usando la proprietà `SqlConnection.ClientConnectionID`.  
  
 `ClientConnectionID` è disponibile per un oggetto di <xref:System.Data.SqlClient.SqlConnection> che stabilisce correttamente una connessione. Se un tentativo di connessione non riesce, `ClientConnectionID` può essere disponibile tramite `SqlException.ToString`.  
  
 ADO.NET invia inoltre un ID di attività specifico del thread. L'ID attività viene acquisito nelle sessioni di eventi estesi se le sessioni vengono avviate all'opzione TRACK_CAUSAILITY abilitata. Per i problemi di prestazioni con una connessione attiva, è possibile ottenere un ID attività dell'analisi di accesso ai dati del client (campo di`ActivityID` ) e quindi individuare gli ID attività nell'output di eventi estesi. L'ID attività negli eventi estesi è un GUID a 16 byte (diverso dal GUID per l'ID di connessione client seguito da un numero in sequenza di quattro byte). Il numero di sequenze rappresenta l'ordine di una richiesta all'interno di un thread e indica un ordinamento relativo del batch e delle istruzioni RPC per il thread. `ActivityID` viene attualmente inviato facoltativamente per le istruzioni batch SQL e le richieste RPC quando è abilitata l'analisi di accesso ai dati e il diciottesimo bit della parola di configurazione dell'analisi di accesso ai dati è ON.  
  
 Di seguito viene riportato un esempio che usa [!INCLUDE[tsql](../../../../includes/tsql-md.md)] per avviare una sessione di eventi estesi che verrà archiviata in un buffer circolare e che registrerà l'ID attività inviato da un client nelle operazioni RPC e batch.  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia di rete in .NET Framework](../../../../docs/framework/network-programming/network-tracing.md)  
 [Traccia e strumentazione di applicazioni](../../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
