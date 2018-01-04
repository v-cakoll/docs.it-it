---
title: Correlazione request/reply
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38f4fc436afbcc5922badda22e9a6e565bc19a0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="request-reply-correlation"></a><span data-ttu-id="c0ff3-102">Correlazione request/reply</span><span class="sxs-lookup"><span data-stu-id="c0ff3-102">Request-Reply Correlation</span></span>
<span data-ttu-id="c0ff3-103">Correlazione request / reply viene usata con un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia per implementare un'operazione bidirezionale in un servizio flusso di lavoro e con un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> coppia che richiama un'operazione bidirezionale in un altro Web servizio.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-103">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="c0ff3-104">Se si richiama un'operazione bidirezionale in un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], quest'ultimo può essere un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] imperativo tradizionale basato sul codice o un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-104">When invoking a two-way operation in a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, the service can be either a traditional imperative code-based [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service or it can be a workflow service.</span></span> <span data-ttu-id="c0ff3-105">Per usare la correlazione request/reply è necessario usare un'associazione bidirezionale, ad esempio <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-105">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="c0ff3-106">Se si richiama o implementa un'operazione bidirezionale, i passaggi dell'inizializzazione della correlazione sono simili e vengono trattati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-106">Whether invoking or implementing a two-way operation, the correlation initialization steps are similar and are covered in this section.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a><span data-ttu-id="c0ff3-107">Utilizzo della correlazione in un'operazione bidirezionale con Receive/SendReply</span><span class="sxs-lookup"><span data-stu-id="c0ff3-107">Using Correlation in a Two-Way Operation with Receive/SendReply</span></span>  
 <span data-ttu-id="c0ff3-108">Oggetto <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia viene usata per implementare un'operazione bidirezionale in un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-108">A <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used to implement a two-way operation in a workflow service.</span></span> <span data-ttu-id="c0ff3-109">Il runtime usa la correlazione request/reply per garantire che la risposta venga inviata al chiamante corretto.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-109">The runtime uses request-reply correlation to ensure that the reply is dispatched to the correct caller.</span></span> <span data-ttu-id="c0ff3-110">Se un flusso di lavoro viene ospitato mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, come nel caso dei servizi flusso di lavoro, è sufficiente l'inizializzazione della correlazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-110">When a workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which is the case for workflow services, then the default correlation initialization is sufficient.</span></span> <span data-ttu-id="c0ff3-111">In questo scenario, un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia viene utilizzata da un flusso di lavoro ed è richiesta alcuna configurazione di correlazione specifico.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-111">In this scenario, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used by a workflow, and no specific correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a><span data-ttu-id="c0ff3-112">Inizializzazione esplicita della correlazione Request/Reply</span><span class="sxs-lookup"><span data-stu-id="c0ff3-112">Explicitly Initializing Request-Reply Correlation</span></span>  
 <span data-ttu-id="c0ff3-113">Se altre operazioni bidirezionali vengono eseguite in parallelo, è necessario configurare la correlazione in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-113">If other two-way operations are in parallel, then correlation should be explicitly configured.</span></span> <span data-ttu-id="c0ff3-114">Questa operazione può essere eseguita specificando un <xref:System.ServiceModel.Activities.CorrelationHandle> e <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, oppure inserendo il <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> all'interno di un <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-114">This can be done by specifying a <xref:System.ServiceModel.Activities.CorrelationHandle> and <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, or by placing the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> inside of a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="c0ff3-115">In questo esempio, correlazione request / reply viene configurata su un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-115">In this example, request-reply correlation is configured on a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair.</span></span>  
  
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
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 <span data-ttu-id="c0ff3-116">Anziché configurare la correlazione in modo esplicito, è possibile usare un'attività <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-116">Instead of explicitly configuring the correlation, a <xref:System.ServiceModel.Activities.CorrelationScope> activity can be used.</span></span> <span data-ttu-id="c0ff3-117"><xref:System.ServiceModel.Activities.CorrelationScope> fornisce un oggetto <xref:System.ServiceModel.Activities.CorrelationHandle> implicito per le attività della messaggistica in esso contenute.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-117"><xref:System.ServiceModel.Activities.CorrelationScope> provides an implicit <xref:System.ServiceModel.Activities.CorrelationHandle> to the messaging activities that it contains.</span></span> <span data-ttu-id="c0ff3-118">In questo esempio, un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia è contenuta all'interno di un <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-118">In this example, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is contained inside a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="c0ff3-119">Non è richiesta alcuna configurazione di correlazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-119">No explicit correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =   
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 <span data-ttu-id="c0ff3-120">Se sono necessarie ulteriori correlazioni, è possibile configurarle usando la proprietà <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> delle rispettive attività di messaggistica mediante i tipi `CorrelationInitializer` desiderati.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-120">If additional correlations are required then they can be configured using the <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> property of the respective messaging activities using the desired `CorrelationInitializer` types.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a><span data-ttu-id="c0ff3-121">Utilizzo della correlazione in un'operazione bidirezionale con Send/ReceiveReply</span><span class="sxs-lookup"><span data-stu-id="c0ff3-121">Using Correlation in a Two-Way Operation with Send/ReceiveReply</span></span>  
 <span data-ttu-id="c0ff3-122">Mentre il <xref:System.ServiceModel.Activities.Receive> attività può essere utilizzata solo in un servizio flusso di lavoro ospitato da <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> coppia può essere usata in qualsiasi flusso di lavoro che deve richiamare un metodo su un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-122">While the <xref:System.ServiceModel.Activities.Receive> activity can only be used in a workflow service hosted by <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> and the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair can be used in any workflow that must invoke a method on a Web service.</span></span> <span data-ttu-id="c0ff3-123">Se il flusso di lavoro è ospitato usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>, viene applicata la correlazione predefinita descritta nella sezione precedente. In caso contrario, è necessario configurare la correlazione in modo esplicito mediante gli elementi <xref:System.ServiceModel.Activities.CorrelationInitializer> e <xref:System.ServiceModel.Activities.CorrelationHandle>oppure tramite la gestione esplicita dell'handle dell'elemento <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-123">If the workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> then the default correlation described in the previous section applies, but if not, then correlation must be configured either explicitly using the desired <xref:System.ServiceModel.Activities.CorrelationInitializer> and <xref:System.ServiceModel.Activities.CorrelationHandle>, or by using the implicit handle management of the <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span>  
  
 <span data-ttu-id="c0ff3-124">Quando si utilizza **Aggiungi riferimento al servizio** su un servizio con operazioni bidirezionali, vengono generate attività che eseguono il wrapping un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> attività internamente con la correlazione Request/Reply della coppia in modo esplicito specificato.</span><span class="sxs-lookup"><span data-stu-id="c0ff3-124">When using **Add Service Reference** on a service with two-way operations, activities are generated that wrap a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair activity internally with the Request/Reply correlation explicitly specified.</span></span>
