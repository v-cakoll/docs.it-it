---
title: "Attività di gestione degli errori in WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a8b7ed6837e9ee88e85324ed5d7a2b9ff3e419a9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="ace56-102">Attività di gestione degli errori in WF</span><span class="sxs-lookup"><span data-stu-id="ace56-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="ace56-103"> offre diverse attività fornite dal sistema per l'implementazione della gestione e risoluzione degli errori.</span><span class="sxs-lookup"><span data-stu-id="ace56-103"> provides several system-provided activities for implementing error handling and recovery.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="ace56-104">[Eccezioni](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="ace56-104"> [Exceptions](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="ace56-105">Attività di gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="ace56-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="ace56-106">Genera nuovamente l'ultima eccezione generata dall'interno di un'attività `TryCatch`.</span><span class="sxs-lookup"><span data-stu-id="ace56-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="ace56-107">Genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ace56-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="ace56-108">Implementa la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="ace56-108">Implements exception handling.</span></span>|
