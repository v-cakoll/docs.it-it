---
title: Riallocazione dell'utilità di progettazione del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 4b89c84d6761fa1e16bc17794885f64086a920f8
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716715"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="f5216-102">Riallocazione dell'utilità di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f5216-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="f5216-103">Il Progettazione flussi di lavoro di Windows può essere riallocato in ambienti esterni a Visual Studio 2012 ai fini della creazione, della modifica e del monitoraggio dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f5216-103">The Windows Workflow Designer can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="f5216-104">Il tipo <xref:System.Activities.Presentation.WorkflowDesigner> è un wrapper dell'area di disegno, della griglia delle proprietà e di altri elementi ed espone un modello di programmazione di base per gestire la maggior parte degli scenari di riallocazione della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f5216-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="f5216-105">Ospitare la <xref:System.Activities.Presentation.WorkflowDesigner> all'interno di un'applicazione Windows Presentation Foundation (WPF) è uno scenario di riallocazione comune per Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f5216-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for Workflow Designer.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f5216-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f5216-106">In This Section</span></span>
 [<span data-ttu-id="f5216-107">Attività 1: Creare una nuova applicazione Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="f5216-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="f5216-108">Attività 2: Ospitare Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="f5216-108">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="f5216-109">Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="f5216-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="f5216-110">Supporto delle nuove funzionalità di Workflow Foundation 4.5 in Progettazione flussi di lavoro riallocato</span><span class="sxs-lookup"><span data-stu-id="f5216-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="f5216-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5216-111">See also</span></span>

- [<span data-ttu-id="f5216-112">Personalizzazione della fase di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f5216-112">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
