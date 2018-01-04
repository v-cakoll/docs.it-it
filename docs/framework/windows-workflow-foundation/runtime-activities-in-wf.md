---
title: "Attività di runtime in WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3386138f01d4865b02ca821a30da68e5d73b64e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="d4edc-102">Attività di runtime in WF</span><span class="sxs-lookup"><span data-stu-id="d4edc-102">Runtime Activities in WF</span></span>
<span data-ttu-id="d4edc-103">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] sono disponibili diverse attività fornite dal sistema per l'accesso alle funzionalità di esecuzione del flusso di lavoro, ad esempio la persistenza e la chiusura.</span><span class="sxs-lookup"><span data-stu-id="d4edc-103">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="d4edc-104">Attività</span><span class="sxs-lookup"><span data-stu-id="d4edc-104">Activity</span></span>|<span data-ttu-id="d4edc-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4edc-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="d4edc-106">Richiede in modo esplicito la persistenza dello stato del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d4edc-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="d4edc-107">Termina l'istanza del flusso di lavoro in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d4edc-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="d4edc-108">Attività contenitore che impedisce la persistenza delle attività figlio.</span><span class="sxs-lookup"><span data-stu-id="d4edc-108">A container activity that prevents child activities from persisting.</span></span>|
