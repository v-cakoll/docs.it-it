---
title: Attività
ms.date: 03/30/2017
ms.assetid: 70471705-f55f-4da1-919f-4b580f172665
ms.openlocfilehash: 41de6b9458feb4e1898eeac6635b74c4617885d6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602141"
---
# <a name="activity"></a>Attività
In questo argomento vengono descritte le tracce delle attività nel modello di traccia Windows Communication Foundation (WCF). Le attività sono unità di elaborazione che consentono all'utente di restringere l'ambito di un errore e quindi di individuarne le cause con maggiore facilità. Gli errori che si verificano nella stessa attività sono correlati in modo diretto. Si consideri ad esempio il caso di un'operazione che non riesce poiché la decrittografia di un messaggio ha avuto esito negativo. Le tracce relative alla non riuscita dell'operazione e della decrittografia del messaggio vengono visualizzate entrambe nella stessa attività, evidenziando in questo modo una correlazione diretta fra i due eventi di errore.  
  
## <a name="configuring-activity-tracing"></a>Configurazione della traccia attività  
 WCF fornisce attività predefinite per l'elaborazione delle applicazioni (vedere [elenco attività](activity-list.md)). È inoltre possibile definire attività a livello di programmazione allo scopo di raggruppare più tracce utente. Per altre informazioni, vedere [creazione di tracce di codice utente](emitting-user-code-traces.md).  
  
 Per emettere tracce di attività in fase di esecuzione, utilizzare l' `ActivityTracing` impostazione per l' `System.ServiceModel` origine di traccia o altre origini di traccia WCF o personalizzate, come illustrato nel codice di configurazione seguente.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
 Per ulteriori informazioni sull'elemento di configurazione e sugli attributi usati, vedere l'argomento [configurazione della traccia](configuring-tracing.md) .  
  
## <a name="viewing-activities"></a>Visualizzazione delle attività  
 È possibile visualizzare le attività e le relative utilità nello [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md). Quando la traccia attività è attiva, questo strumento recupera le tracce e le ordina in base all'attività. È inoltre possibile visualizzare i trasferimenti di traccia. Un trasferimento di traccia indica come le varie attività sono correlate l'una all'altra. È ad esempio possibile visualizzare un'attività che ha provocato l'avvio di un'altra attività, Una richiesta di messaggio, ad esempio, ha avviato un handshake di sicurezza per ottenere un token di conversazione protetta.  
  
### <a name="correlating-activities-in-service-trace-viewer"></a>Correlazione delle attività nel visualizzatore delle tracce dei servizi  
 Lo strumento visualizzatore di tracce dei servizi fornisce due visualizzazioni di attività:  
  
- Visualizzazione **elenco** , in cui l'ID attività viene utilizzato per correlare direttamente le tracce nei processi. Le tracce associate a processi distinti, ad esempio client e servizio, ma aventi lo stesso ID attività vengono raggruppate nella stessa attività. Di conseguenza, sia l'errore che si verifica nel servizio che l'errore conseguente nel client, verranno inclusi nella stessa visualizzazione dell'attività nello strumento.  
  
