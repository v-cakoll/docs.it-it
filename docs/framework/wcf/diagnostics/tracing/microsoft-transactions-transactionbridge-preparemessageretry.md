---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: 02e275fa212128c65beda4bc3703949e75ea5092
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220890"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="fa874-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="fa874-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>
<span data-ttu-id="fa874-103">Tentativo di invio di un messaggio Prepare a un partecipante che non risponde.</span><span class="sxs-lookup"><span data-stu-id="fa874-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fa874-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa874-104">Description</span></span>  
 <span data-ttu-id="fa874-105">Viene tracciato se il gestore transazioni locale deve inviare nuovamente un messaggio Prepare a un partecipante subordinato poiché non viene ricevuta alcuna risposta entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="fa874-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="fa874-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="fa874-106">Troubleshooting</span></span>  
 <span data-ttu-id="fa874-107">Esaminare i potenziali problemi della rete o del prodotto che impediscono il recapito della risposta entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="fa874-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="fa874-108">La visualizzazione di numerosi messaggi di questo tipo può indicare problemi dell'infrastruttura o tempi di risposta eccessivamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="fa874-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="fa874-109">Entrambi i problemi possono ridurre drasticamente la velocità effettiva delle transazioni all'interno del sistema.</span><span class="sxs-lookup"><span data-stu-id="fa874-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa874-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa874-110">See also</span></span>

- [<span data-ttu-id="fa874-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="fa874-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="fa874-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="fa874-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="fa874-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="fa874-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
