---
title: Attività della macchina a stati in WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: eee507f873cde3aabce09c9b3fdb1620cd79fdab
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710316"
---
# <a name="state-machine-activities-in-wf"></a>Attività della macchina a stati in WF
In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] sono disponibili numerose attività fornite dal sistema e ActivityDesigner per la creazione di flussi di lavoro di macchine a stati.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Esegue attività contenute usando il comune paradigma della macchina a stati.|  
|<xref:System.Activities.Statements.State>|Rappresenta lo stato di una macchina a stati.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Rappresenta uno stato di chiusura in una macchina a stati. <xref:System.Activities.Core.Presentation.FinalState> è un ActivityDesigner che, quando usato, crea un elemento <xref:System.Activities.Statements.State> preconfigurato come stato di chiusura. Per altre informazioni, vedere [ActivityDesigner FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Rappresenta la transizione tra due stati. È presente alcun **casella degli strumenti** elemento per <xref:System.Activities.Statements.Transition>; le transizioni vengono create nella finestra di progettazione del flusso di lavoro trascinando e rilasciando una linea tra due stati o rilasciando uno stato sui triangoli visualizzati quando uno stato viene passato sopra un altro . Per altre informazioni, vedere [ActivityDesigner Transition](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Vedere anche
- [Esercitazione introduttiva](getting-started-tutorial.md)
