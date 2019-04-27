---
title: 'Procedura: Configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: cd3729019b5371b5313bba3814758c723c0d448a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857558"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Procedura: Configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> è un comportamento che consente di specificare l'azione da eseguire se si verifica un'eccezione non gestita all'interno di un flusso di lavoro ospitato in <xref:System.ServiceModel.Activities.WorkflowServiceHost>. In questo argomento viene illustrato come configurare il comportamento in un file di configurazione.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>Per configurare WorkflowUnhandledExceptionBehavior  
  
1. Aggiungere un <`workflowUnhandledException`> elemento in un <`behavior`> elemento all'interno di un <`serviceBehaviors`> elemento, usando il `action` attributo per specificare l'azione da intraprendere quando si verifica un'eccezione non gestita come illustrato nell'esempio seguente.  
  
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
    >  L'esempio di configurazione precedente usa la configurazione semplificata. Per altre informazioni, vedere [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     È possibile configurare questo comportamento nel codice, come indicato nell'esempio seguente.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     Il `action` attributo del <`workflowUnhandledException`> elemento può essere impostato su uno dei valori seguenti:  
  
     **abandon**  
     Interrompe l'istanza in memoria senza modificare lo stato dell'istanza persistente (ovvero, senza eseguire il rollback all'ultimo punto persistente).  
  
     **abandonAndSuspend**  
     Interrompe l'istanza in memoria e aggiorna l'istanza persistente da sospendere.  
  
     **cancel**  
     Chiama i gestori annullamento per l'istanza, quindi completa l'istanza in memoria, che può rimuoverlo anche dall'archivio di istanze  
  
     **terminate**  
     Completa l'istanza in memoria e la rimuove dall'archivio di istanze.  
  
     Per altre informazioni sulle <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, vedere [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>Vedere anche

- [Estendibilità dell'host dei servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
