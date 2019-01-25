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
# <a name="out-of-order-message-processing"></a>Elaborazione di messaggi nell'ordine non corretto
I servizi flusso di lavoro possono dipendere da messaggi inviati in un ordine specifico. Un servizio flusso di lavoro contiene una o più attività <xref:System.ServiceModel.Activities.Receive> e ogni attività <xref:System.ServiceModel.Activities.Receive> attende un messaggio specifico. Senza particolari garanzie di recapito di trasporto, i messaggi inviati dai client possono essere differiti e pertanto recapitati in un ordine inatteso dal servizio flusso di lavoro. L'implementazione di un servizio flusso di lavoro che non richiede l'invio di messaggi in un ordine specifico viene in genere effettuata mediante un'attività Parallel. Per un protocollo dell'applicazione più complicato, il flusso di lavoro diverrebbe rapidamente molto complesso.  Il messaggio di non in ordine l'elaborazione di funzionalità in Windows Communication Foundation (WCF) consente di creare tali un flusso di lavoro senza la complessità dell'attività Parallel annidate. L'elaborazione dei messaggi in ordine è supportato solo in canali che supportano <xref:System.ServiceModel.Channels.ReceiveContext> ad esempio le associazioni MSMQ di WCF.  
  
## <a name="enabling-out-of-order-message-processing"></a>Abilitazione dell'elaborazione di messaggi nell'ordine non corretto  
 L'elaborazione dei messaggi nell'ordine non corretto viene abilitata impostando la proprietà <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> su `true` in WorkflowService. Nell'esempio riportato di seguito viene illustrato come impostare la proprietà <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> nel codice.  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 È inoltre possibile applicare l'attributo `AllowBufferedReceive` a un servizio flusso di lavoro in XAML, come indicato nell'esempio seguente.  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.ReceiveContext>
- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Code e sessioni affidabili](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
