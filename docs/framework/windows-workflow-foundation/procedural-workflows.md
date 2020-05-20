---
title: Flussi di lavoro procedurali
description: In Workflow Foundation, i flussi di lavoro procedurali usano metodi di controllo del flusso simili a quelli presenti nei linguaggi procedurali.
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 97664c1352928e7d05c2ed15fc118dd21474cfc3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421436"
---
# <a name="procedural-workflows"></a><span data-ttu-id="9cdb4-103">Flussi di lavoro procedurali</span><span class="sxs-lookup"><span data-stu-id="9cdb4-103">Procedural Workflows</span></span>
<span data-ttu-id="9cdb4-104">Nei flussi di lavoro procedurali vengono usati metodi di controllo del flusso simili a quelli dei linguaggi procedurali.</span><span class="sxs-lookup"><span data-stu-id="9cdb4-104">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="9cdb4-105">Tra questi costrutti sono inclusi `While` e `If`.</span><span class="sxs-lookup"><span data-stu-id="9cdb4-105">These constructs include `While` and `If`.</span></span> <span data-ttu-id="9cdb4-106">Questi flussi di lavoro possono essere creati liberamente usando altre attività di controllo del flusso quale <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="9cdb4-106">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="9cdb4-107">Controllo del flusso di esecuzione</span><span class="sxs-lookup"><span data-stu-id="9cdb4-107">Controlling Execution Flow</span></span>  
 <span data-ttu-id="9cdb4-108">La libreria di attività del flusso di lavoro dispone di attività per modellare la maggior parte dei metodi di controllo del flusso usati nei linguaggi procedurali,</span><span class="sxs-lookup"><span data-stu-id="9cdb4-108">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="9cdb4-109">Tra queste sono incluse:</span><span class="sxs-lookup"><span data-stu-id="9cdb4-109">These include:</span></span>  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="9cdb4-110">Per usare le attività di controllo del flusso, trascinarle dalla casella degli strumenti **attività** in un'attività composta all'interno della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9cdb4-110">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9cdb4-111">Se si utilizzano le funzionalità di hosting di Windows Server AppFabric per ospitare i flussi di lavoro in una Web farm, AppFabric sposta le istanze tra diversi server AppFabric.</span><span class="sxs-lookup"><span data-stu-id="9cdb4-111">If using the hosting features of Windows Server AppFabric to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="9cdb4-112">È necessario quindi che le risorse possano essere condivise tra tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="9cdb4-112">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="9cdb4-113">Nessuna delle attività predefinite del flusso di lavoro di .NET 4 contiene operazioni di accesso alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="9cdb4-113">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="9cdb4-114">Poiché AppFabric non offre alcun meccanismo per contrassegnare un flusso di lavoro come non spostabile, uno sviluppatore non deve creare attività personalizzate che non vengono eseguite correttamente quando un flusso di lavoro viene spostato.</span><span class="sxs-lookup"><span data-stu-id="9cdb4-114">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cdb4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cdb4-115">See also</span></span>

- [<span data-ttu-id="9cdb4-116">Flussi di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="9cdb4-116">Flowchart Workflows</span></span>](flowchart-workflows.md)
