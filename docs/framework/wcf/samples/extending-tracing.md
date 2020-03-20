---
title: Estensione della funzionalità di traccia
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: a7231d340d2528a42c8cbb5294d812d52db92d54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183694"
---
# <a name="extending-tracing"></a><span data-ttu-id="7dc23-102">Estensione della funzionalità di traccia</span><span class="sxs-lookup"><span data-stu-id="7dc23-102">Extending Tracing</span></span>
<span data-ttu-id="7dc23-103">In questo esempio viene illustrato come estendere la funzionalità di traccia di Windows Communication Foundation (WCF) scrivendo tracce di attività definite dall'utente nel codice client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="7dc23-103">This sample demonstrates how to extend the Windows Communication Foundation (WCF) tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="7dc23-104">In questo modo l'utente può creare attività di traccia e raggruppare le tracce in unità logiche di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7dc23-104">This allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="7dc23-105">È anche possibile correlare le attività tramite trasferimenti (all'interno dello stesso endpoint) e propagazione (attraverso diversi endpoint).</span><span class="sxs-lookup"><span data-stu-id="7dc23-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="7dc23-106">In questo esempio la traccia è abilitata sia per il client che per il servizio.</span><span class="sxs-lookup"><span data-stu-id="7dc23-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="7dc23-107">Per ulteriori informazioni su come abilitare l'analisi nei file di configurazione del client e del servizio, vedere [Traccia e registrazione dei](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)messaggi .</span><span class="sxs-lookup"><span data-stu-id="7dc23-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="7dc23-108">Questo esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7dc23-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7dc23-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7dc23-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7dc23-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="7dc23-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7dc23-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="7dc23-111">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7dc23-112">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7dc23-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7dc23-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="7dc23-113">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="7dc23-114">Traccia e propagazione delle attività</span><span class="sxs-lookup"><span data-stu-id="7dc23-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="7dc23-115">L'analisi delle attività definite dall'utente consente all'utente di creare le proprie attività di traccia per raggruppare le tracce in unità logiche di lavoro, correlare le attività tramite trasferimenti e propagazioni e ridurre il costo delle prestazioni della traccia WCF (ad esempio, il costo dello spazio su disco di un file di registro).</span><span class="sxs-lookup"><span data-stu-id="7dc23-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="adding-custom-sources"></a><span data-ttu-id="7dc23-116">Aggiunta di origini personalizzate</span><span class="sxs-lookup"><span data-stu-id="7dc23-116">Adding Custom Sources</span></span>  
 <span data-ttu-id="7dc23-117">Le tracce definite dall'utente possono essere aggiunte sia al codice del client che al codice del servizio.</span><span class="sxs-lookup"><span data-stu-id="7dc23-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="7dc23-118">L'aggiunta di origini di traccia ai file di configurazione del client o del servizio consente di registrare e visualizzare queste tracce personalizzate nello [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="7dc23-118">Adding trace sources to the client or service configuration files allow for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="7dc23-119">Nell'esempio di codice seguente viene illustrato come aggiungere un'origine di traccia definita dall'utente denominata `ServerCalculatorTraceSource` al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7dc23-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
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
  
### <a name="correlating-activities"></a><span data-ttu-id="7dc23-120">Correlazione di attività</span><span class="sxs-lookup"><span data-stu-id="7dc23-120">Correlating Activities</span></span>  
 <span data-ttu-id="7dc23-121">Per correlare direttamente le attività attraverso gli endpoint, l'attributo `propagateActivity` deve essere impostato su `true` nell'origine di traccia `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="7dc23-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="7dc23-122">Inoltre, per propagare le tracce senza passare attraverso le attività WCF, ServiceModel Activity Tracing deve essere disattivato.</span><span class="sxs-lookup"><span data-stu-id="7dc23-122">Also, to propagate traces without going through WCF activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="7dc23-123">Tutto ciò è illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7dc23-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7dc23-124">La disattivazione dell'attività di traccia ServiceModel non equivale a disattivare il livello di traccia, indicato dalla proprietà `switchValue`.</span><span class="sxs-lookup"><span data-stu-id="7dc23-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a><span data-ttu-id="7dc23-125">Riduzione del costo in termini di prestazioni</span><span class="sxs-lookup"><span data-stu-id="7dc23-125">Lessening Performance Cost</span></span>  
 <span data-ttu-id="7dc23-126">La disattivazione di `ActivityTracing` nell'origine di traccia `System.ServiceModel` genera un file di traccia che contiene solo le tracce di attività definite dall'utente, senza includere le tracce di attività ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="7dc23-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="7dc23-127">Di conseguenza, le dimensioni del file di log risulteranno molto più piccole.</span><span class="sxs-lookup"><span data-stu-id="7dc23-127">This results in a log file of much smaller size.</span></span> <span data-ttu-id="7dc23-128">Tuttavia, l'opportunità di correlare le tracce di elaborazione WCF viene persa.</span><span class="sxs-lookup"><span data-stu-id="7dc23-128">However, the opportunity to correlate WCF processing traces is lost.</span></span>  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7dc23-129">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="7dc23-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7dc23-130">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7dc23-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="7dc23-131">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7dc23-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="7dc23-132">Per eseguire l'esempio in una configurazione a singolo o tra computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7dc23-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc23-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dc23-133">See also</span></span>

- <span data-ttu-id="7dc23-134">[Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="7dc23-134">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
