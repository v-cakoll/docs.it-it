---
title: Correlazione request/reply
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: 34a41a149e740faf0f3816bba2c9bd9b47d4996e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184549"
---
# <a name="request-reply-correlation"></a><span data-ttu-id="d8211-102">Correlazione request/reply</span><span class="sxs-lookup"><span data-stu-id="d8211-102">Request-Reply Correlation</span></span>
<span data-ttu-id="d8211-103">La correlazione richiesta-risposta <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> viene utilizzata con una coppia per implementare <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> un'operazione bidirezionale in un servizio flusso di lavoro e con una coppia che richiama un'operazione bidirezionale in un altro servizio Web.</span><span class="sxs-lookup"><span data-stu-id="d8211-103">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="d8211-104">Quando si richiama un'operazione bidirezionale in un servizio WCF, il servizio può essere un servizio Windows Communication Foundation (WCF) imperativo tradizionale o può essere un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8211-104">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based Windows Communication Foundation (WCF) service or it can be a workflow service.</span></span> <span data-ttu-id="d8211-105">Per usare la correlazione request/reply è necessario usare un'associazione bidirezionale, ad esempio <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="d8211-105">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="d8211-106">Se si richiama o implementa un'operazione bidirezionale, i passaggi dell'inizializzazione della correlazione sono simili e vengono trattati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d8211-106">Whether invoking or implementing a two-way operation, the correlation initialization steps are similar and are covered in this section.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a><span data-ttu-id="d8211-107">Utilizzo della correlazione in un'operazione bidirezionale con Receive/SendReply</span><span class="sxs-lookup"><span data-stu-id="d8211-107">Using Correlation in a Two-Way Operation with Receive/SendReply</span></span>  
 <span data-ttu-id="d8211-108"><xref:System.ServiceModel.Activities.Receive> / Una <xref:System.ServiceModel.Activities.SendReply> coppia viene utilizzata per implementare un'operazione bidirezionale in un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8211-108">A <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used to implement a two-way operation in a workflow service.</span></span> <span data-ttu-id="d8211-109">Il runtime usa la correlazione request/reply per garantire che la risposta venga inviata al chiamante corretto.</span><span class="sxs-lookup"><span data-stu-id="d8211-109">The runtime uses request-reply correlation to ensure that the reply is dispatched to the correct caller.</span></span> <span data-ttu-id="d8211-110">Se un flusso di lavoro viene ospitato mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, come nel caso dei servizi flusso di lavoro, è sufficiente l'inizializzazione della correlazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d8211-110">When a workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which is the case for workflow services, then the default correlation initialization is sufficient.</span></span> <span data-ttu-id="d8211-111">In questo scenario, una <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia viene utilizzata da un flusso di lavoro e non è necessaria alcuna configurazione di correlazione specifica.</span><span class="sxs-lookup"><span data-stu-id="d8211-111">In this scenario, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used by a workflow, and no specific correlation configuration is required.</span></span>  
  
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
  
