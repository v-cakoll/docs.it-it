---
title: Traccia e registrazione dei messaggi
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: 7f729e845fe552d523a46a1783404baf4e0bbfca
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44139241"
---
# <a name="tracing-and-message-logging"></a>Traccia e registrazione dei messaggi
In questo esempio viene illustrato come attivare la traccia e la registrazione dei messaggi. Le tracce risultante e i log dei messaggi vengono visualizzati utilizzando il [strumento Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
## <a name="tracing"></a>Traccia  
 Windows Communication Foundation (WCF) viene utilizzato il meccanismo di traccia definito nel <xref:System.Diagnostics> dello spazio dei nomi. In questo modello di traccia, i dati di traccia vengono prodotti da origini di traccia implementate dalle applicazioni. Ogni origine è identificata da un nome. Gli utenti della traccia creano listener di traccia per le origini di traccia per le quali desiderano recuperare informazioni. Per ricevere dati di traccia è necessario creare un listener per l'origine di traccia. In WCF, questa operazione può essere eseguita aggiungendo il codice seguente al file di configurazione del servizio o del client impostando l'origine di traccia del modello di servizio `switchValue`:  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-service.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 Per altre informazioni sulle origini di traccia, vedere la sezione origine di traccia nel [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) argomento.  
  
## <a name="activity-tracing-and-propagation"></a>Traccia e propagazione delle attività  
 Visto `ActivityTracing` abilitato e `propagateActivity` impostata su `true` nel `system.ServiceModel` origini di traccia per il client e il servizio forniscono la correlazione delle tracce all'interno di unità logiche di elaborazione (attività), più attività all'interno di endpoint ( tramite trasferimenti di attività) e per più attività che si estende su più endpoint (tramite la propagazione di ID attività).  
  
 Questi tre meccanismi (attività, trasferimenti e propagazione) possono essere utili per individuare più velocemente la causa radice di un errore utilizzando Service Trace Viewer. Per altre informazioni, vedere [utilizzando Service Trace Viewer per la visualizzazione di tracce correlate e risoluzione dei problemi](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 È possibile estendere la traccia fornita da ServiceModel creando tracce di attività definite dall'utente. Le tracce di attività definite dall'utente consentono all'utente di creare tracce delle attività per:  
  
-   Raggruppare le tracce in unità logiche di lavoro.  
  
-   Correlare le attività tramite trasferimenti e propagazione.  
  
-   Ridurre i costi della traccia di WCF (ad esempio, il costo di spazio su disco di un file di log).  
  
 Per altre informazioni sulla traccia di attività definite dall'utente, vedere la [estendendo traccia](../../../../docs/framework/wcf/samples/extending-tracing.md) esempio.  
  
## <a name="message-logging"></a>Registrazione messaggi  
 La registrazione dei messaggi può essere abilitata sia nel client e nel servizio di qualsiasi applicazione WCF. Per abilitare la registrazione messaggi è necessario aggiungere il codice seguente al client o al servizio:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels -->  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 Quando un messaggio viene registrato, il tipo di traccia dipende da se si traccia il client o il server. Ad esempio, un messaggio "Add" inviato a un client è tracciato nella categoria "TransportWrite" sul client, mentre lo stesso messaggio è tracciato nella la categoria "TransportRead" sul servizio.  
  
 Configurare il listener di traccia aggiungendo il codice seguente alla sezione <xref:System.Diagnostics> del file App.config del client o al file Web.config del servizio:  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-client.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 I messaggi vengono registrati in formato XML nella directory di destinazione specificata nel file di configurazione.  
  
> [!NOTE]
>  I file di traccia non vengono creati senza creare inizialmente la directory del log. Assicurarsi che la directory C:\log\ esista o specificare una directory alternativa per il log nella configurazione del listener. Per ulteriori informazioni, vedere le istruzioni di installazione iniziali alla fine di questo documento.  
  
 Per altre informazioni sulla registrazione dei messaggi, vedere la [configurazione della registrazione dei messaggi](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) argomento.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Prima di eseguire l'esempio di Traccia e registrazione di messaggi, creare la directory C:\log\ in cui il servizio salva i file .svclog. Il nome di questa directory è definito nel file di configurazione come il percorso per la registrazione delle tracce e dei messaggi e può essere modificato. Assegnare all'utente accesso in scrittura al servizio di rete per la directory dei log.  
  
3.  Per compilare l'edizione c#, C++ o Visual Basic .NET della soluzione, seguire le istruzioni in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a>Vedere anche  
 [Traccia](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Esempi di monitoraggio di AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
