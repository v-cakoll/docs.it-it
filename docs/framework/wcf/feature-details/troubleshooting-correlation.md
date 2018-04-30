---
title: Risoluzione dei problemi relativi alla correlazione
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98003875-233d-4512-a688-4b2a1b0b5371
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2de3a8cac6e12d898173f8181b295c3e2e461cc7
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="troubleshooting-correlation"></a><span data-ttu-id="7cbb3-102">Risoluzione dei problemi relativi alla correlazione</span><span class="sxs-lookup"><span data-stu-id="7cbb3-102">Troubleshooting Correlation</span></span>
<span data-ttu-id="7cbb3-103">La correlazione viene utilizzata per correlare i messaggi del servizio flusso di lavoro l'uno all'altro e all'istanza del flusso di lavoro corretta, ma se non viene configurata correttamente, i messaggi non verranno ricevuti e le applicazioni non funzioneranno in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-103">Correlation is used to relate workflow service messages to each other and to the correct workflow instance, but if it is not configured correctly, messages will not be received and applications will not work correctly.</span></span> <span data-ttu-id="7cbb3-104">In questo argomento viene fornita una panoramica dei metodi che consentono di risolvere i problemi relativi alla correlazione e vengono inoltre descritti alcuni dei problemi comuni che possono verificarsi durante l'utilizzo della correlazione.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-104">This topic provides an overview of several methods for troubleshooting correlation issues, and also lists some common issues that can occur when you use correlation.</span></span>  
  
## <a name="handle-the-unknownmessagereceived-event"></a><span data-ttu-id="7cbb3-105">Gestire l'evento UnknownMessageReceived</span><span class="sxs-lookup"><span data-stu-id="7cbb3-105">Handle the UnknownMessageReceived Event</span></span>  
 <span data-ttu-id="7cbb3-106">L'evento <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> si verifica quando un messaggio sconosciuto viene ricevuto da un servizio, inclusi i messaggi che non possono essere correlati a un'istanza esistente.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-106">The <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> event occurs when an unknown message is received by a service, including messages that cannot be correlated to an existing instance.</span></span> <span data-ttu-id="7cbb3-107">Per i servizi indipendenti, questo evento può essere gestito nell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-107">For self-hosted services, this event can be handled in the host application.</span></span>  
  
```csharp  
host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)  
{  
    Console.WriteLine("Unknown Message Received:");  
    Console.WriteLine(e.Message);  
};  
```  
  
 <span data-ttu-id="7cbb3-108">Per i servizi ospitati sul Web, questo evento può essere gestito derivando una classe da <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> ed eseguendo l'override del metodo <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-108">For Web-hosted services, this event can be handled by deriving a class from <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> and overriding <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>.</span></span>  
  
```csharp  
class CustomFactory : WorkflowServiceHostFactory  
{  
    protected override WorkflowServiceHost CreateWorkflowServiceHost(Activity activity, Uri[] baseAddresses)  
    {  
        // Create the WorkflowServiceHost.  
        WorkflowServiceHost host = new WorkflowServiceHost(activity, baseAddresses);  
  
        // Handle the UnknownMessageReceived event.  
        host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)  
        {  
            Console.WriteLine("Unknown Message Received:");  
            Console.WriteLine(e.Message);  
        };  
  
        return host;  
    }  
}  
```  
  
 <span data-ttu-id="7cbb3-109">Questo oggetto <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> personalizzato può essere quindi specificato nel file `svc` per il servizio.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-109">This custom <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> can then be specified in the `svc` file for the service.</span></span>  
  
```  
<% @ServiceHost Language="C#" Service="OrderServiceWorkflow" Factory="CustomFactory" %>  
```  
  
 <span data-ttu-id="7cbb3-110">Il richiamo di questo gestore consente di recuperare il messaggio tramite la proprietà <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> di <xref:System.ServiceModel.UnknownMessageReceivedEventArgs> e sarà simile al messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="7cbb3-110">When this handler is invoked, the message can be retrieved by using the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> property of the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs>, and will resemble the following message.</span></span>  
  
