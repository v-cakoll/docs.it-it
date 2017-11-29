---
title: "Riallocazione dell'utilità di progettazione del flusso di lavoro"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5ca7eec49dec0e9b8896b31147a3cd40ffeef5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="19778-102">Riallocazione dell'utilità di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="19778-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="19778-103">[!INCLUDE[wfd1](../../../includes/wfd1-md.md)] può essere ospitato nuovamente in ambienti esterni a [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] per creare, modificare e monitorare i flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="19778-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] for the purposes of creating, modifying, and monitoring workflows.</span></span>  
  
 <span data-ttu-id="19778-104">Il tipo <xref:System.Activities.Presentation.WorkflowDesigner> è un wrapper dell'area di disegno, della griglia delle proprietà e di altri elementi ed espone un modello di programmazione di base per gestire la maggior parte degli scenari di riallocazione della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="19778-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="19778-105">L'hosting dell'oggetto <xref:System.Activities.Presentation.WorkflowDesigner> in un'applicazione [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] è uno scenario di riallocazione comune per [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19778-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19778-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="19778-106">In This Section</span></span>  
 [<span data-ttu-id="19778-107">Attività 1: Creare una nuova applicazione Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="19778-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
  
 [<span data-ttu-id="19778-108">Attività 2: Ospitare Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="19778-108">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)  
  
 [<span data-ttu-id="19778-109">Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="19778-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)  
  
 [<span data-ttu-id="19778-110">Supporto delle nuove funzionalità di Workflow Foundation 4.5 in Progettazione flussi di lavoro riallocato</span><span class="sxs-lookup"><span data-stu-id="19778-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md)  
  
## <a name="see-also"></a><span data-ttu-id="19778-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19778-111">See Also</span></span>  
 [<span data-ttu-id="19778-112">Personalizzazione della fase di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="19778-112">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
