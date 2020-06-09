---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 0652b3b76c155431b68c5ee0dc8f83977f9845a5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594361"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="09c24-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="09c24-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="09c24-103">La macchina a stati dell'integrazione di un partecipante è passata allo stato di operazione completata.</span><span class="sxs-lookup"><span data-stu-id="09c24-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="09c24-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="09c24-104">Description</span></span>  
 <span data-ttu-id="09c24-105">Traccia eseguita quando l'elaborazione 2PC dell'integrazione di un partecipante subordinato è stata completata.</span><span class="sxs-lookup"><span data-stu-id="09c24-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="09c24-106">Il risultato dell'integrazione può essere "Committed" o "Aborted", a indicare rispettivamente il commit o l'interruzione di una transazione.</span><span class="sxs-lookup"><span data-stu-id="09c24-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="09c24-107">Questa traccia viene inoltre eseguita se un partecipante vota "ReadOnly" durante la fase di preparazione.</span><span class="sxs-lookup"><span data-stu-id="09c24-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c24-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09c24-108">See also</span></span>

- [<span data-ttu-id="09c24-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="09c24-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="09c24-110">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="09c24-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="09c24-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="09c24-111">Administration and Diagnostics</span></span>](../index.md)
