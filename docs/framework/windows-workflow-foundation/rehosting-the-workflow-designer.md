---
title: Riallocazione dell'utilità di progettazione del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 98048ca58bf635f4e87241befa083dc240deaecf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968181"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="ea5fd-102">Riallocazione dell'utilità di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ea5fd-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="ea5fd-103">Il [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] può essere ospitato nuovamente in ambienti all'esterno di Visual Studio 2012 ai fini della creazione, modifica e il monitoraggio dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ea5fd-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="ea5fd-104">Il tipo <xref:System.Activities.Presentation.WorkflowDesigner> è un wrapper dell'area di disegno, della griglia delle proprietà e di altri elementi ed espone un modello di programmazione di base per gestire la maggior parte degli scenari di riallocazione della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ea5fd-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="ea5fd-105">Hosting di <xref:System.Activities.Presentation.WorkflowDesigner> applicazione all'interno di Windows Presentation Foundation (WPF) è uno scenario di riallocazione comune per [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea5fd-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ea5fd-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ea5fd-106">In This Section</span></span>
 [<span data-ttu-id="ea5fd-107">Attività 1: Creare una nuova applicazione Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="ea5fd-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="ea5fd-108">Attività 2: Host di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ea5fd-108">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="ea5fd-109">Attività 3: Creare la casella degli strumenti e PropertyGrid riquadri</span><span class="sxs-lookup"><span data-stu-id="ea5fd-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="ea5fd-110">Supporto delle nuove funzionalità di Workflow Foundation 4.5 in Progettazione flussi di lavoro riallocato</span><span class="sxs-lookup"><span data-stu-id="ea5fd-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="ea5fd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea5fd-111">See also</span></span>

- [<span data-ttu-id="ea5fd-112">Personalizzazione della fase di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ea5fd-112">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
