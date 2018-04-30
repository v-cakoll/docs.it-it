---
title: 'Procedura: configurare il rilevamento con WorkflowServiceHost'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e1de3349bb9766beeee95b9934fc1ca11fc7006f
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a><span data-ttu-id="14fdc-102">Procedura: configurare il rilevamento con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="14fdc-102">How to: Configure Tracking with WorkflowServiceHost</span></span>
<span data-ttu-id="14fdc-103">In questo argomento viene illustrato come configurare il rilevamento di un flusso di lavoro [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] ospitato in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="14fdc-103">This topic explains how to configure tracking for a [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="14fdc-104">Viene configurato tramite un file Web.config specificando un comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="14fdc-104">It is configured through a Web.config file by specifying a service behavior.</span></span>  
  
### <a name="configure-tracking-in-configuration"></a><span data-ttu-id="14fdc-105">Configurare il rilevamento nella configurazione</span><span class="sxs-lookup"><span data-stu-id="14fdc-105">Configure Tracking in Configuration</span></span>  
  
1.  <span data-ttu-id="14fdc-106">Aggiungere <xref:System.Activities.Tracking.EtwTrackingParticipant> usando l'elemento <`behavior`> in un file di configurazione, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="14fdc-106">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="14fdc-107">L'esempio di configurazione precedente usa la configurazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="14fdc-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="14fdc-108">Per altre informazioni, vedere [configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="14fdc-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="14fdc-109">L'esempio di configurazione precedente aggiunge un elemento <xref:System.Activities.Tracking.EtwTrackingParticipant> e specifica un nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="14fdc-109">The preceding configuration sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="14fdc-110">I profili di rilevamento vengono creati in un elemento <`trackingProfile`> all'interno di un elemento <`tracking`>.</span><span class="sxs-lookup"><span data-stu-id="14fdc-110">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element.</span></span> <span data-ttu-id="14fdc-111">Il profilo di rilevamento contiene query di rilevamento che consentono a un partecipante del rilevamento di eseguire la sottoscrizione agli eventi del flusso di lavoro generati quando lo stato di un'istanza del flusso di lavoro viene modificato al runtime.</span><span class="sxs-lookup"><span data-stu-id="14fdc-111">The tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="14fdc-112">Nell'esempio seguente viene illustrato come creare un profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="14fdc-112">The following example shows how to create a tracking profile.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <tracking>   
         <trackingProfile name="Sample Tracking Profile">  
            <workflow activityDefinitionId="*">  
               <workflowInstanceQueries>  
                 <workflowInstanceQuery>  
                    <states>  
                       <state name="Started"/>  
                       <state name="Completed"/>  
                    </states>  
                </workflowInstanceQuery>  
             </workflowInstanceQueries>  
           </workflow>  
         </trackingProfile>   
       </tracking>  
    </system.serviceModel>  
    ```  
  
     <span data-ttu-id="14fdc-113">Per ulteriori informazioni sui profili di rilevamento, vedere [profili di rilevamento](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="14fdc-113">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="14fdc-114">Per ulteriori informazioni sul rilevamento in generale, vedere [flusso di lavoro rilevamento e traccia](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="14fdc-114">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
### <a name="configure-tracking-in-code"></a><span data-ttu-id="14fdc-115">Configurare il rilevamento nel codice</span><span class="sxs-lookup"><span data-stu-id="14fdc-115">Configure Tracking in Code</span></span>  
  
1.  <span data-ttu-id="14fdc-116">Aggiungere l'elemento <xref:System.Activities.Tracking.EtwTrackingParticipant> usando il comportamento <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> nel codice, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="14fdc-116">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> behavior in code, as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     <span data-ttu-id="14fdc-117">L'esempio di codice precedente aggiunge un elemento <xref:System.Activities.Tracking.EtwTrackingParticipant> e specifica un nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="14fdc-117">The preceding code sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="14fdc-118">I profili di rilevamento vengono creati in un elemento <`trackingProfile`> all'interno di un elemento <`tracking`> come illustrato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="14fdc-118">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element as shown in the previous section.</span></span>  
  
     <span data-ttu-id="14fdc-119">Per ulteriori informazioni sui profili di rilevamento, vedere [profili di rilevamento](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="14fdc-119">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="14fdc-120">Per ulteriori informazioni sul rilevamento in generale, vedere [flusso di lavoro rilevamento e traccia](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="14fdc-120">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="14fdc-121">Per un esempio di configurazione del rilevamento a livello di codice vedere [configurazione del rilevamento per un flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="14fdc-121">For an example of configuring tracking programmatically see [Configuring Tracking for a Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14fdc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14fdc-122">See Also</span></span>  
 [<span data-ttu-id="14fdc-123">Configurazione semplificata per servizi WCF</span><span class="sxs-lookup"><span data-stu-id="14fdc-123">Simplified Configuration for WCF Services</span></span>](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)  
 [<span data-ttu-id="14fdc-124">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="14fdc-124">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="14fdc-125">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="14fdc-125">Tracking Profiles</span></span>](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
