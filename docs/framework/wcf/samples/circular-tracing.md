---
title: Analisi circolare
ms.date: 03/30/2017
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
ms.openlocfilehash: 0b1d62177828b52b21a3e43cc083f79c27878804
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741971"
---
# <a name="circular-tracing"></a><span data-ttu-id="be8e7-102">Analisi circolare</span><span class="sxs-lookup"><span data-stu-id="be8e7-102">Circular Tracing</span></span>

<span data-ttu-id="be8e7-103">Questo esempio illustra l'implementazione di un listener traccia circolare del buffer.</span><span class="sxs-lookup"><span data-stu-id="be8e7-103">This sample demonstrates the implementation of a circular buffer trace listener.</span></span> <span data-ttu-id="be8e7-104">Un scenario comune per i servizi in un ambiente di produzione è avere servizi disponibili per lunghi periodi e avere la registrazione analisi attivata a un livello basso.</span><span class="sxs-lookup"><span data-stu-id="be8e7-104">A common scenario for production services is to have services that are available for long periods of time and to have trace logging enabled at a low level.</span></span> <span data-ttu-id="be8e7-105">Questi servizi utilizzano molto spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="be8e7-105">These services consume a lot of disk space.</span></span> <span data-ttu-id="be8e7-106">Durante la risoluzione dei problemi di un servizio, i dati più recenti del registro di traccia sono attinenti alla risoluzione di un problema.</span><span class="sxs-lookup"><span data-stu-id="be8e7-106">When troubleshooting a service, the most recent data in the trace log is relevant to solving a problem.</span></span> <span data-ttu-id="be8e7-107">Questo esempio illustra l'implementazione di un listener di traccia circolare del buffer in cui solo tracce più recenti vengono tenute su disco fino al raggiungimento di una quantità configurabile di dati.</span><span class="sxs-lookup"><span data-stu-id="be8e7-107">This sample demonstrates an implementation of a circular buffer trace listener in which only the most recent traces are kept on disk up to a configurable amount of data.</span></span> <span data-ttu-id="be8e7-108">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) e include un listener di traccia personalizzato.</span><span class="sxs-lookup"><span data-stu-id="be8e7-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes a custom tracing listener.</span></span>

> [!NOTE]
> <span data-ttu-id="be8e7-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="be8e7-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="be8e7-110">Questo esempio presuppone che si abbia familiarità con l'esempio di [traccia e registrazione dei messaggi](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) e che sia stata letta la documentazione fornita per l'esempio di [traccia e registrazione dei messaggi](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) .</span><span class="sxs-lookup"><span data-stu-id="be8e7-110">This sample assumes that you are familiar with the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample and have read the documentation provided for the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>

## <a name="circular-buffer-trace-listener"></a><span data-ttu-id="be8e7-111">Listener di traccia circolare del buffer</span><span class="sxs-lookup"><span data-stu-id="be8e7-111">Circular Buffer Trace Listener</span></span>

<span data-ttu-id="be8e7-112">Il concetto alla base dell'implementazione del Listener di traccia circolare del buffer è avere due file in grado di contenere, singolarmente, la metà dei dati totali che si desidera inserire nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="be8e7-112">The concept behind the implementation of the Circular Buffer Trace Listener is to have two files that can each store up to half of the total desired trace log data.</span></span> <span data-ttu-id="be8e7-113">Il listener crea un file e scrive in quel file fino al raggiungimento della metà dei dati totali, a quel punto passa a scrivere sul secondo file.</span><span class="sxs-lookup"><span data-stu-id="be8e7-113">The listener creates one file and writes to that file until it reaches the limit of half of the data size, at which point it switches to a second file.</span></span> <span data-ttu-id="be8e7-114">Quando il listener raggiunge il limite per il secondo file - sovrascrive il primo file con le nuove tracce.</span><span class="sxs-lookup"><span data-stu-id="be8e7-114">When the listener reaches the limit for the second file - it overwrites the first file with new traces.</span></span>

<span data-ttu-id="be8e7-115">Questo listener deriva dalla `XmlWriteTraceListener` e consente la visualizzazione dei log con lo [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="be8e7-115">This listener derives from the `XmlWriteTraceListener` and allows the logs to be viewed with the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="be8e7-116">Quando si desidera visualizzare il log, i due file possono essere facilmente ricombinati aprendoli contemporaneamente nello strumento Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="be8e7-116">When attempting to view the logs, the two log files can be easily recombined by opening both of the log files at the same time in the Service Trace Viewer tool.</span></span> <span data-ttu-id="be8e7-117">Lo strumento Service Trace Viewer si occupa automaticamente di ordinare le tracce, che verranno visualizzate nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="be8e7-117">The Service Trace Viewer tool automatically takes care of sorting the traces so that they appear in the correct order.</span></span>

## <a name="configuration"></a><span data-ttu-id="be8e7-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="be8e7-118">Configuration</span></span>

<span data-ttu-id="be8e7-119">Un servizio può essere configurato per utilizzare il Listener di traccia circolare del buffer aggiungendo il codice seguente per un listener e gli elementi di origine.</span><span class="sxs-lookup"><span data-stu-id="be8e7-119">A service can be configured to use the Circular Buffer Trace Listener by adding the following code for a listener and source elements.</span></span> <span data-ttu-id="be8e7-120">La dimensione massima del file viene specificata impostando l'attributo `maxFileSizeKB` durante la configurazione listener di traccia circolare,</span><span class="sxs-lookup"><span data-stu-id="be8e7-120">The max file size is specified by setting the `maxFileSizeKB` attribute in the circular trace listener's configuration.</span></span> <span data-ttu-id="be8e7-121">come illustrato nell'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="be8e7-121">This is demonstrated in the following code.</span></span>

```xml
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel" switchValue="Information,ActivityTracing" propagateActivity="true">
      <listeners>
        <add name="CircularTraceListener" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add name="CircularTraceListener" type="Microsoft. Samples.ServiceModel.CircularTraceListener,CircularTraceListener"
         initializeData="c:\logs\CircularTracing-service.svclog" maxFileSizeKB="100" />
  </sharedListeners>
  <trace autoflush="true" />
</system.diagnostics>
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="be8e7-122">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="be8e7-122">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="be8e7-123">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="be8e7-123">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="be8e7-124">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="be8e7-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="be8e7-125">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="be8e7-125">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be8e7-126">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="be8e7-126">The samples may already be installed on your computer.</span></span> <span data-ttu-id="be8e7-127">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="be8e7-127">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="be8e7-128">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="be8e7-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="be8e7-129">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="be8e7-129">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`

## <a name="see-also"></a><span data-ttu-id="be8e7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be8e7-130">See also</span></span>

- <span data-ttu-id="be8e7-131">[Esempi di monitoraggio di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="be8e7-131">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
