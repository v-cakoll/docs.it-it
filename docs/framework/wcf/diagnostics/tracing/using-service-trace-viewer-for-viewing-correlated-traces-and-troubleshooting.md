---
title: Uso di Service Trace Viewer per la visualizzazione di tracce correlate e risoluzione dei problemi
ms.date: 03/30/2017
ms.assetid: 05d2321c-8acb-49d7-a6cd-8ef2220c6775
ms.openlocfilehash: fc1b75d7f2d97103f99b9dbf0fa8cbbfbe2270cd
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465061"
---
# <a name="using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting"></a>Uso di Service Trace Viewer per la visualizzazione di tracce correlate e risoluzione dei problemi
In questo argomento viene illustrato il formato dei dati di traccia, come visualizzarlo e gli approcci che utilizzano Service Trace Viewer per risolvere i problemi dell'applicazione.  
  
## <a name="using-the-service-trace-viewer-tool"></a>Uso dello strumento Visualizzatore di tracce dei servizi  
 Lo strumento Visualizzatore di tracce dei servizi Windows Communication Foundation (WCF) consente di correlare le tracce di diagnostica prodotte dai listener WCF per individuare la causa radice di un errore. Lo strumento fornisce un modo per visualizzare, raggruppare e filtrare le tracce in modo che è possibile diagnosticare, riparare e verificare i problemi dei servizi WCF con facilità. Per altre informazioni sull'uso di questo strumento, vedere [strumento Service Trace Viewer (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).  
  
 In questo argomento è riportate le schermate relative alle tracce generate eseguendo il [traccia e registrazione dei messaggi](../../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) di esempio, quando viene visualizzato utilizzando il [strumento Service Trace Viewer (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). In questo argomento viene dimostrato come capire il contenuto della traccia, le attività e la loro correlazione e come analizzare moltissime tracce in caso di risoluzione dei problemi.  
  
## <a name="viewing-trace-content"></a>Visualizzazione del contenuto di una traccia  
 Un evento traccia contiene le seguenti informazioni più significative:  
  
-   Nome dell'attività quando impostato.  
  
-   Ora di emissione.  
  
-   Livello di traccia.  
  
-   Nome dell'origine di traccia.  
  
-   Nome processo.  
  
-   ID thread.  
  
-   Identificatore della traccia univoco, ovvero un URL che punta a una destinazione in Microsoft Docs, da cui è possibile ottenere altre informazioni relative alla traccia.  
  
 Tutti questi componenti possono essere visualizzati nel riquadro superiore destro in Service Trace Viewer o nella **le informazioni di base** sezione nella visualizzazione formattata del pannello in basso a destra quando si seleziona una traccia.  
  
> [!NOTE]
>  Se il client e il servizio si trovano nello stesso computer, saranno presenti le tracce per entrambe le applicazioni. Questi possono essere filtrati tramite il **nome del processo** colonna.  
  
 La visualizzazione formattata fornisce inoltre anche una descrizione per la traccia e ulteriori informazioni dettagliate quando disponibili. Le informazioni possono includere il tipo di eccezione e il messaggio, gli stack di chiamate, l'azione del messaggio, i campi da/a e altre informazioni sull'eccezione.  
  
 Nella visualizzazione XML, i tag xml utili includono gli elementi seguenti:  
  
-   `<SubType>` (livello di traccia).  
  
-   `<TimeCreated>`.  
  
-   `<Source>` (nome dell'origine traccia).  
  
-   `<Correlation>` (id attività impostato quando viene emessa la traccia).  
  
-   `<Execution>` (id processo e thread).  
  
-   `<Computer>`.  
  
-   `<ExtendedData>`, incluso `<Action>`, `<MessageID>` e il `<ActivityId>` impostato nell'intestazione del messaggio quando si invia un messaggio.  
  
 Se si esamina la traccia "Messaggio inviato tramite canale", è possibile vedere il contenuto seguente.  
  
```xml  
<E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">  
   <System xmlns="http://schemas.microsoft.com/2004/06/windows/eventlog/system">  
      <EventID>262163</EventID>  
      <Type>3</Type>  
      <SubType Name="Information">0</SubType>  
      <Level>8</Level>  
      <TimeCreated SystemTime="2006-08-04T18:45:30.8491051Z" />  
      <Source Name="System.ServiceModel" />  
       <Correlation ActivityID="{27c6331d-8998-43aa-a382-03239013a6bd}"/>  
       <Execution ProcessName="client" ProcessID="1808" ThreadID="1" />  
       <Channel />  
       <Computer>TEST1</Computer>  
   </System>  
   <ApplicationData>  
       <TraceData>  
          <DataItem>  
             <TraceRecord xmlns="http://schemas.microsoft.com/2004/10/E2ETraceEvent/TraceRecord" Severity="Information">  
                 <TraceIdentifier>http://msdn.microsoft.com/library/System.ServiceModel.Channels.MessageSent.aspx</TraceIdentifier>  
                 <Description>Sent a message over a channel.</Description>  
                 <AppDomain>client.exe</AppDomain>  
                 <Source>System.ServiceModel.Channels.ClientFramingDuplexSessionChannel/35191196</Source>  
                <ExtendedData xmlns="http://schemas.microsoft.com/2006/08/ServiceModel/MessageTransmitTraceRecord">  
  
                  <MessageProperties>  
                     <AllowOutputBatching>False</AllowOutputBatching>  
                  </MessageProperties>  
                  <MessageHeaders>  
                     <Action d4p1:mustUnderstand="1" xmlns:d4p1="http://www.w3.org/2003/05/soap-envelope" xmlns="http://www.w3.org/2005/08/addressing">http://Microsoft.ServiceModel.Samples/ICalculator/Multiply</Action>  
                     <MessageID xmlns="http://www.w3.org/2005/08/addressing">urn:uuid:7c6670d8-4c9c-496e-b6a0-2ceb6db35338</MessageID>  
                     <ActivityId CorrelationId="b02e2189-0816-4387-980c-dd8e306440f5" xmlns="http://schemas.microsoft.com/2004/09/ServiceModel/Diagnostics">27c6331d-8998-43aa-a382-03239013a6bd</ActivityId>  
                     <ReplyTo xmlns="http://www.w3.org/2005/08/addressing">  
                        <Address>http://www.w3.org/2005/08/addressing/anonymous</Address>  
                    </ReplyTo>  
                    <To d4p1:mustUnderstand="1" xmlns:d4p1="http://www.w3.org/2003/05/soap-envelope" xmlns="http://www.w3.org/2005/08/addressing">net.tcp://localhost/servicemodelsamples/service</To>  
                  </MessageHeaders>  
                  <RemoteAddress>net.tcp://localhost/servicemodelsamples/service</RemoteAddress>  
                </ExtendedData>  
            </TraceRecord>  
          </DataItem>  
       </TraceData>  
   </ApplicationData>  
</E2ETraceEvent>  
```  
  
## <a name="servicemodel-e2e-tracing"></a>Traccia E2E ServiceModel  
 Quando la `System.ServiceModel` origine di traccia viene impostato con un `switchValue` diverso da Off e `ActivityTracing`, WCF consente di creare attività e trasferimenti per l'elaborazione di WCF.  
  
 Un'attività è un'unità logica di elaborazione che raggruppa tutte le tracce relative a quell'unità di elaborazione. È possibile definire, ad esempio, un'attività per ogni richiesta. I trasferimenti creano una relazione causale tra le attività all'interno di endpoint. La propagazione dell'ID attività consente di correlare le attività attraverso gli endpoint. Questa operazione può essere eseguita impostando `propagateActivity` = `true` nella configurazione in ogni endpoint. Attività, trasferimenti e propagazione consentono di eseguire la correlazione degli errori. In questo modo è possibile individuare più rapidamente la causa radice di un errore.  
  
 Sul client, viene creata un'attività WCF per ogni chiamata al modello oggetto (ad esempio, apertura di ChannelFactory, Aggiungi, divisione e così via.) Ogni chiamata dell'operazione viene elaborata in un'attività "Processaction".  
  
 Nello screenshot seguente, estratto il [traccia e registrazione dei messaggi](../../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) esempio il pannello sinistro visualizzato l'elenco delle attività create nel processo client, ordinati in base all'ora di creazione. Di seguito è riportato un elenco cronologico delle attività:  
  
-   È stata costruita la channel factory (ClientBase).  
  
-   È stata aperta la channel factory.  
  
-   È stata elaborata l'azione di addizione.  
  
-   Configurare la sessione di sicurezza (questo si è verificato alla prima richiesta) e l'infrastruttura di sicurezza di tre elaborati i messaggi di risposta: RST, RSTR, SCT (elaborazione messaggio 1, 2, 3).  
  
-   Sono state elaborate le richieste di sottrazione, moltiplicazione e divisione.  
  
-   È stata chiusa la channel factory e, così facendo, è stata chiusa la sessione di sicurezza ed è stata elaborata la risposta del messaggio di sicurezza di annullamento.  
  
 La visualizzazione dei messaggi dell'infrastruttura di sicurezza è resa possibile da wsHttpBinding.  
  
> [!NOTE]
>  WCF, illustra i messaggi di risposta elaborati inizialmente in un'attività separata (elaborazione messaggio) vengono correlati all'attività elaborazione azione corrispondente che include il messaggio di richiesta, tramite un trasferimento. Ciò vale per i messaggi dell'infrastruttura e le richieste asincrone ed è dovuto al fatto che è necessario ispezionare il messaggio, leggere l'intestazione activityId e identificare l'attività Elaborazione azione esistente con quell'ID per correlarla ad esso. Per le richieste sincrone, viene bloccata la risposta e pertanto viene riconosciuta a quale Elaborazione azione è correlata la risposta.  
  
L'immagine seguente mostra l'attività client WCF elencate in base al momento della creazione (riquadro sinistro) e le tracce (riquadro superiore destro) e le attività annidate:

 ![Screenshot che mostra di attività elencate in base al momento della creazione di client WCF.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-client-activities-creation-time.gif)  
  
 Quando si seleziona un'attività nel riquadro sinistro, le tracce e le attività annidate compaiono nel riquadro in alto a destra. Questa è pertanto una visualizzazione gerarchica ridotta dell'elenco delle attività sulla sinistra, basato sull'attività padre selezionata. Dato che l'Elaborazione azione di aggiunta è la prima richiesta fatta, questa attività contiene l'attività Impostazione sessione di sicurezza (trasferimento a, trasferimento da) e le tracce per l'elaborazione effettiva dell'azione di aggiunta.  
  
 Se si fa doppio clic di elaborazione azione attività Aggiungi nel pannello sinistro, noteremo una rappresentazione grafica delle attività client WCF correlati da aggiungere. La prima attività sulla sinistra è l'attività radice (0000), che è l'attività predefinita. WCF trasferimenti all'esterno dell'attività di ambiente. Se non è definito, WCF trasferisce fuori da 0000. Qui, la seconda attività, Add di Elaborazione azione, viene trasferita fuori da 0. Quindi si vede l'attività di impostazione della sessione di sicurezza.  

 L'immagine seguente mostra una visualizzazione Diagramma del client WCF di attività, in particolare attività di ambiente (qui 0), elaborazione azione e configurare una sessione protetta:   

 ![Nel Visualizzatore di traccia che Mostra azione di processo e attività di ambiente del grafico.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-activities-graph-ambient-process.gif)   
  
 Nel riquadro in alto a destra, è possibile vedere tutte le tracce relative all'attività Add di Elaborazione azione. In particolare, è stato inviato il messaggio di richiesta ("Messaggio inviato tramite canale") ed è stata ricevuta la risposta ("Ricevuto un messaggio tramite canale") nella stessa attività, come illustrato nel grafico seguente. Per maggiore chiarezza, nel grafico l'attività Impostazione sessione di sicurezza è compressa.  
  
 L'immagine seguente mostra un elenco delle tracce per l'attività elaborazione azione. Si invia la richiesta e ricevere la risposta nella stessa attività.
 
 ![Screenshot del Visualizzatore di tracce che mostra un elenco delle tracce per l'attività elaborazione azione](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/process-action-traces.gif)  
  
 In questo caso, si caricano le tracce del client solo per maggiore chiarezza, ma le tracce del servizio (messaggio di richiesta ricevuto e messaggio di risposta inviato) vengono visualizzati nella stessa attività se vengono anche caricati nello strumento e `propagateActivity` è stata impostata su `true.` come illustrato in una figura seguente.  
  
 Nel servizio, il modello di attività esegue il mapping ai concetti WCF come indicato di seguito:  
  
1.  Viene costruito e aperto un ServiceHost (ciò può creare diverse attività correlate all'host, ad esempio, nel caso della protezione).  
  
2.  Viene creata un'attività di ascolto per ogni listener in ServiceHost (con trasferimenti dentro e fuori da Apertura ServiceHost).  
  
3.  Quando il listener rileva una richiesta di comunicazione iniziata dal client, trasferito a un'attività "Receivebytes", in cui vengono elaborati tutti i byte inviati dal client. In questa attività, è possibile vedere qualsiasi errore di connessione che si sia verificato durante l'interazione tra client e servizio.  
  
4.  Per ogni set di byte ricevuto che corrisponde a un messaggio, viene elaborato in un'attività "Elaborazione messaggio", in cui viene creato l'oggetto del messaggio WCF. In questa attività vengono visualizzati gli errori correlati a una envelope errata o a un messaggio in formato non valido.  
  
5.  Quando il messaggio è formato, viene trasferito a un'attività Elaborazione azione. Se `propagateActivity` è impostato su `true` sia nel client che nel servizio, l'ID di questa attività è identico a quello definito nel client e descritto in precedenza. Da questa fase si inizia a beneficiare di correlazione diretta tra gli endpoint, perché tutte le tracce emesse in WCF sono correlati alla richiesta sono in quella stessa attività, tra cui l'elaborazione del messaggio di risposta.  
  
6.  Per l'azione out-of-process, viene creata un'attività "Codice utente Execute" per isolare le tracce emesse nel codice utente da quelle emesse in WCF. Nell'esempio precedente, la traccia "Servizio invia la risposta Add" viene emessa nell'attività "Esecuzione codice utente" non nell'attività propagata dal client, se applicabile.  
  
 Nella figura seguente, la prima attività sulla sinistra è l'attività radice (0000), ed è l'attività predefinita. Le tre attività seguenti interessano l'apertura di ServiceHost. L'attività nella colonna 5 è il listener e le attività rimanenti (da 6 a 8) descrivono l'elaborazione WCF di un messaggio, dall'elaborazione dei byte all'attivazione del codice utente.  

 L'immagine seguente mostra una visualizzazione grafico delle attività del servizio WCF:   

 ![Screenshot del Visualizzatore di traccia che visualizza un elenco delle attività del servizio WCF](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-service-activities.gif)  
  
  
 Nella schermata seguente vengono illustrate le attività sia per il client che per il servizio e viene evidenziata l'attività Add di Elaborazione azione nei processi (arancione). Le frecce indicano i messaggi di richiesta e di risposta inviati e ricevuti dal client e dal servizio. Le tracce di Elaborazione azione sono separate nei processi nel grafico, ma sono riportate come parte della stessa attività nel riquadro in alto a destra. In questo riquadro è possibile vedere le tracce del client per i messaggi inviati, seguite dalle tracce del servizio per i messaggi ricevuti ed elaborati.  
  
 Le immagini seguenti viene illustrata una visualizzazione grafico di entrambe le attività del client e servizio WCF  
 
 ![Grafico dal Visualizzatore di traccia contenente entrambe le attività del client e servizio WCF.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/wcf-client-service-activities.gif)   
  
 Nello scenario di errore seguente, le tracce di errore e di avviso nel servizio e nel client sono correlate. Un'eccezione viene generata prima nel codice utente nel servizio (attività verde più a destra che include una traccia di avviso per l'eccezione relativa all'impossibilità per il servizio di elaborare la richiesta nel codice utente). Quando la risposta viene inviata al client, viene emessa di nuovo una traccia di avviso per indicare il messaggio di errore (attività rosa a sinistra). Il client chiude quindi il proprio client WCF (attività gialla in basso a sinistra), causando l'interruzione della connessione al servizio. Il servizio genera un errore (attività rosa più lunga a destra).  
  
 ![Uso del Visualizzatore di tracce](../../../../../docs/framework/wcf/diagnostics/tracing/media/wcfc-e2etrace9s.gif "wcfc_e2etrace9s")  
Correlazione dell'errore tra il servizio e il client  
  
 L'esempio usato per generare queste tracce è una serie di richieste sincrone tramite wsHttpBinding. Il grafico si presenta diversamente in caso di scenari senza protezione o con richieste asincrone, in cui l'attività Elaborazione azione include le operazioni di inizio e fine che costituiscono la chiamata asincrona e mostra i trasferimenti a un'attività di callback. Per altre informazioni sugli scenari aggiuntivi, vedere [scenari di analisi End-To-End](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md).  
  
## <a name="troubleshooting-using-the-service-trace-viewer"></a>Risoluzione dei problemi tramite Service Trace Viewer  
 Quando si caricano file di traccia nello strumento Servize Trace Viewer, è possibile selezionare qualsiasi attività rossa o gialla nel riquadro di sinistra per individuare la causa di un problema nell'applicazione. L'attività 000 in genere ha eccezioni non gestite che vengono visualizzate all'utente.  
  
  L'immagine seguente mostra come selezionare un'attività rossa o gialla per individuare la radice di un problema.   
 ![Screenshot dell'attività rossa o gialla per individuare la radice di un problema.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/service-trace-viewer.gif)  
 
  
 Nel riquadro in alto a destra, è possibile esaminare le tracce per l'attività selezionata nel riquadro di sinistra. È quindi possibile esaminare le tracce rosse o gialle in quel riquadro e vedere come sono correlate. Nel grafico precedente, le tracce di avviso sia per il client che per il servizio sono riportate nella stessa attività Elaborazione azione.  
  
 Se queste tracce non forniscono la causa radice dell'errore, è possibile usare il grafico facendo doppio clic sull'attività selezionata nel riquadro di sinistra (qui Elaborazione azione). Viene quindi visualizzato il grafico con attività correlate. È quindi possibile espandere le attività correlate (facendo il segno "+") per trovare la prima traccia emessa in rosso o giallo in un'attività correlata. Continuare a espandere le attività che si verificano subito prima della traccia rossa o gialla di interesse, seguendo i trasferimenti alle attività correlate o il flusso dei messaggi tra gli endpoint, fino a individuare la causa principale del problema.  
  
 ![Uso del Visualizzatore di tracce](../../../../../docs/framework/wcf/diagnostics/tracing/media/wcfc-e2etrace9s.gif "wcfc_e2etrace9s")  
Espansione delle attività per individuare la causa principale di un problema  
  
 Se `ActivityTracing` di ServiceModel è disattivata, ma la traccia di ServiceModel è attiva, è possibile visualizzare le tracce di ServiceModel emesse nell'attività 0000. In questo caso, tuttavia, è richiesto un maggior impegno per comprendere la correlazione di queste tracce.  
  
 Se Registrazione messaggi è attivata, è possibile utilizzare la scheda Messaggio per vedere qual è il messaggio su cui influisce l'errore. Facendo doppio clic su un messaggio in rosso o in giallo, è possibile visualizzare la rappresentazione grafica delle attività correlate. Queste attività sono quelle più strettamente legate alla richiesta in cui si è verificato un errore.  
  
 ![Screenshot del Visualizzatore di tracce con la registrazione messaggi attivata.](./media/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting/message-logging-enabled.gif)  

Per avviare la risoluzione dei problemi, è anche possibile selezionare una traccia dei messaggi rossa o gialla e fare doppio clic per individuare la causa radice.  
  
## <a name="see-also"></a>Vedere anche
- [Scenari di traccia end-to-end](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [Traccia](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
