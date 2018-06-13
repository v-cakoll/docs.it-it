---
title: 'Procedura: configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: e09575a7998f676ea188a0500f31012c25c19738
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489193"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="ed9a4-102">Procedura: configurare il comportamento di eccezione non gestita del flusso di lavoro con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="ed9a4-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="ed9a4-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> è un comportamento che consente di specificare l'azione da eseguire se si verifica un'eccezione non gestita all'interno di un flusso di lavoro ospitato in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="ed9a4-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="ed9a4-104">In questo argomento viene illustrato come configurare il comportamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ed9a4-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="ed9a4-105">Per configurare WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="ed9a4-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1.  <span data-ttu-id="ed9a4-106">Aggiungere un <`workflowUnhandledException`> elemento in una <`behavior`> elemento all'interno di un <`serviceBehaviors`> elemento, utilizzando il `action` attributo per specificare l'azione da intraprendere quando si verifica un'eccezione non gestita come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ed9a4-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
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
    >  <span data-ttu-id="ed9a4-107">L'esempio di configurazione precedente usa la configurazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="ed9a4-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="ed9a4-108">Per altre informazioni, vedere [configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="ed9a4-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="ed9a4-109">È possibile configurare questo comportamento nel codice, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ed9a4-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="ed9a4-110">Il `action` attributo di <`workflowUnhandledException`> elemento può essere impostato su uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed9a4-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="ed9a4-111">**Abbandono**</span><span class="sxs-lookup"><span data-stu-id="ed9a4-111">**abandon**</span></span>  
     <span data-ttu-id="ed9a4-112">Interrompe l'istanza in memoria senza modificare lo stato dell'istanza persistente (ovvero, senza eseguire il rollback all'ultimo punto persistente).</span><span class="sxs-lookup"><span data-stu-id="ed9a4-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="ed9a4-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="ed9a4-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="ed9a4-114">Interrompe l'istanza in memoria e aggiorna l'istanza persistente da sospendere.</span><span class="sxs-lookup"><span data-stu-id="ed9a4-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="ed9a4-115">**cancel**</span><span class="sxs-lookup"><span data-stu-id="ed9a4-115">**cancel**</span></span>  
     <span data-ttu-id="ed9a4-116">Chiama i gestori annullamento per l'istanza, quindi completa l'istanza in memoria, che può rimuoverlo anche dall'archivio di istanze</span><span class="sxs-lookup"><span data-stu-id="ed9a4-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="ed9a4-117">**terminate**</span><span class="sxs-lookup"><span data-stu-id="ed9a4-117">**terminate**</span></span>  
     <span data-ttu-id="ed9a4-118">Completa l'istanza in memoria e la rimuove dall'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="ed9a4-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="ed9a4-119">Per ulteriori informazioni <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, vedere [estensibilità Host del servizio del flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="ed9a4-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed9a4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed9a4-120">See Also</span></span>  
 [<span data-ttu-id="ed9a4-121">Estendibilità dell'host dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ed9a4-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [<span data-ttu-id="ed9a4-122">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ed9a4-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
