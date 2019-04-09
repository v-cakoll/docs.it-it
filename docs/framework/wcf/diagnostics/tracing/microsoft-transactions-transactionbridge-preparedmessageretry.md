---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: d8acdb2f94e752860025ee2963aa78682b43b079
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216912"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="d7910-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="d7910-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>
<span data-ttu-id="d7910-103">Tentativo di invio di un messaggio Prepared a un coordinatore che non risponde.</span><span class="sxs-lookup"><span data-stu-id="d7910-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d7910-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7910-104">Description</span></span>  
 <span data-ttu-id="d7910-105">Viene tracciato se il gestore transazioni locale deve inviare nuovamente un messaggio Pepared a un coordinatore superiore poiché non viene ricevuta alcuna risposta entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d7910-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d7910-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="d7910-106">Troubleshooting</span></span>  
 <span data-ttu-id="d7910-107">Esaminare i potenziali problemi della rete o del prodotto che impediscono il recapito della risposta entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="d7910-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="d7910-108">La visualizzazione di numerosi messaggi di questo tipo può indicare problemi dell'infrastruttura o tempi di risposta eccessivamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="d7910-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="d7910-109">Entrambi i problemi ridurranno drasticamente la velocità effettiva delle transazioni all'interno del sistema.</span><span class="sxs-lookup"><span data-stu-id="d7910-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7910-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7910-110">See also</span></span>

- [<span data-ttu-id="d7910-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="d7910-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d7910-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="d7910-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d7910-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="d7910-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
