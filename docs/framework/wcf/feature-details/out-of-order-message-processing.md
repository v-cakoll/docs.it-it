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
# <a name="out-of-order-message-processing"></a>Elaborazione di messaggi nell'ordine non corretto
I servizi flusso di lavoro possono dipendere da messaggi inviati in un ordine specifico. Un servizio flusso di lavoro contiene una o più attività <xref:System.ServiceModel.Activities.Receive> e ogni attività <xref:System.ServiceModel.Activities.Receive> attende un messaggio specifico. Senza particolari garanzie di recapito di trasporto, i messaggi inviati dai client possono essere differiti e pertanto recapitati in un ordine inatteso dal servizio flusso di lavoro. L'implementazione di un servizio flusso di lavoro che non richiede l'invio di messaggi in un ordine specifico viene in genere effettuata mediante un'attività Parallel. Per un protocollo dell'applicazione più complicato, il flusso di lavoro diverrebbe rapidamente molto complesso.  La funzionalità di elaborazione dei messaggi non in ordine in Windows Communication Foundation (WCF) consente di creare un flusso di lavoro di questo tipo senza la complessità delle attività parallele nidificate. L'elaborazione dei messaggi non ordinati è supportata solo nei canali che supportano <xref:System.ServiceModel.Channels.ReceiveContext> , ad esempio i binding WCF MSMQ.  
  
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
- [Servizi flusso di lavoro](workflow-services.md)
- [Code e sessioni affidabili](queues-and-reliable-sessions.md)
