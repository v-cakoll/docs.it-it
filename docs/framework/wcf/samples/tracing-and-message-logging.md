---
title: Traccia e registrazione dei messaggi
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: 9ffb7a99540b953fc93a22d2296caf86f294d25d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143824"
---
# <a name="tracing-and-message-logging"></a>Traccia e registrazione dei messaggi
In questo esempio viene illustrato come attivare la traccia e la registrazione dei messaggi. Le tracce e i log dei messaggi risultanti vengono visualizzati utilizzando lo strumento Visualizzatore di tracce dei servizi [(SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
## <a name="tracing"></a>Traccia  
 Windows Communication Foundation (WCF) usa il <xref:System.Diagnostics> meccanismo di traccia definito nello spazio dei nomi. In questo modello di traccia, i dati di traccia vengono prodotti da origini di traccia implementate dalle applicazioni. Ogni origine è identificata da un nome. Gli utenti della traccia creano listener di traccia per le origini di traccia per le quali desiderano recuperare informazioni. Per ricevere dati di traccia è necessario creare un listener per l'origine di traccia. In WCF, questa operazione può essere eseguita aggiungendo il codice seguente al file di configurazione `switchValue`del servizio o del client impostando l'origine di traccia del modello di servizio:In WCF, this can be done by adding the following code to either the service's or client's configuration file by setting the Service Model trace source :  
  
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
  
 Per altre informazioni sulle origini di traccia, vedere la sezione Origine traccia nell'argomento Configurazione della [traccia.](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
## <a name="activity-tracing-and-propagation"></a>Traccia e propagazione delle attività  
 Avendo `ActivityTracing` abilitato `propagateActivity` e `true` impostato `system.ServiceModel` su nelle origini di traccia per il client e il servizio forniscono la correlazione delle tracce all'interno di unità logiche di elaborazione (attività), tra le attività all'interno degli endpoint (tramite trasferimenti di attività) e tra le attività che si estendono su più endpoint (tramite la propagazione dell'ID attività).  
  
 Questi tre meccanismi (attività, trasferimenti e propagazione) possono essere utili per individuare più velocemente la causa radice di un errore utilizzando Service Trace Viewer. Per ulteriori informazioni, vedere Utilizzo del visualizzatore di tracce dei servizi [per la visualizzazione delle tracce correlate e la risoluzione dei problemi](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 È possibile estendere la traccia fornita da ServiceModel creando tracce di attività definite dall'utente. Le tracce di attività definite dall'utente consentono all'utente di creare tracce delle attività per:  
  
- Raggruppare le tracce in unità logiche di lavoro.  
  
- Correlare le attività tramite trasferimenti e propagazione.  
  
- Ridurre il costo delle prestazioni della traccia WCF (ad esempio, il costo dello spazio su disco di un file di log).  
  
 Per altre informazioni sulla traccia dell'attività definita dall'utente, vedere l'esempio [Estensione della traccia.](../../../../docs/framework/wcf/samples/extending-tracing.md)  
  
## <a name="message-logging"></a>Registrazione messaggi  
 La registrazione dei messaggi può essere abilitata sia nel client che nel servizio di qualsiasi applicazione WCF. Per abilitare la registrazione messaggi è necessario aggiungere il codice seguente al client o al servizio:  
  
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
> I file di traccia non vengono creati senza creare inizialmente la directory del log. Assicurarsi che la directory C:\log\ esista o specificare una directory alternativa per il log nella configurazione del listener. Per ulteriori informazioni, vedere le istruzioni di installazione iniziali alla fine di questo documento.  
  
 Per altre informazioni sulla registrazione dei messaggi, vedere l'argomento Configurazione della [registrazione dei](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) messaggi.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Prima di eseguire l'esempio di Traccia e registrazione di messaggi, creare la directory C:\log\ in cui il servizio salva i file .svclog. Il nome di questa directory è definito nel file di configurazione come il percorso per la registrazione delle tracce e dei messaggi e può essere modificato. Assegnare all'utente accesso in scrittura al servizio di rete per la directory dei log.  
  
3. Per compilare l'edizione della soluzione in C, C, o Visual Basic .NET, seguire le istruzioni riportate in [Compilazione degli esempi](../../../../docs/framework/wcf/samples/building-the-samples.md)di Windows Communication Foundation .  
  
4. Per eseguire l'esempio in una configurazione a singolo o tra computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a>Vedere anche

- [Traccia](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
