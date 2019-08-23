---
title: 'Procedura: Creare un flusso di lavoro'
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 7f0bef673ff14ded13306a1fc26e09695601799d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962303"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="5d20e-102">Procedura: Creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="5d20e-102">How to: Create a Workflow</span></span>
<span data-ttu-id="5d20e-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="5d20e-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="5d20e-104">Negli argomenti di questa sezione viene illustrata la creazione di un flusso di lavoro che utilizza sia attività predefinite <xref:System.Activities.Statements.Flowchart> , ad esempio l'attività, che le attività [personalizzate dalla procedura precedente: Creare un argomento](how-to-create-an-activity.md) di attività.</span><span class="sxs-lookup"><span data-stu-id="5d20e-104">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="5d20e-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="5d20e-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="5d20e-106">Solo uno degli argomenti di questa sezione è necessario per il completamento dell'esercitazione. Selezionare lo stile di proprio interesse e seguire quella procedura.</span><span class="sxs-lookup"><span data-stu-id="5d20e-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="5d20e-107">Se lo si desidera, è comunque possibile completare tutti argomenti.</span><span class="sxs-lookup"><span data-stu-id="5d20e-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d20e-108">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="5d20e-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="5d20e-109">Per completare questo argomento, è necessario completare [prima di tutto come: Creare un'attività](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="5d20e-109">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d20e-110">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="5d20e-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d20e-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5d20e-111">In This Section</span></span>  
 [<span data-ttu-id="5d20e-112">Procedura: Creazione di un flusso di lavoro sequenziale</span><span class="sxs-lookup"><span data-stu-id="5d20e-112">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="5d20e-113">Viene descritto come creare un flusso di lavoro sequenziale usando l'attività <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="5d20e-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="5d20e-114">Procedura: Creare un flusso di lavoro diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="5d20e-114">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="5d20e-115">Viene descritto come creare un flusso di lavoro di un diagramma di flusso usando l'attività <xref:System.Activities.Statements.Flowchart>.</span><span class="sxs-lookup"><span data-stu-id="5d20e-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="5d20e-116">Procedura: Creare un flusso di lavoro della macchina a Stati</span><span class="sxs-lookup"><span data-stu-id="5d20e-116">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="5d20e-117">Viene descritto come creare un flusso di lavoro di una macchina a stati usando l'attività <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="5d20e-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d20e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d20e-118">See also</span></span>

- [<span data-ttu-id="5d20e-119">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="5d20e-119">Windows Workflow Foundation Programming</span></span>](programming.md)
