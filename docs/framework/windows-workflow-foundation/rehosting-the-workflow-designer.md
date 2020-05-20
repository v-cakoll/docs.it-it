---
title: Riallocazione dell'utilità di progettazione del flusso di lavoro
description: Il Progettazione flussi di lavoro di Windows può essere riallocato in ambienti esterni a Visual Studio per la creazione, la modifica e il monitoraggio dei flussi di lavoro.
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 34709b84d445b2bb07e32bfd3f34d06072f125bf
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421423"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="45cee-103">Riallocazione dell'utilità di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="45cee-103">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="45cee-104">Il Progettazione flussi di lavoro di Windows può essere riallocato in ambienti esterni a Visual Studio 2012 ai fini della creazione, della modifica e del monitoraggio dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="45cee-104">The Windows Workflow Designer can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="45cee-105">Il tipo <xref:System.Activities.Presentation.WorkflowDesigner> è un wrapper dell'area di disegno, della griglia delle proprietà e di altri elementi ed espone un modello di programmazione di base per gestire la maggior parte degli scenari di riallocazione della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="45cee-105">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="45cee-106">L'hosting <xref:System.Activities.Presentation.WorkflowDesigner> di all'interno di un'applicazione Windows Presentation Foundation (WPF) è uno scenario di riallocazione comune per progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="45cee-106">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for Workflow Designer.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="45cee-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="45cee-107">In This Section</span></span>
 [<span data-ttu-id="45cee-108">Attività 1: Creare una nuova applicazione Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="45cee-108">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="45cee-109">Attività 2: Ospitare Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="45cee-109">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="45cee-110">Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="45cee-110">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="45cee-111">Supporto delle nuove funzionalità di Workflow Foundation 4.5 in Progettazione flussi di lavoro riallocato</span><span class="sxs-lookup"><span data-stu-id="45cee-111">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="45cee-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45cee-112">See also</span></span>

- [<span data-ttu-id="45cee-113">Personalizzazione della fase di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="45cee-113">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
