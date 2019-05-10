---
title: Traccia e registrazione dei messaggi
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: 55fdb31310c62c5d0ac7e5d963309cb1b3fe2da4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617526"
---
# <a name="tracing-and-message-logging"></a><span data-ttu-id="dfcb9-102">Traccia e registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="dfcb9-102">Tracing and Message Logging</span></span>
<span data-ttu-id="dfcb9-103">In questo esempio viene illustrato come attivare la traccia e la registrazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-103">This sample demonstrates how to enable tracing and message logging.</span></span> <span data-ttu-id="dfcb9-104">Le tracce risultante e i log dei messaggi vengono visualizzati utilizzando il [strumento Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb9-104">The resulting traces and message logs are viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="dfcb9-105">In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb9-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfcb9-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="dfcb9-107">Traccia</span><span class="sxs-lookup"><span data-stu-id="dfcb9-107">Tracing</span></span>  
 <span data-ttu-id="dfcb9-108">Windows Communication Foundation (WCF) viene utilizzato il meccanismo di traccia definito nel <xref:System.Diagnostics> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-108">Windows Communication Foundation (WCF) uses the tracing mechanism defined in the <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="dfcb9-109">In questo modello di traccia, i dati di traccia vengono prodotti da origini di traccia implementate dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-109">In this tracing model, trace data is produced by trace sources that applications implement.</span></span> <span data-ttu-id="dfcb9-110">Ogni origine è identificata da un nome.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-110">Each source is identified by a name.</span></span> <span data-ttu-id="dfcb9-111">Gli utenti della traccia creano listener di traccia per le origini di traccia per le quali desiderano recuperare informazioni.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-111">Trace consumers create trace listeners for the trace sources for which they want to retrieve information.</span></span> <span data-ttu-id="dfcb9-112">Per ricevere dati di traccia è necessario creare un listener per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-112">To receive trace data, you must create a listener for the trace source.</span></span> <span data-ttu-id="dfcb9-113">In WCF, questa operazione può essere eseguita aggiungendo il codice seguente al file di configurazione del servizio o del client impostando l'origine di traccia del modello di servizio `switchValue`:</span><span class="sxs-lookup"><span data-stu-id="dfcb9-113">In WCF, this can be done by adding the following code to either the service’s or client’s configuration file by setting the Service Model trace source `switchValue`:</span></span>  
  
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
  
 <span data-ttu-id="dfcb9-114">Per altre informazioni sulle origini di traccia, vedere la sezione origine di traccia nel [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-114">For more information about trace sources, see the Trace Source section in the [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) topic.</span></span>  
  
## <a name="activity-tracing-and-propagation"></a><span data-ttu-id="dfcb9-115">Traccia e propagazione delle attività</span><span class="sxs-lookup"><span data-stu-id="dfcb9-115">Activity Tracing and Propagation</span></span>  
 <span data-ttu-id="dfcb9-116">Visto `ActivityTracing` abilitato e `propagateActivity` impostata su `true` nel `system.ServiceModel` origini di traccia per il client e il servizio forniscono la correlazione delle tracce all'interno di unità logiche di elaborazione (attività), più attività all'interno di endpoint ( tramite trasferimenti di attività) e per più attività che si estende su più endpoint (tramite la propagazione di ID attività).</span><span class="sxs-lookup"><span data-stu-id="dfcb9-116">Having `ActivityTracing` enabled and `propagateActivity` set to `true` in the `system.ServiceModel` trace sources for both the client and service provide correlation of traces within logical units of processing (activities), across activities within endpoints (through activity transfers), and across activities spanning multiple endpoints (through activity ID propagation).</span></span>  
  
 <span data-ttu-id="dfcb9-117">Questi tre meccanismi (attività, trasferimenti e propagazione) possono essere utili per individuare più velocemente la causa radice di un errore utilizzando Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-117">These three mechanisms (activities, transfers, and propagation) can help you locate the root cause of an error more quickly using the Service Trace Viewer tool.</span></span> <span data-ttu-id="dfcb9-118">Per altre informazioni, vedere [utilizzando Service Trace Viewer per la visualizzazione di tracce correlate e risoluzione dei problemi](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb9-118">For more information, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="dfcb9-119">È possibile estendere la traccia fornita da ServiceModel creando tracce di attività definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-119">It is possible to extend the tracing that is provided by the ServiceModel by creating user-defined activity traces.</span></span> <span data-ttu-id="dfcb9-120">Le tracce di attività definite dall'utente consentono all'utente di creare tracce delle attività per:</span><span class="sxs-lookup"><span data-stu-id="dfcb9-120">User-defined activity tracing allows the user to create trace activities to:</span></span>  
  
- <span data-ttu-id="dfcb9-121">Raggruppare le tracce in unità logiche di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-121">Group traces into logical units of work.</span></span>  
  
- <span data-ttu-id="dfcb9-122">Correlare le attività tramite trasferimenti e propagazione.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-122">Correlate activities through transfers and propagation.</span></span>  
  
- <span data-ttu-id="dfcb9-123">Ridurre i costi della traccia di WCF (ad esempio, il costo di spazio su disco di un file di log).</span><span class="sxs-lookup"><span data-stu-id="dfcb9-123">Lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
 <span data-ttu-id="dfcb9-124">Per altre informazioni sulla traccia di attività definite dall'utente, vedere la [estendendo traccia](../../../../docs/framework/wcf/samples/extending-tracing.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-124">For more information about user-defined activity trace, please see the [Extending Tracing](../../../../docs/framework/wcf/samples/extending-tracing.md) sample.</span></span>  
  
## <a name="message-logging"></a><span data-ttu-id="dfcb9-125">Registrazione messaggi</span><span class="sxs-lookup"><span data-stu-id="dfcb9-125">Message Logging</span></span>  
 <span data-ttu-id="dfcb9-126">La registrazione dei messaggi può essere abilitata sia nel client e nel servizio di qualsiasi applicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-126">Message logging can be enabled both on the client and service of any WCF application.</span></span> <span data-ttu-id="dfcb9-127">Per abilitare la registrazione messaggi è necessario aggiungere il codice seguente al client o al servizio:</span><span class="sxs-lookup"><span data-stu-id="dfcb9-127">To enable message logging, you must add the following code to either the client or service:</span></span>  
  
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
  
 <span data-ttu-id="dfcb9-128">Quando un messaggio viene registrato, il tipo di traccia dipende da se si traccia il client o il server.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-128">When a message is recorded, the trace type depends on whether it is being traced at the client or the server.</span></span> <span data-ttu-id="dfcb9-129">Ad esempio, un messaggio "Add" inviato a un client è tracciato nella categoria "TransportWrite" sul client, mentre lo stesso messaggio è tracciato nella la categoria "TransportRead" sul servizio.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-129">For example, an "Add" message that is sent to a client is traced under the "TransportWrite" category at the client, whereas the same message is traced under the "TransportRead" category at the service.</span></span>  
  
 <span data-ttu-id="dfcb9-130">Configurare il listener di traccia aggiungendo il codice seguente alla sezione <xref:System.Diagnostics> del file App.config del client o al file Web.config del servizio:</span><span class="sxs-lookup"><span data-stu-id="dfcb9-130">Configure the trace listener by adding the following code to the <xref:System.Diagnostics> section of the client's App.config file or the service's Web.config file:</span></span>  
  
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
  
 <span data-ttu-id="dfcb9-131">I messaggi vengono registrati in formato XML nella directory di destinazione specificata nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-131">Messages are logged in XML format in the target directory specified in the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfcb9-132">I file di traccia non vengono creati senza creare inizialmente la directory del log.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-132">Trace files are not created without initially creating the log directory.</span></span> <span data-ttu-id="dfcb9-133">Assicurarsi che la directory C:\log\ esista o specificare una directory alternativa per il log nella configurazione del listener.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-133">Make sure that the directory C:\logs\ exists, or specify an alternate logging directory in the listener configuration.</span></span> <span data-ttu-id="dfcb9-134">Per ulteriori informazioni, vedere le istruzioni di installazione iniziali alla fine di questo documento.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-134">See the initial setup instructions at the end of this document for more information.</span></span>  
  
 <span data-ttu-id="dfcb9-135">Per altre informazioni sulla registrazione dei messaggi, vedere la [configurazione della registrazione dei messaggi](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-135">For more information about message logging, see the [Configuring Message Logging](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) topic.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dfcb9-136">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="dfcb9-136">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="dfcb9-137">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb9-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="dfcb9-138">Prima di eseguire l'esempio di Traccia e registrazione di messaggi, creare la directory C:\log\ in cui il servizio salva i file .svclog.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-138">Before running the Tracing and Message Logging sample, create the directory C:\logs\ for the service to write the .svclog files to.</span></span> <span data-ttu-id="dfcb9-139">Il nome di questa directory è definito nel file di configurazione come il percorso per la registrazione delle tracce e dei messaggi e può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-139">The name of this directory is defined in the configuration file as the path for the traces and messages to be logged and can be changed.</span></span> <span data-ttu-id="dfcb9-140">Assegnare all'utente accesso in scrittura al servizio di rete per la directory dei log.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-140">Give the user Network Service write access to the logs directory.</span></span>  
  
3. <span data-ttu-id="dfcb9-141">Per compilare l'edizione c#, C++ o Visual Basic .NET della soluzione, seguire le istruzioni in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb9-141">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="dfcb9-142">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb9-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dfcb9-143">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-143">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dfcb9-144">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dfcb9-145">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dfcb9-146">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="dfcb9-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a><span data-ttu-id="dfcb9-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfcb9-147">See also</span></span>

- [<span data-ttu-id="dfcb9-148">Traccia</span><span class="sxs-lookup"><span data-stu-id="dfcb9-148">Tracing</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="dfcb9-149">Esempi di monitoraggio di AppFabric</span><span class="sxs-lookup"><span data-stu-id="dfcb9-149">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