```Output  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <To s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://localhost:8080/OrderService</To>  
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>  
  </s:Header>  
  <s:Body>  
    <AddItem xmlns="http://tempuri.org/">  
      <Item>Books</Item>  
    </AddItem>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="7cbb3-111">L'ispezione dei messaggi inviati al gestore <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> può fornire indicazioni sui motivi della mancata correlazione del messaggio a un'istanza del servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-111">Inspecting messages dispatched to the <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> handler may provide clues about why the message did not correlate to an instance of the workflow service.</span></span>  
  
## <a name="use-tracking-to-monitor-the-progress-of-the-workflow"></a><span data-ttu-id="7cbb3-112">Utilizzare il rilevamento per monitorare lo stato di avanzamento del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="7cbb3-112">Use Tracking to Monitor the Progress of the Workflow</span></span>  
 <span data-ttu-id="7cbb3-113">Il rilevamento consente di monitorare lo stato di avanzamento del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-113">Tracking provides a way to monitor the progress of a workflow.</span></span> <span data-ttu-id="7cbb3-114">Per impostazione predefinita, vengono generati record di rilevamento per eventi del ciclo di vita di flusso del lavoro, eventi del ciclo di vita delle attività, propagazione degli errori e ripresa dei segnalibri.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-114">By default, tracking records are emitted for workflow life-cycle events, activity life-cycle events, fault propagation, and bookmark resumption.</span></span> <span data-ttu-id="7cbb3-115">Record di rilevamento personalizzati possono inoltre essere generati da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-115">Additionally, custom tracking records can be emitted by custom activities.</span></span> <span data-ttu-id="7cbb3-116">Durante la risoluzione dei problemi relativi alla correlazione, i record di rilevamento delle attività, di ripresa dei segnalibri e di propagazione degli errori costituiscono gli elementi più utili.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-116">When troubleshooting correlation, the activity tracking records, the bookmark resumption records, and the fault propagation records are the most useful.</span></span> <span data-ttu-id="7cbb3-117">I record di rilevamento delle attività possono essere utilizzati per determinare lo stato di avanzamento corrente del flusso di lavoro e consentono di identificare l'attività di messaggistica attualmente in attesa dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-117">The activity tracking records can be used to determine the current progress of the workflow and can help identify which messaging activity is currently waiting for messages.</span></span> <span data-ttu-id="7cbb3-118">I record di ripresa dei segnalibri sono utili perché indicano la ricezione di un messaggio da parte del flusso di lavoro, mentre i record di propagazione degli errori rendono disponibile un record degli errori presenti nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-118">Bookmark resumption records are useful because they indicate that a message was received by the workflow, and fault propagation records provide a record of any faults in the workflow.</span></span> <span data-ttu-id="7cbb3-119">Per abilitare il rilevamento, specificare l'oggetto <xref:System.Activities.Tracking.TrackingParticipant> desiderato nella proprietà <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> di <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-119">To enable tracking, specify the desired <xref:System.Activities.Tracking.TrackingParticipant> in the <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> of the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="7cbb3-120">Nell'esempio seguente, il `ConsoleTrackingParticipant` (dal [rilevamento personalizzato](../../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) esempio) viene configurato utilizzando il profilo di rilevamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-120">In the following example, the `ConsoleTrackingParticipant` (from the [Custom Tracking](../../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) sample) is configured by using the default tracking profile.</span></span>  
  
```csharp  
host.WorkflowExtensions.Add(new ConsoleTrackingParticipant());  
```  
  
 <span data-ttu-id="7cbb3-121">Un partecipante del rilevamento, quale ConsoleTrackingParticipant, è utile per i servizi flusso di lavoro indipendenti che dispongono di una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-121">A tracking participant such as the ConsoleTrackingParticipant is useful for self-hosted workflow services that have a console window.</span></span> <span data-ttu-id="7cbb3-122">Per un servizio ospitato sul Web, deve essere utilizzato un partecipante del rilevamento che registra le informazioni di rilevamento in un archivio durevole, ad esempio predefinito <xref:System.Activities.Tracking.EtwTrackingParticipant>, o un partecipante del rilevamento personalizzato che registra le informazioni in un file, ad esempio il `TextWriterTrackingParticpant` dal [ Rilevamento tramite un File di testo](../../../../docs/framework/windows-workflow-foundation/samples/tracking-using-a-text-file.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-122">For a Web-hosted service, a tracking participant that logs the tracking information to a durable store should be used, such as the built-in <xref:System.Activities.Tracking.EtwTrackingParticipant>, or a custom tracking participant that logs the information to a file, such as the `TextWriterTrackingParticpant` from the [Tracking Using a Text File](../../../../docs/framework/windows-workflow-foundation/samples/tracking-using-a-text-file.md) sample.</span></span>  
  
 <span data-ttu-id="7cbb3-123">Per ulteriori informazioni sulla registrazione e configurazione del rilevamento per un servizio del flusso di lavoro ospitato sul Web, vedere [flusso di lavoro rilevamento e traccia](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md), [configurazione del rilevamento per un flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)e il [ Rilevamento &#91;esempi WF&#93; ](../../../../docs/framework/windows-workflow-foundation/samples/tracking.md) esempi.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-123">For more information about tracking and configuring tracking for a Web-hosted workflow service, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md), [Configuring Tracking for a Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md), and the [Tracking &#91;WF Samples&#93;](../../../../docs/framework/windows-workflow-foundation/samples/tracking.md) samples.</span></span>  
  
## <a name="use-wcf-tracing"></a><span data-ttu-id="7cbb3-124">Utilizzare la funzionalità di traccia di WCF</span><span class="sxs-lookup"><span data-stu-id="7cbb3-124">Use WCF Tracing</span></span>  
 <span data-ttu-id="7cbb3-125">La funzionalità di traccia di WCF consente di tracciare il flusso di messaggi da e verso un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-125">WCF tracing provides tracing of the flow of messages to and from a workflow service.</span></span> <span data-ttu-id="7cbb3-126">Queste informazioni di traccia sono utili per risolvere i problemi relativi alla correlazione, in particolare per la correlazione basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-126">This tracing information is useful when troubleshooting correlation issues, especially for content-based correlation.</span></span> <span data-ttu-id="7cbb3-127">Per abilitare la traccia, specificare i listener di traccia desiderati nella sezione `system.diagnostics` del file `web.config` se il servizio flusso di lavoro è ospitato sul Web oppure nel file `app.config` se il servizio flusso di lavoro è indipendente.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-127">To enable tracing, specify the desired trace listeners in the `system.diagnostics` section of the `web.config` file if the workflow service is Web-hosted, or the `app.config` file if the workflow service is self-hosted.</span></span> <span data-ttu-id="7cbb3-128">Per includere il contenuto dei messaggi nel file di traccia, specificare `true` per `logEntireMessage` nell'elemento `messageLogging` nella sezione `diagnostics` di `system.serviceModel`.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-128">To include the contents of the messages in the trace file, specify `true` for `logEntireMessage` in the `messageLogging` element in the `diagnostics` section of `system.serviceModel`.</span></span> <span data-ttu-id="7cbb3-129">Nell'esempio seguente le informazioni di analisi, incluso il contenuto dei messaggi, sono configurate in modo da essere scritte in un file denominato `service.svclog`.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-129">In the following example, tracing information, including the content of the messages, is configured to be written to a file that is named `service.svclog`.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information" propagateActivity="true">  
        <listeners>  
          <add name="corr"/>  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="corr"/>  
        </listeners>  
      </source>  
    </sources>  
  
    <sharedListeners>  
      <add name="corr" type="System.Diagnostics.XmlWriterTraceListener" initializeData="c:\logs\service.svclog">  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
  
  <system.serviceModel>  
    <diagnostics>  
      <messageLogging logEntireMessage="true" logMalformedMessages="false"  
         logMessagesAtServiceLevel="false" logMessagesAtTransportLevel="true" maxSizeOfMessageToLog="2147483647">  
      </messageLogging>  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="7cbb3-130">Per visualizzare le informazioni contenute in `service.svclog`, [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-130">To view the trace information that is contained in `service.svclog`, the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) is used.</span></span> <span data-ttu-id="7cbb3-131">Questa soluzione è particolarmente utile per risolvere i problemi relativi alla correlazione basata sul contenuto, in quanto consente di visualizzare il contenuto del messaggio e di vedere esattamente ciò che viene passato, nonché di determinarne la corrispondenza a <xref:System.ServiceModel.CorrelationQuery> per la correlazione basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-131">This is especially useful when troubleshooting content-based correlation issues because you can view the message contents and see exactly what is being passed, and whether it matches the <xref:System.ServiceModel.CorrelationQuery> for the content-based correlation.</span></span> <span data-ttu-id="7cbb3-132">Per ulteriori informazioni sulla traccia di WCF, vedere [strumento Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), [configurazione di traccia](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md), e [utilizzando la funzionalità di traccia per risolvere i problemi dell'applicazione](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="7cbb3-132">For more information about WCF tracing, see [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md), and [Using Tracing to Troubleshoot Your Application](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>  
  
## <a name="common-context-exchange-correlation-issues"></a><span data-ttu-id="7cbb3-133">Problemi comuni relativi alla correlazione di scambio del contesto</span><span class="sxs-lookup"><span data-stu-id="7cbb3-133">Common Context Exchange Correlation Issues</span></span>  
 <span data-ttu-id="7cbb3-134">Per determinati tipi di correlazione, è necessario che venga associato un tipo specifico di associazione affinché la correlazione funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-134">Certain types of correlation require that a specific type of binding is used for the correlation to work correctly.</span></span> <span data-ttu-id="7cbb3-135">Alcuni esempi includono la correlazione request/reply che richiede un'associazione bidirezionale, quale <xref:System.ServiceModel.BasicHttpBinding>, e la correlazione di scambio del contesto per la quale è necessaria un'associazione basata sul contesto, quale <xref:System.ServiceModel.BasicHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-135">Examples include request-reply correlation, which requires a two-way binding such as <xref:System.ServiceModel.BasicHttpBinding>, and context exchange correlation, which requires a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span> <span data-ttu-id="7cbb3-136">La maggior parte delle associazioni supporta operazioni bidirezionali, pertanto questo non rappresenta un problema comune per la correlazione request/reply, mentre è disponibile solo un numero limitato di associazioni basate sul contesto, tra cui <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> e <xref:System.ServiceModel.NetTcpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-136">Most bindings support two-way operations so this is not a common issue for request-reply correlation, but there are only a handful of context-based bindings including <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, and <xref:System.ServiceModel.NetTcpContextBinding>.</span></span> <span data-ttu-id="7cbb3-137">Se non viene utilizzata una di queste associazioni, la chiamata iniziale a un servizio flusso di lavoro avrà esito positivo, ma le chiamate successive non riusciranno generando l'oggetto <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-137">If one of these bindings is not used, the initial call to a workflow service will succeed, but subsequent calls will fail with the following <xref:System.ServiceModel.FaultException>.</span></span>  
  
```Output  
There is no context attached to the incoming message for the service   
and the current operation is not marked with "CanCreateInstance = true".   
In order to communicate with this service check whether the incoming binding   
supports the context protocol and has a valid context initialized.  
```  
  
 <span data-ttu-id="7cbb3-138">Le informazioni sul contesto utilizzate per la correlazione del contesto possono essere restituite da <xref:System.ServiceModel.Activities.SendReply> all'attività <xref:System.ServiceModel.Activities.Receive> che inizializza la correlazione del contesto in caso di utilizzo di un'operazione bidirezionale oppure essere specificate dal chiamante se l'operazione è unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-138">The context information that is used for context correlation can be returned by the <xref:System.ServiceModel.Activities.SendReply> to the <xref:System.ServiceModel.Activities.Receive> activity that initializes the context correlation when using a two-way operation, or it can be specified by the caller if the operation is one-way.</span></span> <span data-ttu-id="7cbb3-139">Se il contesto non viene inviato dal chiamante o non viene restituito dal servizio flusso di lavoro, verrà restituito lo stesso oggetto <xref:System.ServiceModel.FaultException> descritto in precedenza quando viene richiamata un'operazione successiva.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-139">If the context is not sent by the caller or returned by the workflow service, then the same <xref:System.ServiceModel.FaultException> described previously will be returned when a subsequent operation is invoked.</span></span>  
  
 <span data-ttu-id="7cbb3-140">Per altre informazioni, vedere [lo scambio del contesto](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md).</span><span class="sxs-lookup"><span data-stu-id="7cbb3-140">For more information, see [Context Exchange](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md).</span></span>  
  
## <a name="common-request-reply-correlation-issues"></a><span data-ttu-id="7cbb3-141">Problemi comuni relativi alla correlazione request/reply</span><span class="sxs-lookup"><span data-stu-id="7cbb3-141">Common Request-Reply Correlation Issues</span></span>  
 <span data-ttu-id="7cbb3-142">Correlazione request / reply viene usata con un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia per implementare un'operazione bidirezionale in un servizio flusso di lavoro e con un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> coppia che richiama un'operazione bidirezionale in un altro Web servizio.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-142">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="7cbb3-143">Quando si richiama un'operazione bidirezionale in un servizio WCF, il servizio può essere un servizio imperativo tradizionale basato sul [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] o un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-143">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or it can be a workflow service.</span></span> <span data-ttu-id="7cbb3-144">Per utilizzare la correlazione request/reply, è necessario utilizzare un'associazione bidirezionale, ad esempio <xref:System.ServiceModel.BasicHttpBinding>, e che le operazioni siano bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-144">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>, and the operations must be two-way.</span></span>  
  
 <span data-ttu-id="7cbb3-145">Se il servizio del flusso di lavoro presenta operazioni bidirezionali in parallelo o la sovrapposizione <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> o <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> gestione coppie, quindi la correlazione implicita fornita da <xref:System.ServiceModel.Activities.WorkflowServiceHost>potrebbe non essere sufficiente, specialmente negli scenari di carichi di lavoro elevati, e i messaggi non possono essere indirizzati correttamente.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-145">If the workflow service has two-way operations in parallel, or overlapping <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> or <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pairs, then the implicit correlation handle management provided by <xref:System.ServiceModel.Activities.WorkflowServiceHost> may not be sufficient, especially in high-stress scenarios, and messages may not be correctly routed.</span></span> <span data-ttu-id="7cbb3-146">Per evitare che si verifichi questo problema, è consigliabile specificare sempre in modo esplicito un <xref:System.ServiceModel.Activities.CorrelationHandle> quando si utilizza la correlazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-146">To prevent this issue from occurring, we recommend that you always explicitly specify a <xref:System.ServiceModel.Activities.CorrelationHandle> when using request-reply correlation.</span></span> <span data-ttu-id="7cbb3-147">Quando si utilizza il **SendAndReceiveReply** e **ReceiveAndSendReply** modelli dalla sezione della messaggistica il **della casella degli strumenti** nella finestra di progettazione del flusso di lavoro, un <xref:System.ServiceModel.Activities.CorrelationHandle> è configurato in modo esplicito per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-147">When using the **SendAndReceiveReply** and **ReceiveAndSendReply** templates from the Messaging section of the **Toolbox** in the workflow designer, a <xref:System.ServiceModel.Activities.CorrelationHandle> is explicitly configured by default.</span></span> <span data-ttu-id="7cbb3-148">Durante la compilazione di un flusso di lavoro tramite codice, l'oggetto <xref:System.ServiceModel.Activities.CorrelationHandle> viene specificato nella proprietà <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> della prima attività nella coppia.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-148">When building a workflow by using code, the <xref:System.ServiceModel.Activities.CorrelationHandle> is specified in the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> of the first activity in the pair.</span></span> <span data-ttu-id="7cbb3-149">Nell'esempio seguente un'attività <xref:System.ServiceModel.Activities.Receive> viene configurata con una proprietà <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> esplicita specificata in <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-149">In the following example, a <xref:System.ServiceModel.Activities.Receive> activity is configured with an explicit <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> specified in the <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.</span></span>  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = ... // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 <span data-ttu-id="7cbb3-150">Persistenza non è consentita tra un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia o <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> coppia.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-150">Persistence is not permitted between a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair or a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair.</span></span> <span data-ttu-id="7cbb3-151">Viene creata un'area di non persistenza che dura fino a quando non vengono completate entrambe le attività.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-151">A no-persist zone is created that lasts until both activities have completed.</span></span> <span data-ttu-id="7cbb3-152">Se un'attività, ad esempio un'attività di ritardo si trova in quest'area di non persistenza e determina che il flusso di lavoro diventi inattivo, tale flusso di lavoro non verrà conservato anche se l'host è configurato per rendere persistenti i flussi di lavoro quando diventano inattivi.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-152">If an activity, such as a delay activity, is in this no-persist zone and causes the workflow to become idle, the workflow will not persist even if it the host is configured to persist workflows when they become idle.</span></span> <span data-ttu-id="7cbb3-153">Se un'attività, ad esempio un'attività Persist tenta di eseguire la persistenza in modo esplicito nell'area di non persistenza, viene generata un'eccezione irreversibile, il flusso di lavoro viene interrotto e al chiamante viene restituita un'eccezione <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-153">If an activity, such as a persist activity, attempts to explicitly persist in the no-persist zone, a fatal exception is thrown, the workflow aborts, and a <xref:System.ServiceModel.FaultException> is returned to the caller.</span></span> <span data-ttu-id="7cbb3-154">Il messaggio di eccezione irreversibile è "System.InvalidOperationException: blocchi di non persistenza non in grado di contenere le attività Persist".</span><span class="sxs-lookup"><span data-stu-id="7cbb3-154">The fatal exception message is "System.InvalidOperationException: Persist activities cannot be contained within no persistence blocks.".</span></span> <span data-ttu-id="7cbb3-155">Questa eccezione non viene restituita al chiamante ma può essere osservata se il rilevamento è abilitato.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-155">This exception is not returned to the caller but can be observed if tracking is enabled.</span></span> <span data-ttu-id="7cbb3-156">Il messaggio dell'eccezione <xref:System.ServiceModel.FaultException> restituita al chiamante è "WorkflowInstance '5836145b-7da2-49d0-a052-a49162adeab6' è stata completata. Impossibile eseguire l'operazione".</span><span class="sxs-lookup"><span data-stu-id="7cbb3-156">The message for the <xref:System.ServiceModel.FaultException> returned to the caller is "The operation could not be performed because WorkflowInstance '5836145b-7da2-49d0-a052-a49162adeab6' has completed".</span></span>  
  
 <span data-ttu-id="7cbb3-157">Per ulteriori informazioni sulla correlazione request/reply, vedere [Request/Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md).</span><span class="sxs-lookup"><span data-stu-id="7cbb3-157">For more information about request-reply correlation, see [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md).</span></span>  
  
## <a name="common-content-correlation-issues"></a><span data-ttu-id="7cbb3-158">Problemi comuni relativi alla correlazione di contenuto</span><span class="sxs-lookup"><span data-stu-id="7cbb3-158">Common Content Correlation Issues</span></span>  
 <span data-ttu-id="7cbb3-159">La correlazione basata sul contenuto viene utilizzata quando un servizio flusso di lavoro riceve più messaggi e una parte dei dati inclusi nei messaggi scambiati identifica l'istanza desiderata.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-159">Content-based correlation is used when a workflow service receives multiple messages and a piece of data in the exchanged messages identifies the desired instance.</span></span> <span data-ttu-id="7cbb3-160">La correlazione basata sul contenuto utilizza questi dati nel messaggio, ad esempio un numero cliente o un ID dell'ordine, per indirizzare messaggi all'istanza del flusso di lavoro corretta.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-160">Content-based correlation uses this data in the message, such as a customer number or order ID, to route messages to the correct workflow instance.</span></span> <span data-ttu-id="7cbb3-161">Contenuto della sezione vengono descritti alcuni problemi comuni che possono verificarsi durante l'utilizzo della correlazione basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-161">This section describes several common issues that may occur when using content-based correlation.</span></span>  
  
### <a name="ensure-the-identifying-data-is-unique"></a><span data-ttu-id="7cbb3-162">Assicurarsi che i dati di identificazione siano univoci</span><span class="sxs-lookup"><span data-stu-id="7cbb3-162">Ensure the Identifying Data Is Unique</span></span>  
 <span data-ttu-id="7cbb3-163">Per i dati usati per l'identificazione dell'istanza viene generato un hash in una chiave di correlazione.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-163">The data that is used to identify the instance is hashed into a correlation key.</span></span> <span data-ttu-id="7cbb3-164">È necessario verificare che i dati utilizzati per la correlazione siano univoci. In caso contrario, potrebbero verificarsi conflitti nella chiave con hash ed è possibile che i messaggi vengano indirizzati in modo errato.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-164">Care must be taken to guarantee that the data that is used for correlation is unique or else collisions in the hashed key might occur and cause messages to be misrouted.</span></span> <span data-ttu-id="7cbb3-165">Una correlazione basata esclusivamente su un nome di cliente può ad esempio generare un conflitto, poiché possono esistere più clienti con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-165">For example, a correlation based only on a customer name may cause a collision because there may be multiple customers who have the same name.</span></span> <span data-ttu-id="7cbb3-166">Non utilizzare i due punti (:) come parte dei dati utilizzati per correlare il messaggio, in quanto vengono già utilizzati per delimitare il valore e la chiave della query del messaggio per formattare la stringa per la quale verrà generato un hash.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-166">The colon (:) should not be used as part of the data that is used to correlate the message because it is already used to delimit the message query’s key and value to form the string that is subsequently hashed.</span></span> <span data-ttu-id="7cbb3-167">Se si utilizza la persistenza, verificare che i dati di identificazione correnti non siano stati utilizzati da un'istanza persistente precedente.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-167">If persistence is being used, make sure that the current identifying data has not been used by a previously persisted instance.</span></span> <span data-ttu-id="7cbb3-168">La disabilitazione temporanea della persistenza può contribuire a identificare il problema.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-168">Temporarily disabling persistence can help identify this issue.</span></span> <span data-ttu-id="7cbb3-169">La funzionalità di traccia di WCF può essere utilizzata per visualizzare la chiave di correlazione calcolata ed essere utile per eseguire il debug di questo tipo di problema.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-169">WCF tracing can be used to view the calculated correlation key and is useful for debugging this kind of issue.</span></span>  
  
### <a name="race-conditions"></a><span data-ttu-id="7cbb3-170">Condizioni di traccia</span><span class="sxs-lookup"><span data-stu-id="7cbb3-170">Race Conditions</span></span>  
 <span data-ttu-id="7cbb3-171">Tra la ricezione di un messaggio da parte del servizio e il momento in cui la correlazione viene effettivamente inizializzata si verifica un breve intervallo, durante il quale i messaggi seguenti verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-171">There is a small gap in time between the service receiving a message and the correlation actually being initialized, during which follow-up messages will be ignored.</span></span> <span data-ttu-id="7cbb3-172">Se un servizio flusso di lavoro inizializza la correlazione basata sul contenuto tramite dati passati dal client su un'operazione unidirezionale e il chiamante invia immediatamente messaggi successivi, questi messaggi verranno ignorati durante questo intervallo.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-172">If a workflow service initializes the content-based correlation by using data passed from the client over a one-way operation, and the caller sends immediate follow-up messages, these messages will be ignored during this interval.</span></span> <span data-ttu-id="7cbb3-173">È possibile evitare questo problema utilizzando un'operazione bidirezionale per inizializzare la correlazione o un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-173">This can be avoided by using a two-way operation to initialize the correlation, or by using a <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span>  
  
### <a name="correlation-query-issues"></a><span data-ttu-id="7cbb3-174">Problemi relativi alle query di correlazione</span><span class="sxs-lookup"><span data-stu-id="7cbb3-174">Correlation Query Issues</span></span>  
 <span data-ttu-id="7cbb3-175">Le query di correlazione consentono di specificare i dati di un messaggio da utilizzare per la correlazione del messaggio stesso.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-175">Correlation queries are used to specify what data in a message is used to correlate the message.</span></span> <span data-ttu-id="7cbb3-176">Questi dati vengono specificati tramite una query XPath.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-176">This data is specified by using an XPath query.</span></span> <span data-ttu-id="7cbb3-177">Se a un servizio non vengono inviati messaggi anche se tutto sembra corretto, una strategia per la risoluzione dei problemi consiste nel specificare un valore letterale corrispondente al valore dei dati del messaggio anziché una query XPath.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-177">If messages to a service are not being dispatched even though everything appears to be correct, one strategy for troubleshooting is to specify a literal value that matches the value of the message data instead of an XPath query.</span></span> <span data-ttu-id="7cbb3-178">Per specificare un valore letterale, utilizzare la funzione `string`.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-178">To specify a literal value, use the `string` function.</span></span> <span data-ttu-id="7cbb3-179">Nell'esempio seguente viene configurato un oggetto <xref:System.ServiceModel.MessageQuerySet> per l'utilizzo del valore letterale `11445` per `OrderId` e la query XPath viene impostata come commento.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-179">In the following example, a <xref:System.ServiceModel.MessageQuerySet> is configured to use a literal value of `11445` for the `OrderId` and the XPath query is commented out.</span></span>  
  
```csharp  
MessageQuerySet = new MessageQuerySet  
{  
    {  
        "OrderId",   
        //new XPathMessageQuery("sm:body()/tempuri:StartOrderResponse/tempuri:OrderId")  
        new XPathMessageQuery("string('11445')")  
    }  
}  
```  
  
 <span data-ttu-id="7cbb3-180">Se una query XPath non è configurata correttamente in modo tale che non viene recuperato alcun dato di correlazione, viene restituito un errore con il messaggio seguente: "Una query di correlazione ha restituito un set di risultati vuoto.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-180">If an XPath query is configured incorrectly such that no correlation data is retrieved, a fault is returned with the following message: "A correlation query yielded an empty result set.</span></span> <span data-ttu-id="7cbb3-181">Assicurarsi che le query di correlazione dell'endpoint siano configurate correttamente".</span><span class="sxs-lookup"><span data-stu-id="7cbb3-181">Please ensure correlation queries for the endpoint are correctly configured."</span></span> <span data-ttu-id="7cbb3-182">Un metodo rapido per risolvere questo problema consiste nel sostituire la query XPath con un valore letterale come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-182">One quick way to troubleshoot this is to replace the XPath query with a literal value as described in the previous section.</span></span> <span data-ttu-id="7cbb3-183">Questo problema può verificarsi se si utilizza il generatore di query XPath nel **Aggiungi inizializzatori di correlazione** o **definizione di CorrelatesOn** finestre di dialogo e il servizio del flusso di lavoro utilizza contratti di messaggio.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-183">This issue can occur if you use the XPath query builder in the **Add Correlation Initializers** or **CorrelatesOn Definition** dialog boxes and your workflow service uses message contracts.</span></span> <span data-ttu-id="7cbb3-184">Nell'esempio seguente viene definita una classe dei contratto di messaggio.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-184">In the following example, a message contract class is defined.</span></span>  
  
```csharp  
[MessageContract]  
public class AddItemMessage  
{  
    [MessageHeader]  
    public string CartId;  
  
