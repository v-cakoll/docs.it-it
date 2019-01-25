---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: bb7f6fcf95d1ff253fa0e2963610bee2b65ef3c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597112"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="28add-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="28add-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>
<span data-ttu-id="28add-103">Tentativo di invio di un messaggio Replay a un coordinatore che non risponde.</span><span class="sxs-lookup"><span data-stu-id="28add-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="28add-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="28add-104">Description</span></span>  
 <span data-ttu-id="28add-105">Viene tracciato se il gestore transazioni locale deve inviare nuovamente un messaggio Replay a un coordinatore superiore, poiché non ha ricevuto alcuna risposta entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="28add-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="28add-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="28add-106">Troubleshooting</span></span>  
 <span data-ttu-id="28add-107">Esaminare i potenziali problemi della rete o del prodotto che impediscono il recapito della risposta entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="28add-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="28add-108">La visualizzazione di numerosi messaggi di questo tipo può indicare problemi dell'infrastruttura o tempi di risposta eccessivamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="28add-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="28add-109">Entrambi i problemi ridurranno drasticamente la velocità effettiva delle transazioni all'interno del sistema.</span><span class="sxs-lookup"><span data-stu-id="28add-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28add-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28add-110">See also</span></span>
- [<span data-ttu-id="28add-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="28add-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="28add-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="28add-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="28add-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="28add-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
