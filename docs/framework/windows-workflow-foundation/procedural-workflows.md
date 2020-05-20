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
# <a name="procedural-workflows"></a>Flussi di lavoro procedurali
Nei flussi di lavoro procedurali vengono usati metodi di controllo del flusso simili a quelli dei linguaggi procedurali. Tra questi costrutti sono inclusi `While` e `If`. Questi flussi di lavoro possono essere creati liberamente usando altre attività di controllo del flusso quale <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Sequence>.  
  
## <a name="controlling-execution-flow"></a>Controllo del flusso di esecuzione  
 La libreria di attività del flusso di lavoro dispone di attività per modellare la maggior parte dei metodi di controllo del flusso usati nei linguaggi procedurali, Tra queste sono incluse:  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 Per usare le attività di controllo del flusso, trascinarle dalla casella degli strumenti **attività** in un'attività composta all'interno della finestra di progettazione.  
  
> [!NOTE]
> Se si utilizzano le funzionalità di hosting di Windows Server AppFabric per ospitare i flussi di lavoro in una Web farm, AppFabric sposta le istanze tra diversi server AppFabric. È necessario quindi che le risorse possano essere condivise tra tutti i nodi.  Nessuna delle attività predefinite del flusso di lavoro di .NET 4 contiene operazioni di accesso alle risorse locali. Poiché AppFabric non offre alcun meccanismo per contrassegnare un flusso di lavoro come non spostabile, uno sviluppatore non deve creare attività personalizzate che non vengono eseguite correttamente quando un flusso di lavoro viene spostato.  
  
## <a name="see-also"></a>Vedere anche

- [Flussi di lavoro del diagramma di flusso](flowchart-workflows.md)
