---
title: Attività di runtime in WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938099"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="959f0-102">Attività di runtime in WF</span><span class="sxs-lookup"><span data-stu-id="959f0-102">Runtime Activities in WF</span></span>
<span data-ttu-id="959f0-103">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] sono disponibili diverse attività fornite dal sistema per l'accesso alle funzionalità di esecuzione del flusso di lavoro, ad esempio la persistenza e la chiusura.</span><span class="sxs-lookup"><span data-stu-id="959f0-103">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="959f0-104">Attività</span><span class="sxs-lookup"><span data-stu-id="959f0-104">Activity</span></span>|<span data-ttu-id="959f0-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="959f0-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="959f0-106">Richiede in modo esplicito la persistenza dello stato del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="959f0-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="959f0-107">Termina l'istanza del flusso di lavoro in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="959f0-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="959f0-108">Attività contenitore che impedisce la persistenza delle attività figlio.</span><span class="sxs-lookup"><span data-stu-id="959f0-108">A container activity that prevents child activities from persisting.</span></span>|
