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
# <a name="request-reply-correlation"></a>Correlazione request/reply
La correlazione richiesta-risposta <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> viene utilizzata con una coppia per implementare <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> un'operazione bidirezionale in un servizio flusso di lavoro e con una coppia che richiama un'operazione bidirezionale in un altro servizio Web. Quando si richiama un'operazione bidirezionale in un servizio WCF, il servizio può essere un servizio Windows Communication Foundation (WCF) imperativo tradizionale o può essere un servizio flusso di lavoro. Per usare la correlazione request/reply è necessario usare un'associazione bidirezionale, ad esempio <xref:System.ServiceModel.BasicHttpBinding>. Se si richiama o implementa un'operazione bidirezionale, i passaggi dell'inizializzazione della correlazione sono simili e vengono trattati in questa sezione.  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a>Utilizzo della correlazione in un'operazione bidirezionale con Receive/SendReply  
 <xref:System.ServiceModel.Activities.Receive> / Una <xref:System.ServiceModel.Activities.SendReply> coppia viene utilizzata per implementare un'operazione bidirezionale in un servizio flusso di lavoro. Il runtime usa la correlazione request/reply per garantire che la risposta venga inviata al chiamante corretto. Se un flusso di lavoro viene ospitato mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, come nel caso dei servizi flusso di lavoro, è sufficiente l'inizializzazione della correlazione predefinita. In questo scenario, una <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia viene utilizzata da un flusso di lavoro e non è necessaria alcuna configurazione di correlazione specifica.  
  
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
  
### <a name="explicitly-initializing-request-reply-correlation"></a>Inizializzazione esplicita della correlazione Request/Reply  
 Se altre operazioni bidirezionali vengono eseguite in parallelo, è necessario configurare la correlazione in modo esplicito. Questa operazione può essere <xref:System.ServiceModel.Activities.CorrelationHandle> eseguita specificando a <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>e , o inserendo l'interno <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> di un <xref:System.ServiceModel.Activities.CorrelationScope>oggetto . In questo esempio, la correlazione <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> richiesta-risposta è configurata su una coppia.  
  
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
  
 Anziché configurare la correlazione in modo esplicito, è possibile usare un'attività <xref:System.ServiceModel.Activities.CorrelationScope>. <xref:System.ServiceModel.Activities.CorrelationScope> fornisce un oggetto <xref:System.ServiceModel.Activities.CorrelationHandle> implicito per le attività della messaggistica in esso contenute. In questo esempio, una <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia <xref:System.ServiceModel.Activities.CorrelationScope>è contenuta all'interno di un oggetto . Non è richiesta alcuna configurazione di correlazione esplicita.  
  
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
  
 Se sono necessarie ulteriori correlazioni, è possibile configurarle usando la proprietà <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> delle rispettive attività di messaggistica mediante i tipi `CorrelationInitializer` desiderati.  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a>Utilizzo della correlazione in un'operazione bidirezionale con Send/ReceiveReply  
 Mentre <xref:System.ServiceModel.Activities.Receive> l'attività può essere utilizzata solo <xref:System.ServiceModel.Activities.WorkflowServiceHost>in <xref:System.ServiceModel.Activities.Send> un <xref:System.ServiceModel.Activities.Send> / servizio flusso di lavoro ospitato da , mentre la <xref:System.ServiceModel.Activities.ReceiveReply> coppia può essere utilizzata in qualsiasi flusso di lavoro che deve richiamare un metodo su un servizio Web. Se il flusso di lavoro è ospitato usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>, viene applicata la correlazione predefinita descritta nella sezione precedente. In caso contrario, è necessario configurare la correlazione in modo esplicito mediante gli elementi <xref:System.ServiceModel.Activities.CorrelationInitializer> e <xref:System.ServiceModel.Activities.CorrelationHandle>oppure tramite la gestione esplicita dell'handle dell'elemento <xref:System.ServiceModel.Activities.CorrelationScope>.  
  
 Quando si usa **Aggiungi riferimento al servizio** in un servizio <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> con operazioni bidirezionali, vengono generate attività che eseguono il wrapping di un'attività di coppia internamente con la correlazione Richiesta/Risposta specificata in modo esplicito.
