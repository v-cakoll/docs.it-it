---
title: Correlazione di scambio del contesto
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bf84dfce2b2164d78bf07f840d66d6089a16ff23
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="context-exchange-correlation"></a>Correlazione di scambio del contesto
La correlazione del contesto dipende dal meccanismo di scambio di contesto descritto nel [specifica del protocollo .NET contesto Exchange](http://go.microsoft.com/fwlink/?LinkId=166059). La correlazione del contesto utilizza un'intestazione del contesto nota o un cookie per correlare messaggi all'istanza corretta. Per utilizzare la correlazione del contesto, è necessario utilizzare un'associazione basata sul contesto, ad esempio <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> o <xref:System.ServiceModel.NetTcpContextBinding>, sull'endpoint fornito a <xref:System.ServiceModel.Activities.WorkflowServiceHost>. In questo argomento viene illustrato come utilizzare la correlazione del contesto con attività di messaggistica in un servizio flusso di lavoro.  
  
## <a name="using-context-correlation"></a>Utilizzo della correlazione del contesto  
 La correlazione del contesto viene utilizzata se un client deve effettuare chiamate ripetute in un servizio flusso di lavoro e quest'ultimo viene ospitato mediante una delle associazioni del contesto. Questo tipo di correlazione viene inizializzato da un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia del servizio del flusso di lavoro. Il contesto viene nuovamente inviato al client con la risposta e quindi il client associa questo contesto a chiamate successive al servizio.  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a>Configurazione della correlazione del contesto in un servizio flusso di lavoro  
 La correlazione del contesto viene inizializzata utilizzando un oggetto <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> associato all'attività <xref:System.ServiceModel.Activities.SendReply> che risponde al messaggio in arrivo iniziale. Nell'esempio seguente <xref:System.ServiceModel.Activities.SendReply> viene configurato per inizializzare una correlazione di contesto.  
  
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
>  Nell'esempio vengono utilizzati in realtà due tipi di correlazione: correlazione di contesto e correlazione request/reply. La correlazione di contesto viene utilizzata in modo che le chiamate provenienti dai client vengano indirizzate all'istanza corretta. La correlazione request/reply viene utilizzata dall'oggetto <xref:System.ServiceModel.Activities.Receive> e dalle attività <xref:System.ServiceModel.Activities.SendReply> per implementare l'operazione bidirezionale modellata da tali attività. In questo esempio, solo la correlazione del contesto è configurata in modo esplicito e <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia utilizza la correlazione request / reply predefinita fornita dall'operatore implicito <xref:System.ServiceModel.Activities.CorrelationHandle> gestione di <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Quando si utilizza il **ReceiveAndSendReply** modello di attività nella correlazione request / reply della finestra di progettazione, flusso di lavoro è configurato in modo esplicito. Per ulteriori informazioni sulla correlazione request/reply e gestione dell'handle di correlazione implicita, vedere [Request/Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) e [Cenni preliminari sulla correlazione](../../../../docs/framework/wcf/feature-details/correlation-overview.md). Per ulteriori informazioni sul **ReceiveAndSendReply** modello di attività, vedere [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).  
  
 Le attività <xref:System.ServiceModel.Activities.Receive> successive nel servizio flusso di lavoro possono fare riferimento all'elemento <xref:System.ServiceModel.Activities.CorrelationHandle> inizializzato da <xref:System.ServiceModel.Activities.SendReply> nell'esempio precedente.  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 L'endpoint viene quindi configurato sull'elemento <xref:System.ServiceModel.Activities.WorkflowServiceHost> per utilizzare un'associazione basata sul contesto, ad esempio <xref:System.ServiceModel.BasicHttpContextBinding>.  
  
```xml  
<endpoint  
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a>Configurazione della correlazione del contesto in un client flusso di lavoro  
 Se il client è un altro flusso di lavoro, è necessario configurare la correlazione del contesto anche sul client. Nel flusso di lavoro client, il <xref:System.ServiceModel.Activities.ReceiveReply> del <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> coppia che effettua la chiamata iniziale al servizio del flusso di lavoro deve essere configurato con un <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.  
  
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
  
 Dopo aver inizializzato la correlazione, le attività <xref:System.ServiceModel.Activities.Send> successive possono utilizzare l'oggetto <xref:System.ServiceModel.Activities.CorrelationHandle> per richiamare metodi sulla stessa istanza del servizio.  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 In questi esempi è stata configurata la correlazione del contesto in modo esplicito. Se il flusso di lavoro client non è anche ospitato in un <xref:System.ServiceModel.Activities.WorkflowServiceHost>, la correlazione deve essere configurata in modo esplicito, a meno che le attività siano contenute all'interno di un'attività <xref:System.ServiceModel.Activities.CorrelationScope>. Per ulteriori informazioni sulla correlazione del contesto, vedere la [NetContextExchangeCorrelation](http://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) esempio.  
  
 Se il client che effettua chiamate al servizio flusso di lavoro non è un flusso di lavoro, può comunque effettuare chiamate ripetute a condizione che passi di nuovo in modo esplicito il contesto restituito dalla prima chiamata al servizio flusso di lavoro. I proxy generati aggiungendo un riferimento al servizio in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] archiviano e passano questo contesto per impostazione predefinita.
