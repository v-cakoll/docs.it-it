---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 7f37cb5d9ee3d2d9d56519f785388f278b3333b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997880"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="2f52c-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="2f52c-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="2f52c-103">La macchina a stati dell'integrazione di un partecipante è passata allo stato di operazione completata.</span><span class="sxs-lookup"><span data-stu-id="2f52c-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2f52c-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f52c-104">Description</span></span>  
 <span data-ttu-id="2f52c-105">Traccia eseguita quando l'elaborazione 2PC dell'integrazione di un partecipante subordinato è stata completata.</span><span class="sxs-lookup"><span data-stu-id="2f52c-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="2f52c-106">Il risultato dell'integrazione può essere "Committed" o "Aborted", a indicare rispettivamente il commit o l'interruzione di una transazione.</span><span class="sxs-lookup"><span data-stu-id="2f52c-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="2f52c-107">Questa traccia viene inoltre eseguita se un partecipante vota "ReadOnly" durante la fase di preparazione.</span><span class="sxs-lookup"><span data-stu-id="2f52c-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f52c-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f52c-108">See also</span></span>

- [<span data-ttu-id="2f52c-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="2f52c-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2f52c-110">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="2f52c-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2f52c-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="2f52c-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
