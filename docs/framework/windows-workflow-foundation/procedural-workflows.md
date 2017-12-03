---
title: Flussi di lavoro procedurali
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd879d138a95c003ca0ffb12b3ce010534c3e158
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="procedural-workflows"></a><span data-ttu-id="5c3d0-102">Flussi di lavoro procedurali</span><span class="sxs-lookup"><span data-stu-id="5c3d0-102">Procedural Workflows</span></span>
<span data-ttu-id="5c3d0-103">Nei flussi di lavoro procedurali vengono usati metodi di controllo del flusso simili a quelli dei linguaggi procedurali.</span><span class="sxs-lookup"><span data-stu-id="5c3d0-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="5c3d0-104">Tra questi costrutti sono inclusi `While` e `If`.</span><span class="sxs-lookup"><span data-stu-id="5c3d0-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="5c3d0-105">Questi flussi di lavoro possono essere creati liberamente usando altre attività di controllo del flusso quale <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="5c3d0-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="5c3d0-106">Controllo del flusso di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5c3d0-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="5c3d0-107">La libreria di attività del flusso di lavoro dispone di attività per modellare la maggior parte dei metodi di controllo del flusso usati nei linguaggi procedurali,</span><span class="sxs-lookup"><span data-stu-id="5c3d0-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="5c3d0-108">tra cui:</span><span class="sxs-lookup"><span data-stu-id="5c3d0-108">These include:</span></span>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="5c3d0-109">Per utilizzare le attività di controllo di flusso, trascinamento della selezione dal **attività** casella degli strumenti in un'attività composta nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="5c3d0-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c3d0-110">Se si usa [!INCLUDE[dublin](../../../includes/dublin-md.md)] per ospitare i flussi di lavoro in una Web farm, le istanze verranno spostate da AppFabric tra server di AppFabric differenti.</span><span class="sxs-lookup"><span data-stu-id="5c3d0-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="5c3d0-111">È necessario quindi che le risorse possano essere condivise tra tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="5c3d0-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="5c3d0-112">Nessuna delle attività predefinite del flusso di lavoro di .NET 4 contiene operazioni di accesso alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="5c3d0-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="5c3d0-113">Poiché AppFabric non offre alcun meccanismo per contrassegnare un flusso di lavoro come non spostabile, uno sviluppatore non deve creare attività personalizzate che non vengono eseguite correttamente quando un flusso di lavoro viene spostato.</span><span class="sxs-lookup"><span data-stu-id="5c3d0-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3d0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c3d0-114">See Also</span></span>  
 [<span data-ttu-id="5c3d0-115">Flussi di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="5c3d0-115">Flowchart Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
