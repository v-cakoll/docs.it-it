---
title: Attività della macchina a stati in WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120913"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="9c33b-102">Attività della macchina a stati in WF</span><span class="sxs-lookup"><span data-stu-id="9c33b-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="9c33b-103">offre diverse attività fornite dal sistema e ActivityDesigner per la creazione di flussi.</span><span class="sxs-lookup"><span data-stu-id="9c33b-103">provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="9c33b-104">Esegue attività contenute usando il comune paradigma della macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="9c33b-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="9c33b-105">Rappresenta lo stato di una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="9c33b-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="9c33b-106">Rappresenta uno stato di chiusura in una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="9c33b-106">Represents a terminating state in a state machine.</span></span> <xref:System.Activities.Core.Presentation.FinalState> <span data-ttu-id="9c33b-107">è un ActivityDesigner che, quando utilizzata crea un <xref:System.Activities.Statements.State> preconfigurato come stato finale.</span><span class="sxs-lookup"><span data-stu-id="9c33b-107">is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="9c33b-108">Per altre informazioni, vedere [ActivityDesigner FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="9c33b-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="9c33b-109">Rappresenta la transizione tra due stati.</span><span class="sxs-lookup"><span data-stu-id="9c33b-109">Represents the transition between two states.</span></span> <span data-ttu-id="9c33b-110">È presente alcun **casella degli strumenti** elemento per <xref:System.Activities.Statements.Transition>; le transizioni vengono create nella finestra di progettazione del flusso di lavoro trascinando e rilasciando una linea tra due stati o rilasciando uno stato sui triangoli visualizzati quando uno stato viene passato sopra un altro .</span><span class="sxs-lookup"><span data-stu-id="9c33b-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="9c33b-111">Per altre informazioni, vedere [ActivityDesigner Transition](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="9c33b-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c33b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c33b-112">See also</span></span>

- [<span data-ttu-id="9c33b-113">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="9c33b-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
