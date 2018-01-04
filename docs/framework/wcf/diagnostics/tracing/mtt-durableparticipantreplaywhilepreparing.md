---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 375bb5902640ba0816217aec161834d79e9765ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="274a7-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="274a7-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="274a7-103">Il servizio del protocollo WS-AT ha ricevuto un messaggio Replay da un partecipante durevole che non ha risposto a Prepare.</span><span class="sxs-lookup"><span data-stu-id="274a7-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="274a7-104">Di conseguenza la transazione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="274a7-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="274a7-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="274a7-105">Description</span></span>  
 <span data-ttu-id="274a7-106">Viene tracciato se viene ricevuto un messaggio Replay mentre un partecipante durevole è ancora in preparazione.</span><span class="sxs-lookup"><span data-stu-id="274a7-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="274a7-107">Si tratta di un messaggio non valido per lo stato e la transazione sarà interrotta.</span><span class="sxs-lookup"><span data-stu-id="274a7-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="274a7-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="274a7-108">Troubleshooting</span></span>  
 <span data-ttu-id="274a7-109">La ricezione di questo errore può indicare che un partecipante durevole (tra cui un gestore transazioni subordinato) ha effettuato il ripristino a seguito di un errore, ci sono tuttavia dubbi sul risultato della transazione e ne viene richiesto lo stato.</span><span class="sxs-lookup"><span data-stu-id="274a7-109">Receiving this error can indiate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure, however it is unsure of the transaction outcome and request its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="274a7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="274a7-110">See Also</span></span>  
 [<span data-ttu-id="274a7-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="274a7-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="274a7-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="274a7-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="274a7-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="274a7-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
