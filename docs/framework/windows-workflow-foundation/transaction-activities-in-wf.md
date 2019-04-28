---
title: Attività di transazione in WF
ms.date: 03/30/2017
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
ms.openlocfilehash: 7ffd64abdc6edf45174d4b756833d65ec0ef747c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670261"
---
# <a name="transaction-activities-in-wf"></a>Attività di transazione in WF
In [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] sono disponibili numerose attività fornite dal sistema per la modellazione delle transazioni, la compensazione e l'annullamento. Questi modelli di programmazione consentono al flusso di lavoro di proseguire esecuzione nel caso di modifiche nella logica di business e durante la gestione degli errori. Per altre informazioni sull'annullamento, compensazione e transazioni, vedere [transazioni](workflow-transactions.md), [compensazione](compensation.md), e [annullamento](modeling-cancellation-behavior-in-workflows.md).  
  
## <a name="transaction-activities"></a>Attività di transazione  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|Associa la logica di annullamento, sotto forma di un'attività, a un percorso principale di esecuzione, anch'esso espresso come attività.|  
|<xref:System.Activities.Statements.CompensableActivity>|Supporta la compensazione delle relative attività figlio.|  
|<xref:System.Activities.Statements.Compensate>|Richiama in modo esplicito il gestore compensazione di un oggetto <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.Confirm>|Richiama in modo esplicito il gestore conferma di un oggetto <xref:System.Activities.Statements.CompensableActivity>.|  
|<xref:System.Activities.Statements.TransactionScope>|Demarca un limite della transazione.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|Ambito della durata di una transazione iniziata da un messaggio ricevuto. È possibile che la transazione sia propagata nel flusso di lavoro al messaggio di avvio o venga creata dal dispatcher alla ricezione del messaggio. **Nota:**  Il <xref:System.ServiceModel.Activities.TransactedReceiveScope> si trova nel **messaggistica** sezione del **casella degli strumenti**.|
