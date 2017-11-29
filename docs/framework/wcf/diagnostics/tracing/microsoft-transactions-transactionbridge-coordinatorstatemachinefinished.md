---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c9a456e668560cb2172de80295b731a6103aa7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="f54dd-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="f54dd-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="f54dd-103">Il computer di stato per l'integrazione di un coordinatore è in stato di operazione completata.</span><span class="sxs-lookup"><span data-stu-id="f54dd-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f54dd-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f54dd-104">Description</span></span>  
 <span data-ttu-id="f54dd-105">Traccia eseguita quando il gestore transazioni locale ritiene che l'integrazione di un coordinatore superiore abbia completato l'elaborazione 2pc.</span><span class="sxs-lookup"><span data-stu-id="f54dd-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="f54dd-106">Il risultato dell'integrazione può essere Committed, Aborted o Forgotten.</span><span class="sxs-lookup"><span data-stu-id="f54dd-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="f54dd-107">Questa traccia viene inoltre eseguita se il gestore transazioni locale vota ReadOnly durante la fase di preparazione.</span><span class="sxs-lookup"><span data-stu-id="f54dd-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f54dd-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f54dd-108">See Also</span></span>  
 [<span data-ttu-id="f54dd-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="f54dd-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f54dd-110">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="f54dd-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f54dd-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="f54dd-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