### <a name="explicitly-initializing-request-reply-correlation"></a><span data-ttu-id="d8211-112">Inizializzazione esplicita della correlazione Request/Reply</span><span class="sxs-lookup"><span data-stu-id="d8211-112">Explicitly Initializing Request-Reply Correlation</span></span>  
 <span data-ttu-id="d8211-113">Se altre operazioni bidirezionali vengono eseguite in parallelo, è necessario configurare la correlazione in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="d8211-113">If other two-way operations are in parallel, then correlation should be explicitly configured.</span></span> <span data-ttu-id="d8211-114">Questa operazione può essere <xref:System.ServiceModel.Activities.CorrelationHandle> eseguita specificando a <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>e , o inserendo l'interno <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> di un <xref:System.ServiceModel.Activities.CorrelationScope>oggetto .</span><span class="sxs-lookup"><span data-stu-id="d8211-114">This can be done by specifying a <xref:System.ServiceModel.Activities.CorrelationHandle> and <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, or by placing the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> inside of a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="d8211-115">In questo esempio, la correlazione <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> richiesta-risposta è configurata su una coppia.</span><span class="sxs-lookup"><span data-stu-id="d8211-115">In this example, request-reply correlation is configured on a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair.</span></span>  
  
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
  
 <span data-ttu-id="d8211-116">Anziché configurare la correlazione in modo esplicito, è possibile usare un'attività <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="d8211-116">Instead of explicitly configuring the correlation, a <xref:System.ServiceModel.Activities.CorrelationScope> activity can be used.</span></span> <span data-ttu-id="d8211-117"><xref:System.ServiceModel.Activities.CorrelationScope> fornisce un oggetto <xref:System.ServiceModel.Activities.CorrelationHandle> implicito per le attività della messaggistica in esso contenute.</span><span class="sxs-lookup"><span data-stu-id="d8211-117"><xref:System.ServiceModel.Activities.CorrelationScope> provides an implicit <xref:System.ServiceModel.Activities.CorrelationHandle> to the messaging activities that it contains.</span></span> <span data-ttu-id="d8211-118">In questo esempio, una <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia <xref:System.ServiceModel.Activities.CorrelationScope>è contenuta all'interno di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="d8211-118">In this example, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is contained inside a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="d8211-119">Non è richiesta alcuna configurazione di correlazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="d8211-119">No explicit correlation configuration is required.</span></span>  
  
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
  
 <span data-ttu-id="d8211-120">Se sono necessarie ulteriori correlazioni, è possibile configurarle usando la proprietà <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> delle rispettive attività di messaggistica mediante i tipi `CorrelationInitializer` desiderati.</span><span class="sxs-lookup"><span data-stu-id="d8211-120">If additional correlations are required then they can be configured using the <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> property of the respective messaging activities using the desired `CorrelationInitializer` types.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a><span data-ttu-id="d8211-121">Utilizzo della correlazione in un'operazione bidirezionale con Send/ReceiveReply</span><span class="sxs-lookup"><span data-stu-id="d8211-121">Using Correlation in a Two-Way Operation with Send/ReceiveReply</span></span>  
 <span data-ttu-id="d8211-122">Mentre <xref:System.ServiceModel.Activities.Receive> l'attività può essere utilizzata solo <xref:System.ServiceModel.Activities.WorkflowServiceHost>in <xref:System.ServiceModel.Activities.Send> un <xref:System.ServiceModel.Activities.Send> / servizio flusso di lavoro ospitato da , mentre la <xref:System.ServiceModel.Activities.ReceiveReply> coppia può essere utilizzata in qualsiasi flusso di lavoro che deve richiamare un metodo su un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="d8211-122">While the <xref:System.ServiceModel.Activities.Receive> activity can only be used in a workflow service hosted by <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> and the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair can be used in any workflow that must invoke a method on a Web service.</span></span> <span data-ttu-id="d8211-123">Se il flusso di lavoro è ospitato usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>, viene applicata la correlazione predefinita descritta nella sezione precedente. In caso contrario, è necessario configurare la correlazione in modo esplicito mediante gli elementi <xref:System.ServiceModel.Activities.CorrelationInitializer> e <xref:System.ServiceModel.Activities.CorrelationHandle>oppure tramite la gestione esplicita dell'handle dell'elemento <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="d8211-123">If the workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> then the default correlation described in the previous section applies, but if not, then correlation must be configured either explicitly using the desired <xref:System.ServiceModel.Activities.CorrelationInitializer> and <xref:System.ServiceModel.Activities.CorrelationHandle>, or by using the implicit handle management of the <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span>  
  
 <span data-ttu-id="d8211-124">Quando si usa **Aggiungi riferimento al servizio** in un servizio <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> con operazioni bidirezionali, vengono generate attività che eseguono il wrapping di un'attività di coppia internamente con la correlazione Richiesta/Risposta specificata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="d8211-124">When using **Add Service Reference** on a service with two-way operations, activities are generated that wrap a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair activity internally with the Request/Reply correlation explicitly specified.</span></span>
