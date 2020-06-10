---
title: Elaborazione di messaggi nell'ordine non corretto
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 7930f26cf5957158a16d65085267cf1bab2e4504
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598723"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="c7540-102">Elaborazione di messaggi nell'ordine non corretto</span><span class="sxs-lookup"><span data-stu-id="c7540-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="c7540-103">I servizi flusso di lavoro possono dipendere da messaggi inviati in un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="c7540-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="c7540-104">Un servizio flusso di lavoro contiene una o più attività <xref:System.ServiceModel.Activities.Receive> e ogni attività <xref:System.ServiceModel.Activities.Receive> attende un messaggio specifico.</span><span class="sxs-lookup"><span data-stu-id="c7540-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="c7540-105">Senza particolari garanzie di recapito di trasporto, i messaggi inviati dai client possono essere differiti e pertanto recapitati in un ordine inatteso dal servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c7540-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="c7540-106">L'implementazione di un servizio flusso di lavoro che non richiede l'invio di messaggi in un ordine specifico viene in genere effettuata mediante un'attività Parallel.</span><span class="sxs-lookup"><span data-stu-id="c7540-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="c7540-107">Per un protocollo dell'applicazione più complicato, il flusso di lavoro diverrebbe rapidamente molto complesso.</span><span class="sxs-lookup"><span data-stu-id="c7540-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="c7540-108">La funzionalità di elaborazione dei messaggi non in ordine in Windows Communication Foundation (WCF) consente di creare un flusso di lavoro di questo tipo senza la complessità delle attività parallele nidificate.</span><span class="sxs-lookup"><span data-stu-id="c7540-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="c7540-109">L'elaborazione dei messaggi non ordinati è supportata solo nei canali che supportano <xref:System.ServiceModel.Channels.ReceiveContext> , ad esempio i binding WCF MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c7540-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="c7540-110">Abilitazione dell'elaborazione di messaggi nell'ordine non corretto</span><span class="sxs-lookup"><span data-stu-id="c7540-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="c7540-111">L'elaborazione dei messaggi nell'ordine non corretto viene abilitata impostando la proprietà <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> su `true` in WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="c7540-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="c7540-112">Nell'esempio riportato di seguito viene illustrato come impostare la proprietà <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> nel codice.</span><span class="sxs-lookup"><span data-stu-id="c7540-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="c7540-113">È inoltre possibile applicare l'attributo `AllowBufferedReceive` a un servizio flusso di lavoro in XAML, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c7540-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7540-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7540-114">See also</span></span>

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="c7540-115">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c7540-115">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="c7540-116">Code e sessioni affidabili</span><span class="sxs-lookup"><span data-stu-id="c7540-116">Queues and Reliable Sessions</span></span>](queues-and-reliable-sessions.md)
