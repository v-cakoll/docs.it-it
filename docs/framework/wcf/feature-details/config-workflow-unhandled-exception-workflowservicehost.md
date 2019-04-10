---
title: 'Procedura: Configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: cd3729019b5371b5313bba3814758c723c0d448a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318747"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="26913-102">Procedura: Configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="26913-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="26913-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> è un comportamento che consente di specificare l'azione da eseguire se si verifica un'eccezione non gestita all'interno di un flusso di lavoro ospitato in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="26913-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="26913-104">In questo argomento viene illustrato come configurare il comportamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="26913-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="26913-105">Per configurare WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="26913-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1. <span data-ttu-id="26913-106">Aggiungere un <`workflowUnhandledException`> elemento in un <`behavior`> elemento all'interno di un <`serviceBehaviors`> elemento, usando il `action` attributo per specificare l'azione da intraprendere quando si verifica un'eccezione non gestita come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="26913-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
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
    >  <span data-ttu-id="26913-107">L'esempio di configurazione precedente usa la configurazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="26913-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="26913-108">Per altre informazioni, vedere [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="26913-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="26913-109">È possibile configurare questo comportamento nel codice, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="26913-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="26913-110">Il `action` attributo del <`workflowUnhandledException`> elemento può essere impostato su uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="26913-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     **<span data-ttu-id="26913-111">abandon</span><span class="sxs-lookup"><span data-stu-id="26913-111">abandon</span></span>**  
     <span data-ttu-id="26913-112">Interrompe l'istanza in memoria senza modificare lo stato dell'istanza persistente (ovvero, senza eseguire il rollback all'ultimo punto persistente).</span><span class="sxs-lookup"><span data-stu-id="26913-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     **<span data-ttu-id="26913-113">abandonAndSuspend</span><span class="sxs-lookup"><span data-stu-id="26913-113">abandonAndSuspend</span></span>**  
     <span data-ttu-id="26913-114">Interrompe l'istanza in memoria e aggiorna l'istanza persistente da sospendere.</span><span class="sxs-lookup"><span data-stu-id="26913-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     **<span data-ttu-id="26913-115">cancel</span><span class="sxs-lookup"><span data-stu-id="26913-115">cancel</span></span>**  
     <span data-ttu-id="26913-116">Chiama i gestori annullamento per l'istanza, quindi completa l'istanza in memoria, che può rimuoverlo anche dall'archivio di istanze</span><span class="sxs-lookup"><span data-stu-id="26913-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     **<span data-ttu-id="26913-117">terminate</span><span class="sxs-lookup"><span data-stu-id="26913-117">terminate</span></span>**  
     <span data-ttu-id="26913-118">Completa l'istanza in memoria e la rimuove dall'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="26913-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="26913-119">Per altre informazioni sulle <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, vedere [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="26913-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26913-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26913-120">See also</span></span>

- [<span data-ttu-id="26913-121">Estensibilità host del servizio flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="26913-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="26913-122">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="26913-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
