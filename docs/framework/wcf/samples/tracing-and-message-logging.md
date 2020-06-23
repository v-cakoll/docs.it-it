---
title: Traccia e registrazione dei messaggi
description: Informazioni su come utilizzare lo strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe) per visualizzare tracce e registri messaggi utilizzando questo esempio WFC.
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: bb49334252c2415223b0f8f5559a6dc838d175e3
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246025"
---
# <a name="tracing-and-message-logging"></a><span data-ttu-id="3bcec-103">Traccia e registrazione dei messaggi</span><span class="sxs-lookup"><span data-stu-id="3bcec-103">Tracing and Message Logging</span></span>
<span data-ttu-id="3bcec-104">In questo esempio viene illustrato come attivare la traccia e la registrazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="3bcec-104">This sample demonstrates how to enable tracing and message logging.</span></span> <span data-ttu-id="3bcec-105">Le tracce e i log dei messaggi risultanti vengono visualizzati utilizzando lo [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3bcec-105">The resulting traces and message logs are viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="3bcec-106">Questo esempio è basato sul [Introduzione](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="3bcec-106">This sample is based on the [Getting Started](getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3bcec-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3bcec-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="3bcec-108">Traccia</span><span class="sxs-lookup"><span data-stu-id="3bcec-108">Tracing</span></span>  
 <span data-ttu-id="3bcec-109">Windows Communication Foundation (WCF) utilizza il meccanismo di traccia definito nello <xref:System.Diagnostics> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3bcec-109">Windows Communication Foundation (WCF) uses the tracing mechanism defined in the <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="3bcec-110">In questo modello di traccia, i dati di traccia vengono prodotti da origini di traccia implementate dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3bcec-110">In this tracing model, trace data is produced by trace sources that applications implement.</span></span> <span data-ttu-id="3bcec-111">Ogni origine è identificata da un nome.</span><span class="sxs-lookup"><span data-stu-id="3bcec-111">Each source is identified by a name.</span></span> <span data-ttu-id="3bcec-112">Gli utenti della traccia creano listener di traccia per le origini di traccia per le quali desiderano recuperare informazioni.</span><span class="sxs-lookup"><span data-stu-id="3bcec-112">Trace consumers create trace listeners for the trace sources for which they want to retrieve information.</span></span> <span data-ttu-id="3bcec-113">Per ricevere dati di traccia è necessario creare un listener per l'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="3bcec-113">To receive trace data, you must create a listener for the trace source.</span></span> <span data-ttu-id="3bcec-114">In WCF questa operazione può essere eseguita aggiungendo il codice seguente al file di configurazione del servizio o del client impostando l'origine di traccia del modello di servizio `switchValue` :</span><span class="sxs-lookup"><span data-stu-id="3bcec-114">In WCF, this can be done by adding the following code to either the service’s or client’s configuration file by setting the Service Model trace source `switchValue`:</span></span>  
  
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
  
 <span data-ttu-id="3bcec-115">Per ulteriori informazioni sulle origini di traccia, vedere la sezione origine di traccia nell'argomento [configurazione della traccia](../diagnostics/tracing/configuring-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="3bcec-115">For more information about trace sources, see the Trace Source section in the [Configuring Tracing](../diagnostics/tracing/configuring-tracing.md) topic.</span></span>  
  
## <a name="activity-tracing-and-propagation"></a><span data-ttu-id="3bcec-116">Traccia e propagazione delle attività</span><span class="sxs-lookup"><span data-stu-id="3bcec-116">Activity Tracing and Propagation</span></span>  
 <span data-ttu-id="3bcec-117">`ActivityTracing`L'abilitazione e l' `propagateActivity` impostazione di su `true` nelle `system.ServiceModel` origini di traccia per il client e il servizio forniscono la correlazione delle tracce all'interno di unità logiche di elaborazione (attività), tra le attività all'interno di endpoint (tramite trasferimenti di attività) e tra le attività che si estendono su più endpoint (tramite la propagazione dell'ID attività).</span><span class="sxs-lookup"><span data-stu-id="3bcec-117">Having `ActivityTracing` enabled and `propagateActivity` set to `true` in the `system.ServiceModel` trace sources for both the client and service provide correlation of traces within logical units of processing (activities), across activities within endpoints (through activity transfers), and across activities spanning multiple endpoints (through activity ID propagation).</span></span>  
  
 <span data-ttu-id="3bcec-118">Questi tre meccanismi (attività, trasferimenti e propagazione) possono essere utili per individuare più velocemente la causa radice di un errore utilizzando Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="3bcec-118">These three mechanisms (activities, transfers, and propagation) can help you locate the root cause of an error more quickly using the Service Trace Viewer tool.</span></span> <span data-ttu-id="3bcec-119">Per ulteriori informazioni, vedere [utilizzo del Visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e risoluzione dei problemi](../diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="3bcec-119">For more information, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="3bcec-120">È possibile estendere la traccia fornita da ServiceModel creando tracce di attività definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3bcec-120">It is possible to extend the tracing that is provided by the ServiceModel by creating user-defined activity traces.</span></span> <span data-ttu-id="3bcec-121">Le tracce di attività definite dall'utente consentono all'utente di creare tracce delle attività per:</span><span class="sxs-lookup"><span data-stu-id="3bcec-121">User-defined activity tracing allows the user to create trace activities to:</span></span>  
  
- <span data-ttu-id="3bcec-122">Raggruppare le tracce in unità logiche di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3bcec-122">Group traces into logical units of work.</span></span>  
  
- <span data-ttu-id="3bcec-123">Correlare le attività tramite trasferimenti e propagazione.</span><span class="sxs-lookup"><span data-stu-id="3bcec-123">Correlate activities through transfers and propagation.</span></span>  
  
- <span data-ttu-id="3bcec-124">Ridurre il costo delle prestazioni della traccia WCF (ad esempio, il costo dello spazio su disco di un file di log).</span><span class="sxs-lookup"><span data-stu-id="3bcec-124">Lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
 <span data-ttu-id="3bcec-125">Per ulteriori informazioni sulla traccia attività definita dall'utente, vedere l'esempio di [estensione della traccia](extending-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="3bcec-125">For more information about user-defined activity trace, please see the [Extending Tracing](extending-tracing.md) sample.</span></span>  
  
## <a name="message-logging"></a><span data-ttu-id="3bcec-126">Registrazione messaggi</span><span class="sxs-lookup"><span data-stu-id="3bcec-126">Message Logging</span></span>  
 <span data-ttu-id="3bcec-127">La registrazione dei messaggi può essere abilitata sia nel client che nel servizio di qualsiasi applicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="3bcec-127">Message logging can be enabled both on the client and service of any WCF application.</span></span> <span data-ttu-id="3bcec-128">Per abilitare la registrazione messaggi è necessario aggiungere il codice seguente al client o al servizio:</span><span class="sxs-lookup"><span data-stu-id="3bcec-128">To enable message logging, you must add the following code to either the client or service:</span></span>  
  
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
  
 <span data-ttu-id="3bcec-129">Quando un messaggio viene registrato, il tipo di traccia dipende da se si traccia il client o il server.</span><span class="sxs-lookup"><span data-stu-id="3bcec-129">When a message is recorded, the trace type depends on whether it is being traced at the client or the server.</span></span> <span data-ttu-id="3bcec-130">Ad esempio, un messaggio "Add" inviato a un client è tracciato nella categoria "TransportWrite" sul client, mentre lo stesso messaggio è tracciato nella la categoria "TransportRead" sul servizio.</span><span class="sxs-lookup"><span data-stu-id="3bcec-130">For example, an "Add" message that is sent to a client is traced under the "TransportWrite" category at the client, whereas the same message is traced under the "TransportRead" category at the service.</span></span>  
  
 <span data-ttu-id="3bcec-131">Configurare il listener di traccia aggiungendo il codice seguente alla sezione <xref:System.Diagnostics> del file App.config del client o al file Web.config del servizio:</span><span class="sxs-lookup"><span data-stu-id="3bcec-131">Configure the trace listener by adding the following code to the <xref:System.Diagnostics> section of the client's App.config file or the service's Web.config file:</span></span>  
  
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
  
 <span data-ttu-id="3bcec-132">I messaggi vengono registrati in formato XML nella directory di destinazione specificata nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3bcec-132">Messages are logged in XML format in the target directory specified in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3bcec-133">I file di traccia non vengono creati senza creare inizialmente la directory del log.</span><span class="sxs-lookup"><span data-stu-id="3bcec-133">Trace files are not created without initially creating the log directory.</span></span> <span data-ttu-id="3bcec-134">Assicurarsi che la directory C:\log\ esista o specificare una directory alternativa per il log nella configurazione del listener.</span><span class="sxs-lookup"><span data-stu-id="3bcec-134">Make sure that the directory C:\logs\ exists, or specify an alternate logging directory in the listener configuration.</span></span> <span data-ttu-id="3bcec-135">Per ulteriori informazioni, vedere le istruzioni di installazione iniziali alla fine di questo documento.</span><span class="sxs-lookup"><span data-stu-id="3bcec-135">See the initial setup instructions at the end of this document for more information.</span></span>  
  
 <span data-ttu-id="3bcec-136">Per ulteriori informazioni sulla registrazione dei messaggi, vedere l'argomento [configurazione della registrazione dei messaggi](../diagnostics/configuring-message-logging.md) .</span><span class="sxs-lookup"><span data-stu-id="3bcec-136">For more information about message logging, see the [Configuring Message Logging](../diagnostics/configuring-message-logging.md) topic.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3bcec-137">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3bcec-137">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3bcec-138">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3bcec-138">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="3bcec-139">Prima di eseguire l'esempio di Traccia e registrazione di messaggi, creare la directory C:\log\ in cui il servizio salva i file .svclog.</span><span class="sxs-lookup"><span data-stu-id="3bcec-139">Before running the Tracing and Message Logging sample, create the directory C:\logs\ for the service to write the .svclog files to.</span></span> <span data-ttu-id="3bcec-140">Il nome di questa directory è definito nel file di configurazione come il percorso per la registrazione delle tracce e dei messaggi e può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="3bcec-140">The name of this directory is defined in the configuration file as the path for the traces and messages to be logged and can be changed.</span></span> <span data-ttu-id="3bcec-141">Assegnare all'utente accesso in scrittura al servizio di rete per la directory dei log.</span><span class="sxs-lookup"><span data-stu-id="3bcec-141">Give the user Network Service write access to the logs directory.</span></span>  
  
3. <span data-ttu-id="3bcec-142">Per compilare l'edizione C#, C++ o Visual Basic .NET della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3bcec-142">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="3bcec-143">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3bcec-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3bcec-144">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3bcec-144">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3bcec-145">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3bcec-145">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3bcec-146">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="3bcec-146">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3bcec-147">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3bcec-147">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a><span data-ttu-id="3bcec-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bcec-148">See also</span></span>

- [<span data-ttu-id="3bcec-149">Traccia</span><span class="sxs-lookup"><span data-stu-id="3bcec-149">Tracing</span></span>](../diagnostics/tracing/index.md)
- <span data-ttu-id="3bcec-150">[Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3bcec-150">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
