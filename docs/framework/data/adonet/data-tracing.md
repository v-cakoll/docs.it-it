---
title: Traccia dati in ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: fcd149b34282ef6ae21593e4549478bab91e0189
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="data-tracing-in-adonet"></a>Traccia dati in ADO.NET
In ADO.NET 2.0 è disponibile una funzionalità di analisi dei dati incorporata supportata dai provider di dati .NET per [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], Oracle, OLE DB e ODBC, nonché dall'oggetto <xref:System.Data.DataSet>ADO.NET e dai protocolli di rete di [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].  
  
 L'analisi delle chiamate API di accesso ai dati consente di diagnosticare i seguenti problemi:  
  
-   Mancata corrispondenza di schema tra il programma client e il database.  
  
-   Database non disponibile o problemi nella libreria di rete.  
  
-   Sintassi SQL non corretta definita a livello di codice o generata da un'applicazione.  
  
-   Logica di programmazione non corretta.  
  
-   Problemi risultanti dall'interazione tra più componenti ADO.NET o tra ADO.NET e i componenti dell'utente.  
  
 Per supportare tecnologie di traccia diverse, questa funzionalità è estensibile, pertanto uno sviluppatore può tracciare un problema a qualsiasi livello dello stack dell'applicazione. Sebbene la funzionalità di analisi non sia esclusiva di ADO.NET, i provider Microsoft usano l'analisi generalizzata e le API della strumentazione.  
  
 Per ulteriori informazioni sulla configurazione dell'analisi gestita in ADO.NET, vedere [accesso ai dati di traccia](http://msdn.microsoft.com/library/hh880086.aspx).  
  
## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>Accesso alle informazioni diagnostiche nel registro di eventi esteso  
 Nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], traccia di accesso ai dati ([traccia di accesso ai dati](http://msdn.microsoft.com/library/hh880086.aspx)) è stata aggiornata per semplificare per correlare gli eventi client con le informazioni di diagnostica, ad esempio gli errori di connessione da connettività buffer circolare e applicazione delle prestazioni informazioni del server nel log degli eventi estesi. Per informazioni sulla lettura del log di eventi estesi, vedere [visualizzare i dati di sessione eventi](http://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx).  
  
 Per le operazioni di connessione, ADO.NET invierà un ID della connessione client. Se la connessione non riesce, è possibile accedere al buffer circolare ([la risoluzione dei problemi di connettività in SQL Server 2008 con il Buffer circolare di connettività](http://go.microsoft.com/fwlink/?LinkId=207752)) e individuare il `ClientConnectionID` campo e ottenere informazioni di diagnostica di Errore di connessione. Gli ID della connessione client vengono registrati nel buffer circolare solo se si verifica un errore. Se la connessione non riesce prima di inviare il pacchetto di preaccesso, non verrà generato un ID di connessione client. L'ID di connessione client è un GUID a 16 byte. È anche possibile trovare l'ID di connessione client nell'output di destinazione di eventi estesi, se l'azione `client_connection_id` viene aggiunta agli eventi in una sessione di eventi estesi. È possibile abilitare l'analisi di accesso ai dati ed eseguire di nuovo il comando di connessione e osservare il campo `ClientConnectionID` nell'analisi di accesso ai dati, se si necessita di ulteriore assistenza per la diagnostica dei driver del client.  
  
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
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
