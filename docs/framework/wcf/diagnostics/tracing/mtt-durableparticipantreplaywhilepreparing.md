---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 31fb8d466c76c7490aa80dfcab089332af4036a2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589132"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="9ec27-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="9ec27-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="9ec27-103">Il servizio del protocollo WS-AT ha ricevuto un messaggio Replay da un partecipante durevole che non ha risposto a Prepare.</span><span class="sxs-lookup"><span data-stu-id="9ec27-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="9ec27-104">Di conseguenza la transazione è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="9ec27-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9ec27-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ec27-105">Description</span></span>  
 <span data-ttu-id="9ec27-106">Viene tracciato se viene ricevuto un messaggio Replay mentre un partecipante durevole è ancora in preparazione.</span><span class="sxs-lookup"><span data-stu-id="9ec27-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="9ec27-107">Si tratta di un messaggio non valido per lo stato e la transazione sarà interrotta.</span><span class="sxs-lookup"><span data-stu-id="9ec27-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="9ec27-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9ec27-108">Troubleshooting</span></span>

<span data-ttu-id="9ec27-109">La ricezione di questo errore può indicare che un partecipante durevole (incluso TransactionManagers subordinato) è stato recuperato dall'errore; Tuttavia, non è sicuro del risultato della transazione e ne richiede lo stato.</span><span class="sxs-lookup"><span data-stu-id="9ec27-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec27-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ec27-110">See also</span></span>

- [<span data-ttu-id="9ec27-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="9ec27-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="9ec27-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="9ec27-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9ec27-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="9ec27-113">Administration and Diagnostics</span></span>](../index.md)
