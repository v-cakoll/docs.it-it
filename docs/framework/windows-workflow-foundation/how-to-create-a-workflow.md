---
title: 'Procedura: creare un flusso di lavoro'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
caps.latest.revision: "34"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f16df123837b2233efd156bf35975e3adbe7279
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="0814a-102">Procedura: creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0814a-102">How to: Create a Workflow</span></span>
<span data-ttu-id="0814a-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="0814a-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="0814a-104">Gli argomenti in questo passaggio della sezione tramite la creazione di un flusso di lavoro che utilizza entrambe le attività predefinite, ad esempio il <xref:System.Activities.Statements.Flowchart> attività e le attività personalizzate dal precedente [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="0814a-104">This topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="0814a-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="0814a-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="0814a-106">Solo uno degli argomenti di questa sezione è necessario per il completamento dell'esercitazione. Selezionare lo stile di proprio interesse e seguire quella procedura.</span><span class="sxs-lookup"><span data-stu-id="0814a-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="0814a-107">Se lo si desidera, è comunque possibile completare tutti argomenti.</span><span class="sxs-lookup"><span data-stu-id="0814a-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0814a-108">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="0814a-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="0814a-109">Per completare questo argomento, è necessario prima completare [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="0814a-109">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0814a-110">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="0814a-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0814a-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0814a-111">In This Section</span></span>  
 [<span data-ttu-id="0814a-112">Procedura: Creare un flusso di lavoro sequenziale</span><span class="sxs-lookup"><span data-stu-id="0814a-112">How to: Create a Sequential Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="0814a-113">Viene descritto come creare un flusso di lavoro sequenziale usando l'attività <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="0814a-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="0814a-114">Procedura: Creare un flusso di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="0814a-114">How to: Create a Flowchart Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="0814a-115">Viene descritto come creare un flusso di lavoro di un diagramma di flusso usando l'attività <xref:System.Activities.Statements.Flowchart>.</span><span class="sxs-lookup"><span data-stu-id="0814a-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="0814a-116">Procedura: Creare un flusso di lavoro della macchina a stati</span><span class="sxs-lookup"><span data-stu-id="0814a-116">How to: Create a State Machine Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="0814a-117">Viene descritto come creare un flusso di lavoro di una macchina a stati usando l'attività <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="0814a-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0814a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0814a-118">See Also</span></span>  
 [<span data-ttu-id="0814a-119">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="0814a-119">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
