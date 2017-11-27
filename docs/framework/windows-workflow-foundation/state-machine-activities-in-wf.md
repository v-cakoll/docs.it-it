---
title: "Attività della macchina a stati in WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5056557c9fee74e9a16b235220c797e1f6356ce3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="85ba8-102">Attività della macchina a stati in WF</span><span class="sxs-lookup"><span data-stu-id="85ba8-102">State Machine Activities in WF</span></span>
<span data-ttu-id="85ba8-103">In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] sono disponibili numerose attività fornite dal sistema e ActivityDesigner per la creazione di flussi di lavoro di macchine a stati.</span><span class="sxs-lookup"><span data-stu-id="85ba8-103">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="85ba8-104">Esegue attività contenute usando il comune paradigma della macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="85ba8-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="85ba8-105">Rappresenta lo stato di una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="85ba8-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="85ba8-106">Rappresenta uno stato di chiusura in una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="85ba8-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="85ba8-107"><xref:System.Activities.Core.Presentation.FinalState> è un ActivityDesigner che, quando usato, crea un elemento <xref:System.Activities.Statements.State> preconfigurato come stato di chiusura.</span><span class="sxs-lookup"><span data-stu-id="85ba8-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="85ba8-108">Per ulteriori informazioni, vedere [ActivityDesigner FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="85ba8-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="85ba8-109">Rappresenta la transizione tra due stati.</span><span class="sxs-lookup"><span data-stu-id="85ba8-109">Represents the transition between two states.</span></span> <span data-ttu-id="85ba8-110">Non esiste alcun **della casella degli strumenti** elemento per <xref:System.Activities.Statements.Transition>; le transizioni vengono create nella finestra di progettazione del flusso di lavoro trascinando e rilasciando una linea tra due stati o rilasciando uno stato sui triangoli visualizzati quando uno stato viene passato sopra un altro .</span><span class="sxs-lookup"><span data-stu-id="85ba8-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="85ba8-111">Per ulteriori informazioni, vedere [ActivityDesigner Transition](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="85ba8-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85ba8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85ba8-112">See Also</span></span>  
 [<span data-ttu-id="85ba8-113">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="85ba8-113">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
