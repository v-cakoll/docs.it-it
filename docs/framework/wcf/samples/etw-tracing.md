---
title: Traccia ETW
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: a62403e61e0566d5e7b753ff951bf4b316209b6f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742119"
---
# <a name="etw-tracing"></a><span data-ttu-id="0e7e2-102">Traccia ETW</span><span class="sxs-lookup"><span data-stu-id="0e7e2-102">ETW Tracing</span></span>
<span data-ttu-id="0e7e2-103">In questo esempio viene illustrato come implementare la traccia End-to-End (E2E) utilizzando il sistema Event Tracing for Windows (ETW) e il `ETWTraceListener` fornito in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-103">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="0e7e2-104">L'esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) e include la traccia ETW.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e7e2-105">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0e7e2-106">In questo esempio si presuppone che l'utente abbia familiarità con la [traccia e la registrazione dei messaggi](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="0e7e2-106">This sample assumes that you are familiar with [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="0e7e2-107">Ogni origine di traccia nel modello di traccia <xref:System.Diagnostics> può essere dotata di più listener di traccia che determinano dove e come tracciare i dati.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-107">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="0e7e2-108">Il tipo di listener definisce il formato della registrazione dei dati di traccia.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-108">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="0e7e2-109">Nell'esempio di codice seguente viene illustrato come aggiungere il listener alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-109">The following code sample shows how to add the listener to configuration.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"   
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="0e7e2-110">Prima di utilizzare questo listener, è necessario avviare una sessione di traccia ETW.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-110">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="0e7e2-111">Questa sessione può essere avviata utilizzando Logman.exe o Tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-111">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="0e7e2-112">Questo esempio comprende un file SetupETW.bat che può essere utilizzato per configurare la sessione di traccia ETW e un file CleanupETW.bat che può essere utilizzato per chiudere la sessione e completare il file di log.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-112">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e7e2-113">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="0e7e2-114">Per ulteriori informazioni su questi strumenti, vedere <https://go.microsoft.com/fwlink/?LinkId=56580></span><span class="sxs-lookup"><span data-stu-id="0e7e2-114">For more information about these tools, see <https://go.microsoft.com/fwlink/?LinkId=56580></span></span>  
  
 <span data-ttu-id="0e7e2-115">Quando si utilizza ETWTraceListener, le tracce vengono registrate in file .etl binari.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-115">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="0e7e2-116">Se la traccia ServiceModel è attivata, tutte le tracce generate vengono visualizzate nello stesso file.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-116">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="0e7e2-117">Usare [lo strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) per visualizzare i file di log ETL e svclog.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-117">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="0e7e2-118">Il visualizzatore crea una visualizzazione end-to-end del sistema che rende possibile tracciare un messaggio dall'origine alla destinazione e al punto di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-118">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="0e7e2-119">Il listener di traccia ETW supporta i log circolari.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-119">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="0e7e2-120">Per abilitare questa funzionalità, passare a **Start**, **esegui** e digitare `cmd` per avviare una console comandi.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-120">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="0e7e2-121">Nel comando seguente, sostituire il parametro `<logfilename>` con il nome del file di log.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-121">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="0e7e2-122">Le opzioni `-f` e `-max` sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-122">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="0e7e2-123">Specificano rispettivamente il formato circolare binario e la dimensione massima del log di 1000 MB.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-123">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="0e7e2-124">L'opzione `-p` viene utilizzata per specificare il provider di traccia.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-124">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="0e7e2-125">Nell'esempio `"{411a0819-c24b-428c-83e2-26b41091702e}"` è il GUID per un l'esempio di provider ETW XML.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-125">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="0e7e2-126">Per avviare la sessione, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0e7e2-126">To start the session, type in the following command.</span></span>  
  
```console  
logman start Wcf  
```  
  
 <span data-ttu-id="0e7e2-127">Una volta completato il log, è possibile interrompere la sessione con il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-127">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```console  
logman stop Wcf  
```  
  
 <span data-ttu-id="0e7e2-128">Questo processo genera log circolari binari che è possibile elaborare con lo strumento preferito, incluso [lo strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) o Tracerpt.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-128">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="0e7e2-129">È anche possibile esaminare l'esempio di [traccia circolare](../../../../docs/framework/wcf/samples/circular-tracing.md) per ulteriori informazioni su un listener alternativo per eseguire la registrazione circolare.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-129">You can also review the [Circular Tracing](../../../../docs/framework/wcf/samples/circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0e7e2-130">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0e7e2-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0e7e2-131">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0e7e2-131">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0e7e2-132">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0e7e2-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0e7e2-133">Per utilizzare i comandi RegisterProvider.bat, SetupETW.bat e CleanupETW.bat comandi, è necessario aver eseguito l'accesso con un account Administrator locale.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-133">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="0e7e2-134">Se si utilizza Windows Vista o versione successiva, è inoltre necessario eseguire il prompt dei comandi con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-134">If you are using Windows Vista or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="0e7e2-135">A tale scopo, fare clic con il pulsante destro del mouse sull'icona del prompt dei comandi, quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-135">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="0e7e2-136">Prima di eseguire l'esempio, eseguire RegisterProvider.bat nel client e nel server.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-136">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="0e7e2-137">In questo modo viene configurato il file ETWTracingSampleLog.etl risultante per generare tracce che possono essere lette da Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-137">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="0e7e2-138">Questo file si trova nella cartella C:\log.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-138">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="0e7e2-139">Se questa cartella non esiste, deve essere creata o non verranno generate tracce.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-139">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="0e7e2-140">Eseguire quindi SetupETW.bat sui computer client e server per avviare la sessione di traccia ETW.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-140">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="0e7e2-141">Il file SetupETW.bat si trova nella cartella CS\Client.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-141">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4. <span data-ttu-id="0e7e2-142">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0e7e2-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="0e7e2-143">Una volta completato l'esempio, eseguire CleanupETW.bat per completare la creazione del file ETWTracingSampleLog.etl.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-143">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6. <span data-ttu-id="0e7e2-144">Aprire il file ETWTracingSampleLog.etl da Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-144">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="0e7e2-145">Verrà richiesto di salvare il file binario formattato come un file .svclog.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-145">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7. <span data-ttu-id="0e7e2-146">In Service Trace Viewer aprire il file .svclog creato per visualizzare le tracce ETW e ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-146">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0e7e2-147">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-147">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0e7e2-148">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-148">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="0e7e2-149">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0e7e2-150">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0e7e2-150">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="0e7e2-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e7e2-151">See also</span></span>

- <span data-ttu-id="0e7e2-152">[Esempi di monitoraggio di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0e7e2-152">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
