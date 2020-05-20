---
title: 'Procedura: creare un flusso di lavoro'
description: Completare una delle tre opzioni in questa sezione per creare un flusso di lavoro come parte di questa esercitazione su Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 7e4575436405e74b7575e55bea37a1a99d879a3e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419564"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="a0c2f-103">Procedura: creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="a0c2f-103">How to: Create a Workflow</span></span>
<span data-ttu-id="a0c2f-104">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="a0c2f-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="a0c2f-105">Negli argomenti di questa sezione viene illustrata la creazione di un flusso di lavoro che usa sia attività predefinite, ad esempio l' <xref:System.Activities.Statements.Flowchart> attività, che le attività personalizzate dell'argomento [procedura: creare un'attività](how-to-create-an-activity.md) precedente.</span><span class="sxs-lookup"><span data-stu-id="a0c2f-105">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="a0c2f-106">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="a0c2f-106">The workflow models a number guessing game.</span></span> <span data-ttu-id="a0c2f-107">Solo uno degli argomenti di questa sezione è necessario per il completamento dell'esercitazione. Selezionare lo stile di proprio interesse e seguire quella procedura.</span><span class="sxs-lookup"><span data-stu-id="a0c2f-107">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="a0c2f-108">Se lo si desidera, è comunque possibile completare tutti argomenti.</span><span class="sxs-lookup"><span data-stu-id="a0c2f-108">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0c2f-109">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="a0c2f-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="a0c2f-110">Per completare questo argomento, è necessario completare prima di tutto [procedura: creare un'attività](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="a0c2f-110">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0c2f-111">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="a0c2f-111">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0c2f-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a0c2f-112">In This Section</span></span>  
 [<span data-ttu-id="a0c2f-113">Procedura: creare un flusso di lavoro sequenziale</span><span class="sxs-lookup"><span data-stu-id="a0c2f-113">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="a0c2f-114">Viene descritto come creare un flusso di lavoro sequenziale usando l'attività <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="a0c2f-114">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="a0c2f-115">Procedura: Creare un flusso di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="a0c2f-115">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="a0c2f-116">Viene descritto come creare un flusso di lavoro di un diagramma di flusso usando l'attività <xref:System.Activities.Statements.Flowchart>.</span><span class="sxs-lookup"><span data-stu-id="a0c2f-116">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="a0c2f-117">Procedura: Creare un flusso di lavoro della macchina a stati</span><span class="sxs-lookup"><span data-stu-id="a0c2f-117">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="a0c2f-118">Viene descritto come creare un flusso di lavoro di una macchina a stati usando l'attività <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="a0c2f-118">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c2f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0c2f-119">See also</span></span>

- [<span data-ttu-id="a0c2f-120">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="a0c2f-120">Windows Workflow Foundation Programming</span></span>](programming.md)
