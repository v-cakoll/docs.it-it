---
title: Correlazione di scambio del contesto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18f6501d2c5a97f7f267321e9cf0b06737afa5bd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="context-exchange-correlation"></a><span data-ttu-id="12e65-102">Correlazione di scambio del contesto</span><span class="sxs-lookup"><span data-stu-id="12e65-102">Context Exchange Correlation</span></span>
<span data-ttu-id="12e65-103">La correlazione del contesto dipende dal meccanismo di scambio di contesto descritto nel [specifica del protocollo .NET contesto Exchange](http://go.microsoft.com/fwlink/?LinkId=166059).</span><span class="sxs-lookup"><span data-stu-id="12e65-103">Context correlation is based on the context exchange mechanism described in the [.NET Context Exchange Protocol Specification](http://go.microsoft.com/fwlink/?LinkId=166059).</span></span> <span data-ttu-id="12e65-104">La correlazione del contesto utilizza un'intestazione del contesto nota o un cookie per correlare messaggi all'istanza corretta.</span><span class="sxs-lookup"><span data-stu-id="12e65-104">Context correlation uses a well-known context header or cookie to relate messages to the correct instance.</span></span> <span data-ttu-id="12e65-105">Per utilizzare la correlazione del contesto, è necessario utilizzare un'associazione basata sul contesto, ad esempio <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> o <xref:System.ServiceModel.NetTcpContextBinding>, sull'endpoint fornito a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="12e65-105">To use context correlation, a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, or <xref:System.ServiceModel.NetTcpContextBinding> must be used on the endpoint provided to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="12e65-106">In questo argomento viene illustrato come utilizzare la correlazione del contesto con attività di messaggistica in un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="12e65-106">This topic explains how to use context correlation with messaging activities in a workflow service.</span></span>  
  
## <a name="using-context-correlation"></a><span data-ttu-id="12e65-107">Utilizzo della correlazione del contesto</span><span class="sxs-lookup"><span data-stu-id="12e65-107">Using Context Correlation</span></span>  
 <span data-ttu-id="12e65-108">La correlazione del contesto viene utilizzata se un client deve effettuare chiamate ripetute in un servizio flusso di lavoro e quest'ultimo viene ospitato mediante una delle associazioni del contesto.</span><span class="sxs-lookup"><span data-stu-id="12e65-108">Context correlation is used when a client must make repeated calls into a workflow service and the service is hosted using one of the context bindings.</span></span> <span data-ttu-id="12e65-109">Questo tipo di correlazione viene inizializzato da un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia del servizio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="12e65-109">This type of correlation is initialized by a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair in the workflow service.</span></span> <span data-ttu-id="12e65-110">Il contesto viene nuovamente inviato al client con la risposta e quindi il client associa questo contesto a chiamate successive al servizio.</span><span class="sxs-lookup"><span data-stu-id="12e65-110">The context is sent back to the client together with the reply, and then the client attaches this context on subsequent calls to the service.</span></span>  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a><span data-ttu-id="12e65-111">Configurazione della correlazione del contesto in un servizio flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="12e65-111">Configuring Context Correlation in a Workflow Service</span></span>  
 <span data-ttu-id="12e65-112">La correlazione del contesto viene inizializzata utilizzando un oggetto <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> associato all'attività <xref:System.ServiceModel.Activities.SendReply> che risponde al messaggio in arrivo iniziale.</span><span class="sxs-lookup"><span data-stu-id="12e65-112">Context correlation is initialized by using a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> that is associated with the <xref:System.ServiceModel.Activities.SendReply> activity that replies to the initial incoming message.</span></span> <span data-ttu-id="12e65-113">Nell'esempio seguente <xref:System.ServiceModel.Activities.SendReply> viene configurato per inizializzare una correlazione di contesto.</span><span class="sxs-lookup"><span data-stu-id="12e65-113">In the following example, the <xref:System.ServiceModel.Activities.SendReply> is configured to initialize a context correlation.</span></span>  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  <span data-ttu-id="12e65-114">Nell'esempio vengono utilizzati in realtà due tipi di correlazione: correlazione di contesto e correlazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="12e65-114">In this example, there are actually two types of correlation being used: context correlation and request-reply correlation.</span></span> <span data-ttu-id="12e65-115">La correlazione di contesto viene utilizzata in modo che le chiamate provenienti dai client vengano indirizzate all'istanza corretta.</span><span class="sxs-lookup"><span data-stu-id="12e65-115">The context correlation is used so that calls from clients are routed to the correct instance.</span></span> <span data-ttu-id="12e65-116">La correlazione request/reply viene utilizzata dall'oggetto <xref:System.ServiceModel.Activities.Receive> e dalle attività <xref:System.ServiceModel.Activities.SendReply> per implementare l'operazione bidirezionale modellata da tali attività.</span><span class="sxs-lookup"><span data-stu-id="12e65-116">The request-reply correlation is used by the <xref:System.ServiceModel.Activities.Receive> and the <xref:System.ServiceModel.Activities.SendReply> activities together to implement the two-way operation modeled by these activities.</span></span> <span data-ttu-id="12e65-117">In questo esempio, solo la correlazione del contesto è configurata in modo esplicito e <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia utilizza la correlazione request / reply predefinita fornita dall'operatore implicito <xref:System.ServiceModel.Activities.CorrelationHandle> gestione di <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="12e65-117">In this example, only the context correlation is explicitly configured, and the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is using the default request-reply correlation that is provided by the implicit <xref:System.ServiceModel.Activities.CorrelationHandle> management of <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="12e65-118">Quando si utilizza il **ReceiveAndSendReply** modello di attività nella correlazione request / reply della finestra di progettazione, flusso di lavoro è configurato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="12e65-118">When using the **ReceiveAndSendReply** activity template in the workflow designer, request-reply correlation is explicitly configured.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="12e65-119">correlazione request / reply e gestione dell'handle di correlazione implicita, vedere [Request / Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) e [Panoramica della correlazione](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="12e65-119"> request-reply correlation and implicit correlation handle management, see [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) and [Correlation Overview](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="12e65-120">il **ReceiveAndSendReply** modello di attività, vedere [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span><span class="sxs-lookup"><span data-stu-id="12e65-120"> the **ReceiveAndSendReply** activity template, see [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span></span>  
  
 <span data-ttu-id="12e65-121">Le attività <xref:System.ServiceModel.Activities.Receive> successive nel servizio flusso di lavoro possono fare riferimento all'elemento <xref:System.ServiceModel.Activities.CorrelationHandle> inizializzato da <xref:System.ServiceModel.Activities.SendReply> nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="12e65-121">Subsequent <xref:System.ServiceModel.Activities.Receive> activities in the workflow service can reference the <xref:System.ServiceModel.Activities.CorrelationHandle> that was initialized by the <xref:System.ServiceModel.Activities.SendReply> in the previous example.</span></span>  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 <span data-ttu-id="12e65-122">L'endpoint viene quindi configurato sull'elemento <xref:System.ServiceModel.Activities.WorkflowServiceHost> per utilizzare un'associazione basata sul contesto, ad esempio <xref:System.ServiceModel.BasicHttpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="12e65-122">The endpoint is then configured on the <xref:System.ServiceModel.Activities.WorkflowServiceHost> to use a context-based binding, such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span>  
  
```xml  
<endpoint  
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a><span data-ttu-id="12e65-123">Configurazione della correlazione del contesto in un client flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="12e65-123">Configuring Context Correlation in a Workflow Client</span></span>  
 <span data-ttu-id="12e65-124">Se il client è un altro flusso di lavoro, è necessario configurare la correlazione del contesto anche sul client.</span><span class="sxs-lookup"><span data-stu-id="12e65-124">When the client is another workflow, context correlation must be configured on the client as well.</span></span> <span data-ttu-id="12e65-125">Nel flusso di lavoro client, il <xref:System.ServiceModel.Activities.ReceiveReply> del <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> coppia che effettua la chiamata iniziale al servizio del flusso di lavoro deve essere configurato con un <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span><span class="sxs-lookup"><span data-stu-id="12e65-125">On the client workflow, the <xref:System.ServiceModel.Activities.ReceiveReply> of the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that makes the initial call to the workflow service must be configured with a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span></span>  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 <span data-ttu-id="12e65-126">Dopo aver inizializzato la correlazione, le attività <xref:System.ServiceModel.Activities.Send> successive possono utilizzare l'oggetto <xref:System.ServiceModel.Activities.CorrelationHandle> per richiamare metodi sulla stessa istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="12e65-126">After the correlation is initialized, subsequent <xref:System.ServiceModel.Activities.Send> activities can use the <xref:System.ServiceModel.Activities.CorrelationHandle> to invoke methods on the same service instance.</span></span>  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 <span data-ttu-id="12e65-127">In questi esempi è stata configurata la correlazione del contesto in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="12e65-127">Note that in these examples, the context correlation has been explicitly configured.</span></span> <span data-ttu-id="12e65-128">Se il flusso di lavoro client non è anche ospitato in un <xref:System.ServiceModel.Activities.WorkflowServiceHost>, la correlazione deve essere configurata in modo esplicito, a meno che le attività siano contenute all'interno di un'attività <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="12e65-128">If the client workflow is not also hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, then correlation must be explicitly configured, unless the activities are contained within a <xref:System.ServiceModel.Activities.CorrelationScope> activity.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="12e65-129">la correlazione del contesto, vedere il [NetContextExchangeCorrelation](http://msdn.microsoft.com/en-us/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) esempio.</span><span class="sxs-lookup"><span data-stu-id="12e65-129"> context correlation, see the [NetContextExchangeCorrelation](http://msdn.microsoft.com/en-us/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) sample.</span></span>  
  
 <span data-ttu-id="12e65-130">Se il client che effettua chiamate al servizio flusso di lavoro non è un flusso di lavoro, può comunque effettuare chiamate ripetute a condizione che passi di nuovo in modo esplicito il contesto restituito dalla prima chiamata al servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="12e65-130">If the client that is making calls to the workflow service is not a workflow, then it can still make repeated calls as long as it explicitly passes back the context that is returned from the first call to the workflow service.</span></span> <span data-ttu-id="12e65-131">I proxy generati aggiungendo un riferimento al servizio in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] archiviano e passano questo contesto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="12e65-131">Proxies generated by adding a service reference in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] store and pass this context by default.</span></span>
