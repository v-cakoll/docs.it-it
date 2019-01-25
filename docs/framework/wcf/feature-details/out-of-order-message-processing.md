---
title: Elaborazione di messaggi nell'ordine non corretto
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 7d908be84f22835bea744de74d278689516f3185
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698011"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="1aabd-102">Elaborazione di messaggi nell'ordine non corretto</span><span class="sxs-lookup"><span data-stu-id="1aabd-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="1aabd-103">I servizi flusso di lavoro possono dipendere da messaggi inviati in un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="1aabd-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="1aabd-104">Un servizio flusso di lavoro contiene una o più attività <xref:System.ServiceModel.Activities.Receive> e ogni attività <xref:System.ServiceModel.Activities.Receive> attende un messaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="1aabd-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="1aabd-105">Senza particolari garanzie di recapito di trasporto, i messaggi inviati dai client possono essere differiti e pertanto recapitati in un ordine inatteso dal servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1aabd-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="1aabd-106">L'implementazione di un servizio flusso di lavoro che non richiede l'invio di messaggi in un ordine specifico viene in genere effettuata mediante un'attività Parallel.</span><span class="sxs-lookup"><span data-stu-id="1aabd-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="1aabd-107">Per un protocollo dell'applicazione più complicato, il flusso di lavoro diverrebbe rapidamente molto complesso.</span><span class="sxs-lookup"><span data-stu-id="1aabd-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="1aabd-108">Il messaggio di non in ordine l'elaborazione di funzionalità in Windows Communication Foundation (WCF) consente di creare tali un flusso di lavoro senza la complessità dell'attività Parallel annidate.</span><span class="sxs-lookup"><span data-stu-id="1aabd-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="1aabd-109">L'elaborazione dei messaggi in ordine è supportato solo in canali che supportano <xref:System.ServiceModel.Channels.ReceiveContext> ad esempio le associazioni MSMQ di WCF.</span><span class="sxs-lookup"><span data-stu-id="1aabd-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="1aabd-110">Abilitazione dell'elaborazione di messaggi nell'ordine non corretto</span><span class="sxs-lookup"><span data-stu-id="1aabd-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="1aabd-111">L'elaborazione dei messaggi nell'ordine non corretto viene abilitata impostando la proprietà <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> su `true` in WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="1aabd-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="1aabd-112">Nell'esempio riportato di seguito viene illustrato come impostare la proprietà <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> nel codice.</span><span class="sxs-lookup"><span data-stu-id="1aabd-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="1aabd-113">È inoltre possibile applicare l'attributo `AllowBufferedReceive` a un servizio flusso di lavoro in XAML, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1aabd-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1aabd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aabd-114">See also</span></span>
- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="1aabd-115">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1aabd-115">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="1aabd-116">Code e sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="1aabd-116">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
