---
title: 'Procedura: configurare il comportamento inattivo con WorkflowServiceHost'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04ab5e657ffae42e9e52a7f392070a7d6ecf680c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a><span data-ttu-id="0f2be-102">Procedura: configurare il comportamento inattivo con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="0f2be-102">How to: Configure Idle Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="0f2be-103">I flussi di lavoro diventano inattivi se incontrano un segnalibro che deve essere ripreso da uno stimolo esterno, ad esempio nel caso in cui l'istanza del flusso di lavoro sia in attesa di un messaggio da recapitare usando un'attività <xref:System.ServiceModel.Activities.Receive> .</span><span class="sxs-lookup"><span data-stu-id="0f2be-103">Workflows go idle when they encounter a bookmark that must be resumed by some external stimulus, for example when the workflow instance is waiting for a message to be delivered using a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="0f2be-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> è un comportamento che consente di specificare l'orario compreso tra il momento in cui un'istanza del servizio diventa inattiva e il momento in cui viene resa persistente o scaricata.</span><span class="sxs-lookup"><span data-stu-id="0f2be-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> is a behavior that allows you to specify the time between when a service instance goes idle and when the instance is persisted or unloaded.</span></span> <span data-ttu-id="0f2be-105">Contiene due proprietà che consentono di impostare questi intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="0f2be-105">It contains two properties that enable you to set these time spans.</span></span> <span data-ttu-id="0f2be-106">La proprietà<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> specifica l'intervallo di tempo compreso tra il momento in cui un'istanza di servizio del flusso di lavoro diventa inattiva e il momento in cui l'istanza di servizio del flusso di lavoro viene resa persistente.</span><span class="sxs-lookup"><span data-stu-id="0f2be-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="0f2be-107">La proprietà<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> specifica l'intervallo di tempo compreso tra il momento in cui un'istanza di servizio del flusso di lavoro diventa inattiva e il momento in cui l'istanza di servizio del flusso di lavoro viene scaricata, ovvero resa persistente nell'archivio di istanze e rimossa dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="0f2be-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is unloaded, where unload means persisting the instance to the instance store and removing it from memory.</span></span> <span data-ttu-id="0f2be-108">In questo argomento viene illustrato come configurare <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0f2be-108">This topic explains how to configure the <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in a configuration file.</span></span>  
  
### <a name="to-configure-workflowidlebehavior"></a><span data-ttu-id="0f2be-109">Per configurare WorkflowIdleBehavior</span><span class="sxs-lookup"><span data-stu-id="0f2be-109">To configure WorkflowIdleBehavior</span></span>  
  
1.  <span data-ttu-id="0f2be-110">Aggiungere un <`workflowIdle`> elemento per il <`behavior`> elemento all'interno di <`serviceBehaviors`> come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0f2be-110">Add a <`workflowIdle`> element to the <`behavior`> element within the <`serviceBehaviors`> element as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="0f2be-111">L'attributo `timeToUnload` specifica il periodo di tempo compreso tra il momento in cui un'istanza di servizio del flusso di lavoro diviene inattiva e il momento in cui il servizio flusso di lavoro viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="0f2be-111">The `timeToUnload` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service is unloaded.</span></span> <span data-ttu-id="0f2be-112">L'attributo `timeToPersist` specifica il periodo di tempo compreso tra il momento in cui un'istanza del servizio flusso di lavoro diviene inattiva e il momento in cui l'istanza del servizio flusso di lavoro è persistente.</span><span class="sxs-lookup"><span data-stu-id="0f2be-112">The `timeToPersist` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="0f2be-113">Il valore predefinito per `timeToUnload` è 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="0f2be-113">The default value for `timeToUnload` is 1 minute.</span></span> <span data-ttu-id="0f2be-114">Il valore predefinito per la proprietà `timeToPersist` è <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="0f2be-114">The default value for `timeToPersist` is <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="0f2be-115">Se si desidera mantenere le istanze inattive in memoria ma renderle persistenti per motivi di affidabilità, impostare i valori in modo tale che `timeToPersist` < `timeToUnload`.</span><span class="sxs-lookup"><span data-stu-id="0f2be-115">If you want to keep idle instances in memory but persist them for robustness, set values so that `timeToPersist` < `timeToUnload`.</span></span> <span data-ttu-id="0f2be-116">Se si desidera impedire lo scaricamento delle istanze inattive, impostare `timeToUnload` su <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="0f2be-116">If you want to prevent idle instances from being unloaded, set `timeToUnload` to <xref:System.TimeSpan.MaxValue>.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0f2be-117"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, vedere [estensibilità Host del servizio del flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="0f2be-117"> <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f2be-118">L'esempio di configurazione precedente usa la configurazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="0f2be-118">The preceding configuration sample is using simplified configuration.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="0f2be-119">[Semplificata la configurazione](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="0f2be-119"> [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
### <a name="to-change-idle-behavior-in-code"></a><span data-ttu-id="0f2be-120">Per modificare il comportamento inattivo nel codice</span><span class="sxs-lookup"><span data-stu-id="0f2be-120">To change idle behavior in code</span></span>  
  
-   <span data-ttu-id="0f2be-121">Nell'esempio seguente viene modificato il tempo di attesa prima della persistenza e dello scaricamento a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="0f2be-121">The following example changes the time to wait before persisting and unloading programmatically.</span></span>  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0f2be-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f2be-122">See Also</span></span>  
 [<span data-ttu-id="0f2be-123">Estensibilità Host del servizio del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0f2be-123">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [<span data-ttu-id="0f2be-124">Configurazione semplificata</span><span class="sxs-lookup"><span data-stu-id="0f2be-124">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="0f2be-125">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0f2be-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
