---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 845b344cee6c47a0c2f125caab7965ef8f65f336
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="debed-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="debed-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="debed-103">La macchina a stati dell'integrazione di un partecipante è passata allo stato di operazione completata.</span><span class="sxs-lookup"><span data-stu-id="debed-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="debed-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="debed-104">Description</span></span>  
 <span data-ttu-id="debed-105">Traccia eseguita quando l'elaborazione 2PC dell'integrazione di un partecipante subordinato è stata completata.</span><span class="sxs-lookup"><span data-stu-id="debed-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="debed-106">Il risultato dell'integrazione può essere "Committed" o "Aborted", a indicare rispettivamente il commit o l'interruzione di una transazione.</span><span class="sxs-lookup"><span data-stu-id="debed-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="debed-107">Questa traccia viene inoltre eseguita se un partecipante vota "ReadOnly" durante la fase di preparazione.</span><span class="sxs-lookup"><span data-stu-id="debed-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="debed-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="debed-108">See Also</span></span>  
 [<span data-ttu-id="debed-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="debed-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="debed-110">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="debed-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="debed-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="debed-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
