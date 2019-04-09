---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: 0c9e79709f5929e1fa123a8d1695ca720046e9e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190873"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="987ab-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="987ab-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>
<span data-ttu-id="987ab-103">Tentativo di invio di un messaggio Replay a un coordinatore che non risponde.</span><span class="sxs-lookup"><span data-stu-id="987ab-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="987ab-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="987ab-104">Description</span></span>  
 <span data-ttu-id="987ab-105">Viene tracciato se il gestore transazioni locale deve inviare nuovamente un messaggio Replay a un coordinatore superiore, poiché non ha ricevuto alcuna risposta entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="987ab-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="987ab-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="987ab-106">Troubleshooting</span></span>  
 <span data-ttu-id="987ab-107">Esaminare i potenziali problemi della rete o del prodotto che impediscono il recapito della risposta entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="987ab-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="987ab-108">La visualizzazione di numerosi messaggi di questo tipo può indicare problemi dell'infrastruttura o tempi di risposta eccessivamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="987ab-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="987ab-109">Entrambi i problemi ridurranno drasticamente la velocità effettiva delle transazioni all'interno del sistema.</span><span class="sxs-lookup"><span data-stu-id="987ab-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987ab-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="987ab-110">See also</span></span>

- [<span data-ttu-id="987ab-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="987ab-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="987ab-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="987ab-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="987ab-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="987ab-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
