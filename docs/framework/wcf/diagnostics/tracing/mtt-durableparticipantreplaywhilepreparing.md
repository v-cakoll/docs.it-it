---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: fe88e70ab4955305d78baa1158cd73a93ba2ed2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33476320"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="84d76-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="84d76-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="84d76-103">Il servizio del protocollo WS-AT ha ricevuto un messaggio Replay da un partecipante durevole che non ha risposto a Prepare.</span><span class="sxs-lookup"><span data-stu-id="84d76-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="84d76-104">Di conseguenza la transazione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="84d76-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="84d76-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84d76-105">Description</span></span>  
 <span data-ttu-id="84d76-106">Viene tracciato se viene ricevuto un messaggio Replay mentre un partecipante durevole è ancora in preparazione.</span><span class="sxs-lookup"><span data-stu-id="84d76-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="84d76-107">Si tratta di un messaggio non valido per lo stato e la transazione sarà interrotta.</span><span class="sxs-lookup"><span data-stu-id="84d76-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="84d76-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="84d76-108">Troubleshooting</span></span>  
 <span data-ttu-id="84d76-109">La ricezione di questo errore può indicare che un partecipante durevole (tra cui un gestore transazioni subordinato) ha effettuato il ripristino a seguito di un errore, ci sono tuttavia dubbi sul risultato della transazione e ne viene richiesto lo stato.</span><span class="sxs-lookup"><span data-stu-id="84d76-109">Receiving this error can indiate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure, however it is unsure of the transaction outcome and request its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d76-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84d76-110">See Also</span></span>  
 [<span data-ttu-id="84d76-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="84d76-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="84d76-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="84d76-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="84d76-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="84d76-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
