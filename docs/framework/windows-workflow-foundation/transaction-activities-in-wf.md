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
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="50a46-102">Attività di transazione in WF</span><span class="sxs-lookup"><span data-stu-id="50a46-102">Transaction Activities in WF</span></span>
<span data-ttu-id="50a46-103">In [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] sono disponibili numerose attività fornite dal sistema per la modellazione delle transazioni, la compensazione e l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="50a46-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="50a46-104">Questi modelli di programmazione consentono al flusso di lavoro di proseguire esecuzione nel caso di modifiche nella logica di business e durante la gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="50a46-104">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="50a46-105">le transazioni, compensazione e l'annullamento, vedere [transazioni](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [compensazione](../../../docs/framework/windows-workflow-foundation/compensation.md), e [annullamento](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="50a46-105"> transactions, compensation, and cancellation, see [Transactions](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [Compensation](../../../docs/framework/windows-workflow-foundation/compensation.md), and [Cancellation](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="50a46-106">Attività di transazione</span><span class="sxs-lookup"><span data-stu-id="50a46-106">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="50a46-107">Associa la logica di annullamento, sotto forma di un'attività, a un percorso principale di esecuzione, anch'esso espresso come attività.</span><span class="sxs-lookup"><span data-stu-id="50a46-107">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="50a46-108">Supporta la compensazione delle relative attività figlio.</span><span class="sxs-lookup"><span data-stu-id="50a46-108">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="50a46-109">Richiama in modo esplicito il gestore compensazione di un oggetto <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="50a46-109">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="50a46-110">Richiama in modo esplicito il gestore conferma di un oggetto <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="50a46-110">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="50a46-111">Demarca un limite della transazione.</span><span class="sxs-lookup"><span data-stu-id="50a46-111">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="50a46-112">Ambito della durata di una transazione iniziata da un messaggio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="50a46-112">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="50a46-113">È possibile che la transazione sia propagata nel flusso di lavoro al messaggio di avvio o venga creata dal dispatcher alla ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="50a46-113">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="50a46-114">**Nota:** il <xref:System.ServiceModel.Activities.TransactedReceiveScope> si trova nel **messaggistica** sezione il **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="50a46-114">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
