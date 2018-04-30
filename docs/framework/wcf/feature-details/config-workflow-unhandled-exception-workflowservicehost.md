---
title: 'Procedura: configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a49b3d42e51ed7a0a57deb392f5728f407909b00
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Procedura: configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> è un comportamento che consente di specificare l'azione da eseguire se si verifica un'eccezione non gestita all'interno di un flusso di lavoro ospitato in <xref:System.ServiceModel.Activities.WorkflowServiceHost>. In questo argomento viene illustrato come configurare il comportamento in un file di configurazione.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>Per configurare WorkflowUnhandledExceptionBehavior  
  
1.  Aggiungere un <`workflowUnhandledException`> elemento in una <`behavior`> elemento all'interno di un <`serviceBehaviors`> elemento, utilizzando il `action` attributo per specificare l'azione da intraprendere quando si verifica un'eccezione non gestita come illustrato nell'esempio seguente.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  L'esempio di configurazione precedente usa la configurazione semplificata. Per altre informazioni, vedere [configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     È possibile configurare questo comportamento nel codice, come indicato nell'esempio seguente.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     Il `action` attributo di <`workflowUnhandledException`> elemento può essere impostato su uno dei valori seguenti:  
  
     **Abbandono**  
     Interrompe l'istanza in memoria senza modificare lo stato dell'istanza persistente (ovvero, senza eseguire il rollback all'ultimo punto persistente).  
  
     **abandonAndSuspend**  
     Interrompe l'istanza in memoria e aggiorna l'istanza persistente da sospendere.  
  
     **cancel**  
     Chiama i gestori annullamento per l'istanza, quindi completa l'istanza in memoria, che può rimuoverlo anche dall'archivio di istanze  
  
     **terminate**  
     Completa l'istanza in memoria e la rimuove dall'archivio di istanze.  
  
     Per ulteriori informazioni <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, vedere [estensibilità Host del servizio del flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Estendibilità dell'host dei servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
