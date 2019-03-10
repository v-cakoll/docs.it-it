---
title: Libreria di attività
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: b701d382c25644181b23f3c0f0cd8e019b8d37d1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709836"
---
# <a name="activity-library"></a><span data-ttu-id="38f0b-102">Libreria di attività</span><span class="sxs-lookup"><span data-stu-id="38f0b-102">Activity Library</span></span>
<span data-ttu-id="38f0b-103">In questa sezione è inclusi esempi che illustrano attività personalizzate avanzate in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="38f0b-103">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38f0b-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="38f0b-104">In This Section</span></span>

 [<span data-ttu-id="38f0b-105">Attività personalizzata SendMail</span><span class="sxs-lookup"><span data-stu-id="38f0b-105">SendMail Custom Activity</span></span>](sendmail-custom-activity.md)  
 <span data-ttu-id="38f0b-106">Viene illustrato come creare un'attività personalizzata che deriva da <xref:System.Activities.AsyncCodeActivity> per inviare messaggi di posta elettronica tramite il protocollo SMTP da usare in un'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="38f0b-106">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="38f0b-107">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="38f0b-107">Throttled Parallel ForEach</span></span>](throttled-parallel-foreach.md)  
 <span data-ttu-id="38f0b-108">Viene illustrato che l'attività `ThrottleParallelForEach` è simile all'attività <xref:System.Activities.Statements.ParallelForEach%601> con l'unica eccezione che consente l'impostazione di un fattore di concorrenza per limitare il numero di rami simultanei da eseguire.</span><span class="sxs-lookup"><span data-stu-id="38f0b-108">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="38f0b-109">Attività di accesso al database</span><span class="sxs-lookup"><span data-stu-id="38f0b-109">Database Access Activities</span></span>](database-access-activities.md)  
 <span data-ttu-id="38f0b-110">Viene illustrato come creare attività che consentono l'accesso ai database per recuperare o modificare informazioni e utilizzare [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) per accedere al database.</span><span class="sxs-lookup"><span data-stu-id="38f0b-110">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
 [<span data-ttu-id="38f0b-111">Attività ExternalizedPolicy in .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="38f0b-111">Externalized Policy Activity in .NET Framework 4.5</span></span>](externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="38f0b-112">Viene illustrato come l'attività ExternalizedPolicy4 consenta l'esecuzione esistenti di Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> gli oggetti in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) direttamente tramite il motore regole vale a dire disponibile in WF 3.5.</span><span class="sxs-lookup"><span data-stu-id="38f0b-112">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span> 
  
 [<span data-ttu-id="38f0b-113">Attività ForEach non generica</span><span class="sxs-lookup"><span data-stu-id="38f0b-113">Non-Generic ForEach</span></span>](non-generic-foreach.md)  
 <span data-ttu-id="38f0b-114">Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="38f0b-114">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="38f0b-115">Attività ParallelForEach non generica</span><span class="sxs-lookup"><span data-stu-id="38f0b-115">Non-Generic ParallelForEach</span></span>](non-generic-parallelforeach.md)  
 <span data-ttu-id="38f0b-116">Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="38f0b-116">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="38f0b-117">Ottenere WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="38f0b-117">Get WorkflowInstanceId</span></span>](get-workflowinstanceid.md)  
 <span data-ttu-id="38f0b-118">Viene illustrato come usare l'attività personalizzata, `GetWorkflowInstanceId`, per restituire l'ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="38f0b-118">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
