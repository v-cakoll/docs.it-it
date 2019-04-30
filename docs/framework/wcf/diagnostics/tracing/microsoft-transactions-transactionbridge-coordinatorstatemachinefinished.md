---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: bffaed4976d82202eaea9ce50f6d389548fdabfd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998010"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="08f3b-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="08f3b-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="08f3b-103">Il computer di stato per l'integrazione di un coordinatore è in stato di operazione completata.</span><span class="sxs-lookup"><span data-stu-id="08f3b-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="08f3b-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08f3b-104">Description</span></span>  
 <span data-ttu-id="08f3b-105">Traccia eseguita quando il gestore transazioni locale ritiene che l'integrazione di un coordinatore superiore abbia completato l'elaborazione 2pc.</span><span class="sxs-lookup"><span data-stu-id="08f3b-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="08f3b-106">Il risultato dell'integrazione può essere Committed, Aborted o Forgotten.</span><span class="sxs-lookup"><span data-stu-id="08f3b-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="08f3b-107">Questa traccia viene inoltre eseguita se il gestore transazioni locale vota ReadOnly durante la fase di preparazione.</span><span class="sxs-lookup"><span data-stu-id="08f3b-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f3b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08f3b-108">See also</span></span>

- [<span data-ttu-id="08f3b-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="08f3b-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="08f3b-110">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="08f3b-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="08f3b-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="08f3b-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