- Visualizzazione **grafico** , in cui le attività vengono raggruppate in base ai processi. In questa visualizzazione, le tracce di un client e di un servizio aventi lo stesso ID attività vengono riportate in attività diverse. Per correlare le attività aventi lo stesso ID ma contenute in processi distinti, lo strumento mostra i flussi dei messaggi fra le attività correlate.  
  
 Per ulteriori informazioni e per visualizzare una visualizzazione grafica dello strumento Visualizzatore di tracce dei servizi, vedere strumento Visualizzatore di tracce dei servizi [(SvcTraceViewer. exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md) e [utilizzo del Visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e risoluzione dei problemi](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
## <a name="defining-the-scope-of-an-activity"></a>Definizione dell'ambito di un'attività  
 Le attività vengono definite in fase di progettazione per indicare un'unità logica di esecuzione. Le tracce emesse con lo stesso identificatore di attività sono direttamente correlate, in quanto parte della stessa attività. Poiché le attività possono oltrepassare i limiti di endpoint (nel caso di una richiesta), per ogni attività vengono definiti due ambiti.  
  
- Ambito `Global`, per applicazione. In questo ambito, l'attività è identificata dal proprio identificatore di attività globalmente univoco a 128 bit, il gAId. Il gAid è l'ID che viene propagato fra gli endpoint.  
  
- Ambito `Local`, per endpoint. In questo ambito, l'attività è identificata dal relativo gAId, insieme al nome dell'origine di traccia che emette le tracce dell'attività e all'ID del processo. Questa tripletta costituisce l'ID attività locale, lAId. Il lAId è utilizzato per definire i limiti (locali) di un'attività.  
  
## <a name="trace-schema"></a>Schema di traccia  
 Le tracce possono essere emesse utilizzando qualsiasi schema e tra piattaforme Microsoft diverse. "e2e" (per "end-to-end") è uno schema di uso comune. Questo schema include un gAId a 128 bit, il nome dell'origine di traccia e l'ID del processo. In codice gestito, <xref:System.Diagnostics.XmlWriterTraceListener> emette tracce nello schema E2E.  
  
 Gli sviluppatori possono impostare l'AID emesso con una traccia impostando la proprietà <xref:System.Diagnostics.CorrelationManager.ActivityId%2A> con un GUID nell'archiviazione locale di thread (TLS, Thread Local Storage). L'esempio seguente illustra questa operazione.  
  
```csharp
// set the current Activity ID to a new GUID.  
CorrelationManager.ActivityId = Guid.NewGuid();  
```
  
 L'impostazione di gAId in TLS sarà evidente quando le tracce vengono emesse utilizzando un'origine di traccia, come illustrato nell'esempio seguente.  
  
```csharp
TraceSource traceSource = new TraceSource("myTraceSource");  
traceSource.TraceEvent(TraceEventType.Warning, eventId, "Information");  
```  
  
 La traccia emessa conterrà il gAId presente in TLS, il nome dell'origine di traccia passato come parametro al costruttore dell'origine di traccia e l'ID del processo corrente.  
  
## <a name="activity-lifetime"></a>Durata dell'attività  
 In termini rigorosi, l'evidenza di un'attività inizia la prima la prima volta che l'ID attività viene utilizzato in una traccia emessa e termina l'ultima volta che tale ID viene utilizzato in una traccia emessa. Un set predefinito di tipi di traccia viene fornito dallo spazio dei nomi <xref:System.Diagnostics>, che utilizza due tipi di traccia, Start e Stop, per contrassegnare in modo esplicito i limiti di durata dell'attività.  
  
- Start: indica l'inizio di un'attività. Una traccia "Start" fornisce un record per iniziare una nuova attività cardine di elaborazione. Tale traccia contiene un nuovo ID attività per una determinata origine di analisi in un processo specificato. Se tuttavia l'ID attività viene propagato fra più endpoint, viene visualizzata una traccia "Start" per ogni endpoint. Esempi di avvio di una nuova attività includono la creazione di un nuovo thread di elaborazione o l'immissione di un nuovo metodo pubblico.  
  
- Stop: indica la fine di un'attività. Una traccia "Stop" fornisce un record per terminare un'attività cardine di elaborazione esistente. Tale traccia contiene un ID attività esistente per una determinata origine di analisi in un processo specificato. Se tuttavia l'ID attività viene propagato fra più endpoint, viene visualizzata una traccia "Stop" per ogni endpoint.  Esempi di interruzione di un'attività includono la terminazione di un thread di elaborazione o l'uscita da un metodo il cui inizio è stato indicato con una traccia di avvio.  
  
- Suspend: indica una sospensione nell'elaborazione di un'attività. Una traccia di sospensione contiene un ID attività esistente la cui elaborazione dovrebbe essere ripresa in un secondo momento. Non vengono emesse tracce con questo ID tra l'evento di sospensione e quello di ripresa dall'origine della traccia corrente. Ne è un esempio la sospensione di un'attività in caso di chiamata a una funzione della libreria esterna o di attesa in una risorsa quale una porta di completamento di I/O.  
  
- Resume: indica la ripresa dell'elaborazione di un'attività. Una traccia "Resume" contiene un ID attività esistente la cui ultima traccia emessa dall'origine di traccia corrente è una traccia di "suspend". Negli esempi è inclusa la restituzione da una chiamata a una funzione della libreria esterna o la segnalazione per riprendere l'elaborazione da parte di una risorsa, ad esempio una porta di completamento di I/O.  
  
- Transfer: poiché alcune attività sono causate da altri utenti o sono correlate ad altre, le attività possono essere correlate ad altre attività tramite tracce di trasferimento. Un trasferimento registra la relazione diretta di un'attività con un'altra  
  
 Le tracce Start e Stop non sono critiche per la correlazione. Possono tuttavia contribuire ad aumentare le prestazioni, il profiling e la convalida dell'ambito dell'attività.  
  
 Utilizzando questi tipi, gli strumenti riescono a ottimizzare l'accesso ai registri di traccia per individuare gli eventi immediatamente correlati della stessa attività o eventi in attività correlate se lo strumento segue tracce di trasferimento. Gli strumenti interromperanno l'analisi dei log di una determinata attività quando vedono una traccia Start/Stop.  
  
 Questi tipi di traccia possono essere utilizzati anche per il profiling. Le risorse utilizzate tra i marcatori di inizio e di arresto rappresentano il tempo inclusivo dell'attività, comprese le attività logiche contenute. La sottrazione degli intervalli di tempo tra le tracce Suspend e Resume fornisce il tempo di attività effettivo.  
  
 La traccia Stop è inoltre particolarmente utile per convalidare l'ambito delle attività implementate. Se alcune tracce di elaborazione vengono visualizzate dopo la traccia Stop, anziché all'interno di una determinata attività, è probabile che vi sia un difetto del codice.  
  
## <a name="guidelines-for-using-activity-tracing"></a>Linee guida per l'utilizzo della traccia attività  
 Di seguito viene illustrato come utilizzare le tracce di ActivityTracing (Start, Stop, Suspend, Resume e Transfer).  
  
- La traccia è un grafico ciclico diretto, non un albero. È possibile restituire il controllo a un'attività che ha generato un'attività.  
  
- Un'attività denota un limite di elaborazione che può essere significativo per l'amministratore del sistema o per le configurazioni supportate.  
  
- Ogni metodo WCF, sia sul client che sul server, è associato dall'inizio di una nuova attività, quindi, dopo il completamento del lavoro, termina la nuova attività e restituisce l'attività di ambiente.  
  
- Le attività a esecuzione prolungata (in corso), ad esempio l'ascolto di connessioni o l'attesa di messaggi, sono rappresentate da marcatori di avvio/arresto corrispondenti.  
  
- Le attività avviate dal ricevimento o dall'elaborazione di un messaggio sono rappresentate da limiti di traccia.  
  
- Le attività rappresentano attività, non necessariamente degli oggetti. Un'attività deve essere interpretata come "questa operazione si è verificata quando. . . (si è verificata l'emissione di una traccia significativa)".  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione delle funzionalità di traccia](configuring-tracing.md)
- [Uso del visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e la risoluzione dei problemi](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Scenari di analisi end-to-end](end-to-end-tracing-scenarios.md)
- [Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md)
- [Creazione di tracce di codice utente](emitting-user-code-traces.md)