    [MessageBodyMember]  
    public string Item;  
}  
```  
  
 <span data-ttu-id="7cbb3-185">Questo contratto di messaggio viene utilizzato da un'attività <xref:System.ServiceModel.Activities.Receive> in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-185">This message contract is used by a <xref:System.ServiceModel.Activities.Receive> activity in a workflow.</span></span> <span data-ttu-id="7cbb3-186">Il `CartId` nell'intestazione del messaggio viene utilizzato per correlare il messaggio all'istanza corretta.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-186">The `CartId` in the header of the message is used to correlate the message to the correct instance.</span></span> <span data-ttu-id="7cbb3-187">Se la query XPath che recupera il `CartId` viene creata utilizzando le finestre di dialogo di correlazione nella finestra di progettazione del flusso di lavoro, viene generata la seguente query XPath errata.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-187">If the XPath query that retrieves the `CartId` is created using the correlation dialogs in the workflow designer, the following incorrect XPath query is generated.</span></span>  
  
```  
sm:body()/xg0:AddItemMessage/xg0:CartId  
```  
  
 <span data-ttu-id="7cbb3-188">Questa query XPath sarebbe corretta se l'attività <xref:System.ServiceModel.Activities.Receive> utilizzasse i parametri relativi ai dati, ma dal momento che utilizza un contratto di messaggio, non è corretta.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-188">This XPath query would be correct if the <xref:System.ServiceModel.Activities.Receive> activity used parameters for the data, but since it is using a message contract it is incorrect.</span></span> <span data-ttu-id="7cbb3-189">La seguenti query XPath è la query XPath corretta per recuperare il `CartId` dall'intestazione.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-189">The following XPath query is the correct XPath query to retrieve the `CartId` from the header.</span></span>  
  
```  
sm:header()/tempuri:CartId  
```  
  
 <span data-ttu-id="7cbb3-190">Questo può essere confermato esaminando il corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-190">This can be confirmed by examining the body of the message.</span></span>  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>  
    <h:CartId xmlns:h="http://tempuri.org/">80c95b41-c98d-4660-a6c1-99412206e54c</h:CartId>  
  </s:Header>  
  <s:Body>  
    <AddItemMessage xmlns="http://tempuri.org/">  
      <Item>Books</Item>  
    </AddItemMessage>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="7cbb3-191">Nell'esempio riportato di seguito viene illustrata un'attività <xref:System.ServiceModel.Activities.Receive> configurata per un'operazione `AddItem` che utilizza il contratto di messaggio precedente per ricevere i dati.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-191">The following example shows a <xref:System.ServiceModel.Activities.Receive> activity configured for an `AddItem` operation that uses the previous message contract to receive data.</span></span> <span data-ttu-id="7cbb3-192">La query XPath è configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-192">The XPath query is correctly configured.</span></span>  
  
```xaml  
<Receive CorrelatesWith="[CCHandle] OperationName="AddItem" ServiceContractName="p:IService">  
  <Receive.CorrelatesOn>  
    <XPathMessageQuery x:Key="key1">  
      <XPathMessageQuery.Namespaces>  
        <ssx:XPathMessageContextMarkup>  
          <x:String x:Key="xg0">http://schemas.datacontract.org/2004/07/MessageContractWFService</x:String>  
        </ssx:XPathMessageContextMarkup>  
      </XPathMessageQuery.Namespaces>sm:header()/tempuri:CartId</XPathMessageQuery>  
  </Receive.CorrelatesOn>  
  <ReceiveMessageContent DeclaredMessageType="m:AddItemMessage">  
    <p1:OutArgument x:TypeArguments="m:AddItemMessage">[AddItemMessage]</p1:OutArgument>  
  </ReceiveMessageContent>  
</Receive>  
```  
  
 <span data-ttu-id="7cbb3-193">Per ulteriori informazioni sulla correlazione basata sul contenuto, vedere [in base al contenuto](../../../../docs/framework/wcf/feature-details/content-based-correlation.md) e il [calcolatrice correlata](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="7cbb3-193">For more information about content-based correlation, see [Content Based](../../../../docs/framework/wcf/feature-details/content-based-correlation.md) and the [Correlated Calculator](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md) sample.</span></span>
