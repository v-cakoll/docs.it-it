---
title: Estensione della funzionalità di traccia
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: 59291b6a57ba602e5fea84dcd571a8d767b7cc04
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806809"
---
# <a name="extending-tracing"></a><span data-ttu-id="b154c-102">Estensione della funzionalità di traccia</span><span class="sxs-lookup"><span data-stu-id="b154c-102">Extending Tracing</span></span>
<span data-ttu-id="b154c-103">In questo esempio viene illustrato come estendere la funzionalità di traccia di Windows Communication Foundation (WCF) scrivendo le tracce di attività definite dall'utente nel codice client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="b154c-103">This sample demonstrates how to extend the Windows Communication Foundation (WCF) tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="b154c-104">In questo modo l'utente può creare attività di traccia e raggruppare le tracce in unità logiche di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b154c-104">This allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="b154c-105">È anche possibile correlare le attività tramite trasferimenti (all'interno dello stesso endpoint) e propagazione (attraverso diversi endpoint).</span><span class="sxs-lookup"><span data-stu-id="b154c-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="b154c-106">In questo esempio la traccia è abilitata sia per il client che per il servizio.</span><span class="sxs-lookup"><span data-stu-id="b154c-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="b154c-107">Per ulteriori informazioni su come abilitare la traccia nel file di configurazione client e servizio, vedere [traccia e registrazione dei messaggi](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="b154c-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="b154c-108">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b154c-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b154c-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b154c-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b154c-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b154c-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b154c-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b154c-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b154c-112">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b154c-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b154c-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b154c-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="b154c-114">Traccia e propagazione delle attività</span><span class="sxs-lookup"><span data-stu-id="b154c-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="b154c-115">La funzionalità di traccia di attività definite dall'utente consente all'utente di creare le proprie attività di traccia per raggruppare le tracce in unità logiche di lavoro, correlare le attività tramite trasferimenti e propagazione e ridurre i costi della traccia WCF (ad esempio, lo spazio su disco dei costi di un file di log).</span><span class="sxs-lookup"><span data-stu-id="b154c-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="adding-custom-sources"></a><span data-ttu-id="b154c-116">Aggiunta di origini personalizzate</span><span class="sxs-lookup"><span data-stu-id="b154c-116">Adding Custom Sources</span></span>  
 <span data-ttu-id="b154c-117">Le tracce definite dall'utente possono essere aggiunte sia al codice del client che al codice del servizio.</span><span class="sxs-lookup"><span data-stu-id="b154c-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="b154c-118">Aggiunta di origini di traccia per i file di configurazione client o del servizio consentono di queste tracce personalizzate essere registrato e visualizzato nel [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b154c-118">Adding trace sources to the client or service configuration files allow for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="b154c-119">Nell'esempio di codice seguente viene illustrato come aggiungere un'origine di traccia definita dall'utente denominata `ServerCalculatorTraceSource` al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b154c-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### <a name="correlating-activities"></a><span data-ttu-id="b154c-120">Correlazione di attività</span><span class="sxs-lookup"><span data-stu-id="b154c-120">Correlating Activities</span></span>  
 <span data-ttu-id="b154c-121">Per correlare direttamente le attività attraverso gli endpoint, l'attributo `propagateActivity` deve essere impostato su `true` nell'origine di traccia `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="b154c-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="b154c-122">Inoltre, per propagare le tracce senza passare attraverso le attività WCF, traccia attività ServiceModel deve essere spenta.</span><span class="sxs-lookup"><span data-stu-id="b154c-122">Also, to propagate traces without going through WCF activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="b154c-123">Tutto ciò è illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b154c-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b154c-124">La disattivazione dell'attività di traccia ServiceModel non equivale a disattivare il livello di traccia, indicato dalla proprietà `switchValue`.</span><span class="sxs-lookup"><span data-stu-id="b154c-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a><span data-ttu-id="b154c-125">Riduzione del costo in termini di prestazioni</span><span class="sxs-lookup"><span data-stu-id="b154c-125">Lessening Performance Cost</span></span>  
 <span data-ttu-id="b154c-126">La disattivazione di `ActivityTracing` nell'origine di traccia `System.ServiceModel` genera un file di traccia che contiene solo le tracce di attività definite dall'utente, senza includere le tracce di attività ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b154c-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="b154c-127">Di conseguenza, le dimensioni del file di log risulteranno molto più piccole.</span><span class="sxs-lookup"><span data-stu-id="b154c-127">This results in a log file of much smaller size.</span></span> <span data-ttu-id="b154c-128">Tuttavia, la possibilità per correlare le tracce di elaborazione WCF viene persa.</span><span class="sxs-lookup"><span data-stu-id="b154c-128">However, the opportunity to correlate WCF processing traces is lost.</span></span>  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b154c-129">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b154c-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b154c-130">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b154c-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b154c-131">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b154c-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="b154c-132">Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b154c-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b154c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b154c-133">See Also</span></span>  
 [<span data-ttu-id="b154c-134">Esempi di monitoraggio di AppFabric</span><span class="sxs-lookup"><span data-stu-id="b154c-134">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
