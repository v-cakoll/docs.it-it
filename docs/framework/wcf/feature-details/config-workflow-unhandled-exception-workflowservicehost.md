---
title: 'Procedura: Configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 8f7fe203a4198aa98e8aee1be3a12e4d72a066f8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175409"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="c00e7-102">Procedura: Configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="c00e7-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="c00e7-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> è un comportamento che consente di specificare l'azione da eseguire se si verifica un'eccezione non gestita all'interno di un flusso di lavoro ospitato in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c00e7-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="c00e7-104">In questo argomento viene illustrato come configurare il comportamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c00e7-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="c00e7-105">Per configurare WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="c00e7-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1.  <span data-ttu-id="c00e7-106">Aggiungere un <`workflowUnhandledException`> elemento in un <`behavior`> elemento all'interno di un <`serviceBehaviors`> elemento, usando il `action` attributo per specificare l'azione da intraprendere quando si verifica un'eccezione non gestita come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c00e7-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
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
    >  <span data-ttu-id="c00e7-107">L'esempio di configurazione precedente usa la configurazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="c00e7-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="c00e7-108">Per altre informazioni, vedere [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="c00e7-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="c00e7-109">È possibile configurare questo comportamento nel codice, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c00e7-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="c00e7-110">Il `action` attributo del <`workflowUnhandledException`> elemento può essere impostato su uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c00e7-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     **<span data-ttu-id="c00e7-111">abandon</span><span class="sxs-lookup"><span data-stu-id="c00e7-111">abandon</span></span>**  
     <span data-ttu-id="c00e7-112">Interrompe l'istanza in memoria senza modificare lo stato dell'istanza persistente (ovvero, senza eseguire il rollback all'ultimo punto persistente).</span><span class="sxs-lookup"><span data-stu-id="c00e7-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     **<span data-ttu-id="c00e7-113">abandonAndSuspend</span><span class="sxs-lookup"><span data-stu-id="c00e7-113">abandonAndSuspend</span></span>**  
     <span data-ttu-id="c00e7-114">Interrompe l'istanza in memoria e aggiorna l'istanza persistente da sospendere.</span><span class="sxs-lookup"><span data-stu-id="c00e7-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     **<span data-ttu-id="c00e7-115">cancel</span><span class="sxs-lookup"><span data-stu-id="c00e7-115">cancel</span></span>**  
     <span data-ttu-id="c00e7-116">Chiama i gestori annullamento per l'istanza, quindi completa l'istanza in memoria, che può rimuoverlo anche dall'archivio di istanze</span><span class="sxs-lookup"><span data-stu-id="c00e7-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     **<span data-ttu-id="c00e7-117">terminate</span><span class="sxs-lookup"><span data-stu-id="c00e7-117">terminate</span></span>**  
     <span data-ttu-id="c00e7-118">Completa l'istanza in memoria e la rimuove dall'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="c00e7-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="c00e7-119">Per altre informazioni sulle <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, vedere [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="c00e7-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00e7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c00e7-120">See also</span></span>

- [<span data-ttu-id="c00e7-121">Estensibilità host del servizio flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c00e7-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="c00e7-122">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c00e7-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
