---
title: "Attività di transazione in WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b12cfa1cecde648e66872784eb1e353f8c16da8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-activities-in-wf"></a>Attività di transazione in WF
In [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] sono disponibili numerose attività fornite dal sistema per la modellazione delle transazioni, la compensazione e l'annullamento. Questi modelli di programmazione consentono al flusso di lavoro di proseguire esecuzione nel caso di modifiche nella logica di business e durante la gestione degli errori. [!INCLUDE[crabout](../../../includes/crabout-md.md)]le transazioni, compensazione e l'annullamento, vedere [transazioni](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [compensazione](../../../docs/framework/windows-workflow-foundation/compensation.md), e [annullamento](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).  
  
## <a name="transaction-activities"></a>Attività di transazione  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|Associa la logica di annullamento, sotto forma di un'attività, a un percorso principale di esecuzione, anch'esso espresso come attività.|  
|<xref:System.Activities.Statements.CompensableActivity>|Supporta la compensazione delle relative attività figlio.|  
|<xref:System.Activities.Statements.Compensate>|Richiama in modo esplicito il gestore compensazione di un oggetto <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.Confirm>|Richiama in modo esplicito il gestore conferma di un oggetto <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.TransactionScope>|Demarca un limite della transazione.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|Ambito della durata di una transazione iniziata da un messaggio ricevuto. È possibile che la transazione sia propagata nel flusso di lavoro al messaggio di avvio o venga creata dal dispatcher alla ricezione del messaggio. **Nota:** il <xref:System.ServiceModel.Activities.TransactedReceiveScope> si trova nel **messaggistica** sezione il **della casella degli strumenti**.|
