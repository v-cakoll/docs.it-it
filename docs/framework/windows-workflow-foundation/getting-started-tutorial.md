---
title: Introduzione Tutorial2
description: Questo articolo inizia una serie di esercitazioni che illustrano la programmazione Windows Workflow Foundation applicazioni.
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 148ba77231067bf5f8ff1d8b444b83d951ce8761
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419850"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="599b8-103">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="599b8-103">Getting Started Tutorial</span></span>
<span data-ttu-id="599b8-104">In questa sezione è disponibile una serie di argomenti di procedura dettagliata che introducono le applicazioni di programmazione Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="599b8-104">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="599b8-105">Seguendo le procedure di questi argomenti, verrà compilata un'applicazione che è un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="599b8-105">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="599b8-106">Nel primo argomento dell'esercitazione vengono descritti i passaggi per creare le attività personalizzate richieste per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="599b8-106">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="599b8-107">Nel secondo argomento, queste attività vengono assemblate in un flusso di lavoro del diagramma di flusso insieme alle attività incorporate del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="599b8-107">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="599b8-108">Nel terzo argomento, l'applicazione host viene configurata in modo da eseguire il flusso di lavoro e nell'ultimo argomento viene introdotta la persistenza.</span><span class="sxs-lookup"><span data-stu-id="599b8-108">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="599b8-109">Ogni passaggio in questo processo dipende dai passaggi precedenti, pertanto si consiglia di completarli in ordine.</span><span class="sxs-lookup"><span data-stu-id="599b8-109">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="599b8-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="599b8-110">In This Section</span></span>  
 [<span data-ttu-id="599b8-111">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="599b8-111">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="599b8-112">Viene descritto come creare un'attività personalizzata che deriva dall'oggetto <xref:System.Activities.NativeActivity%601> e come comporre questa attività insieme a un'attività incorporata in un'attività composita tramite l'ActivityDesigner.</span><span class="sxs-lookup"><span data-stu-id="599b8-112">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="599b8-113">Procedura: Creare un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="599b8-113">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="599b8-114">Viene descritto come creare flussi di lavoro di diagramma di flusso, sequenziali e di macchina a stati tramite le attività predefinite e le attività personalizzate dall'esercitazione precedente.</span><span class="sxs-lookup"><span data-stu-id="599b8-114">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="599b8-115">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="599b8-115">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="599b8-116">Viene descritto come richiamare un flusso di lavoro da un ambiente host, come passare i dati all'interno e all'esterno di un flusso di lavoro e come riprendere i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="599b8-116">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="599b8-117">Procedura: Creare ed eseguire un flusso di lavoro con esecuzione prolungata</span><span class="sxs-lookup"><span data-stu-id="599b8-117">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="599b8-118">Viene descritto come aggiungere la persistenza a un'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="599b8-118">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="599b8-119">Procedura: Creare un partecipante di rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="599b8-119">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="599b8-120">Viene descritto come creare un partecipante del rilevamento personalizzato e un profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="599b8-120">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="599b8-121">Procedura: Ospitare più versioni di un flusso di lavoro side-by-side</span><span class="sxs-lookup"><span data-stu-id="599b8-121">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="599b8-122">Viene descritto come usare `WorkflowIdentity` per ospitare più versioni di un flusso di lavoro side-by-side.</span><span class="sxs-lookup"><span data-stu-id="599b8-122">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="599b8-123">Procedura: Aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione</span><span class="sxs-lookup"><span data-stu-id="599b8-123">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="599b8-124">Viene descritto come usare l'aggiornamento dinamico per modificare le istanze in esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="599b8-124">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="599b8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="599b8-125">See also</span></span>

- [<span data-ttu-id="599b8-126">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="599b8-126">Windows Workflow Foundation Programming</span></span>](programming.md)
