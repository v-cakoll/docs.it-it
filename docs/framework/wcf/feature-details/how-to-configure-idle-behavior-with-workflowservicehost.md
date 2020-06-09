---
title: 'Procedura: configurare il comportamento inattivo con WorkflowServiceHost'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
ms.openlocfilehash: 8b9fa36408d5f2bc5445ebeccba61f71417935e7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599126"
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a>Procedura: configurare il comportamento inattivo con WorkflowServiceHost
I flussi di lavoro diventano inattivi se incontrano un segnalibro che deve essere ripreso da uno stimolo esterno, ad esempio nel caso in cui l'istanza del flusso di lavoro sia in attesa di un messaggio da recapitare usando un'attività <xref:System.ServiceModel.Activities.Receive> . <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> è un comportamento che consente di specificare l'orario compreso tra il momento in cui un'istanza del servizio diventa inattiva e il momento in cui viene resa persistente o scaricata. Contiene due proprietà che consentono di impostare questi intervalli di tempo. La proprietà<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> specifica l'intervallo di tempo compreso tra il momento in cui un'istanza di servizio del flusso di lavoro diventa inattiva e il momento in cui l'istanza di servizio del flusso di lavoro viene resa persistente. La proprietà<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> specifica l'intervallo di tempo compreso tra il momento in cui un'istanza di servizio del flusso di lavoro diventa inattiva e il momento in cui l'istanza di servizio del flusso di lavoro viene scaricata, ovvero resa persistente nell'archivio di istanze e rimossa dalla memoria. In questo argomento viene illustrato come configurare <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in un file di configurazione.  
  
### <a name="to-configure-workflowidlebehavior"></a>Per configurare WorkflowIdleBehavior  
  
1. Aggiungere un `workflowIdle` elemento <> all'elemento <`behavior`> nell' `serviceBehaviors` elemento <> come illustrato nell'esempio seguente.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     L'attributo `timeToUnload` specifica il periodo di tempo compreso tra il momento in cui un'istanza di servizio del flusso di lavoro diviene inattiva e il momento in cui il servizio flusso di lavoro viene scaricato. L'attributo `timeToPersist` specifica il periodo di tempo compreso tra il momento in cui un'istanza del servizio flusso di lavoro diviene inattiva e il momento in cui l'istanza del servizio flusso di lavoro è persistente. Il valore predefinito per `timeToUnload` è 1 minuto. Il valore predefinito per la proprietà `timeToPersist` è <xref:System.TimeSpan.MaxValue>. Se si desidera mantenere le istanze inattive in memoria ma renderle persistenti per motivi di affidabilità, impostare i valori in modo tale che `timeToPersist` < `timeToUnload`. Se si desidera impedire lo scaricamento delle istanze inattive, impostare `timeToUnload` su <xref:System.TimeSpan.MaxValue>. Per ulteriori informazioni su <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> , vedere [Estensibilità host del servizio flusso di lavoro](workflow-service-host-extensibility.md)  
  
    > [!NOTE]
    > L'esempio di configurazione precedente usa la configurazione semplificata. Per altre informazioni, vedere [Configurazione semplificata](../simplified-configuration.md).  
  
### <a name="to-change-idle-behavior-in-code"></a>Per modificare il comportamento inattivo nel codice  
  
- Nell'esempio seguente viene modificato il tempo di attesa prima della persistenza e dello scaricamento a livello di codice.  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Workflow Service Host Extensibility](workflow-service-host-extensibility.md)
- [Configurazione semplificata](../simplified-configuration.md)
- [Servizi flusso di lavoro](workflow-services.md)
