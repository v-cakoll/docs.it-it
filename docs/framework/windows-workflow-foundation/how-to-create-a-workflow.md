---
title: 'Procedura: Creare un flusso di lavoro'
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 75af0e1dae43cb424dcd13f9f2540d65fbdca126
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558995"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="72357-102">Procedura: Creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="72357-102">How to: Create a Workflow</span></span>
<span data-ttu-id="72357-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="72357-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="72357-104">Negli argomenti di questa sezione eseguire la creazione di un flusso di lavoro che vengono usate sia attività incorporate, ad esempio la <xref:System.Activities.Statements.Flowchart> attività e le attività personalizzate dal precedente [come: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="72357-104">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="72357-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="72357-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="72357-106">Solo uno degli argomenti di questa sezione è necessario per il completamento dell'esercitazione. Selezionare lo stile di proprio interesse e seguire quella procedura.</span><span class="sxs-lookup"><span data-stu-id="72357-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="72357-107">Se lo si desidera, è comunque possibile completare tutti argomenti.</span><span class="sxs-lookup"><span data-stu-id="72357-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72357-108">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="72357-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="72357-109">Per completare questo argomento, è necessario completare prima [come: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="72357-109">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72357-110">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="72357-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72357-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="72357-111">In This Section</span></span>  
 [<span data-ttu-id="72357-112">Procedura: Creare un flusso di lavoro sequenza</span><span class="sxs-lookup"><span data-stu-id="72357-112">How to: Create a Sequential Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="72357-113">Viene descritto come creare un flusso di lavoro sequenziale usando l'attività <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="72357-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="72357-114">Procedura: Creare un flusso di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="72357-114">How to: Create a Flowchart Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="72357-115">Viene descritto come creare un flusso di lavoro di un diagramma di flusso usando l'attività <xref:System.Activities.Statements.Flowchart>.</span><span class="sxs-lookup"><span data-stu-id="72357-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="72357-116">Procedura: Creare un flusso di lavoro macchina a stati</span><span class="sxs-lookup"><span data-stu-id="72357-116">How to: Create a State Machine Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="72357-117">Viene descritto come creare un flusso di lavoro di una macchina a stati usando l'attività <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="72357-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72357-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72357-118">See also</span></span>
- [<span data-ttu-id="72357-119">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="72357-119">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
