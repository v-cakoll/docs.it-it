---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 85b8cc4e5044cc7c87ea784e09c160cc527dddaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473532"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="c7a79-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="c7a79-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="c7a79-103">La macchina a stati dell'integrazione di un partecipante è passata allo stato di operazione completata.</span><span class="sxs-lookup"><span data-stu-id="c7a79-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c7a79-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7a79-104">Description</span></span>  
 <span data-ttu-id="c7a79-105">Traccia eseguita quando l'elaborazione 2PC dell'integrazione di un partecipante subordinato è stata completata.</span><span class="sxs-lookup"><span data-stu-id="c7a79-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="c7a79-106">Il risultato dell'integrazione può essere "Committed" o "Aborted", a indicare rispettivamente il commit o l'interruzione di una transazione.</span><span class="sxs-lookup"><span data-stu-id="c7a79-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="c7a79-107">Questa traccia viene inoltre eseguita se un partecipante vota "ReadOnly" durante la fase di preparazione.</span><span class="sxs-lookup"><span data-stu-id="c7a79-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a79-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7a79-108">See Also</span></span>  
 [<span data-ttu-id="c7a79-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="c7a79-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="c7a79-110">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="c7a79-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="c7a79-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c7a79-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
