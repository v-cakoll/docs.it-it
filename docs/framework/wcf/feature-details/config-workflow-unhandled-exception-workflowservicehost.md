---
title: 'Procedura: configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 69c6b1ce11d735181390a0c67df2f8dbea4f906c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185316"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Procedura: configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> è un comportamento che consente di specificare l'azione da eseguire se si verifica un'eccezione non gestita all'interno di un flusso di lavoro ospitato in <xref:System.ServiceModel.Activities.WorkflowServiceHost>. In questo argomento viene illustrato come configurare il comportamento in un file di configurazione.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>Per configurare WorkflowUnhandledExceptionBehavior  
  
1. Aggiungere un `workflowUnhandledException` elemento <`behavior`> in un `serviceBehaviors` elemento> `action` <all'interno di un elemento> <, utilizzando l'attributo per specificare l'azione da eseguire quando si verifica un'eccezione non gestita, come illustrato nell'esempio seguente.  
  
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
    > L'esempio di configurazione precedente usa la configurazione semplificata. Per ulteriori informazioni, vedere [Configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     È possibile configurare questo comportamento nel codice, come indicato nell'esempio seguente.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     L'attributo `action` `workflowUnhandledException` dell'elemento> <può essere impostato su uno dei seguenti valori:  
  
     **Abbandonare**  
     Interrompe l'istanza in memoria senza modificare lo stato dell'istanza persistente (ovvero, senza eseguire il rollback all'ultimo punto persistente).  
  
     **abandonAndSuspend**  
     Interrompe l'istanza in memoria e aggiorna l'istanza persistente da sospendere.  
  
     **Annulla**  
     Chiama i gestori annullamento per l'istanza, quindi completa l'istanza in memoria, che può rimuoverlo anche dall'archivio di istanze  
  
     **termine**  
     Completa l'istanza in memoria e la rimuove dall'archivio di istanze.  
  
     Per ulteriori <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>informazioni su , vedere [Estensibilità host del servizio flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>Vedere anche

- [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
