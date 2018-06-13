---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.date: 03/30/2017
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
ms.openlocfilehash: affa647b30dbeb9237e4c20ebb441645eda94276
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474324"
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="d4606-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="d4606-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>
<span data-ttu-id="d4606-103">Tentativo di invio di un messaggio Prepare a un partecipante che non risponde.</span><span class="sxs-lookup"><span data-stu-id="d4606-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d4606-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4606-104">Description</span></span>  
 <span data-ttu-id="d4606-105">Viene tracciato se il gestore transazioni locale deve inviare nuovamente un messaggio Prepare a un partecipante subordinato poiché non viene ricevuta alcuna risposta entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d4606-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d4606-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="d4606-106">Troubleshooting</span></span>  
 <span data-ttu-id="d4606-107">Esaminare i potenziali problemi della rete o del prodotto che impediscono il recapito della risposta entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="d4606-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="d4606-108">La visualizzazione di numerosi messaggi di questo tipo può indicare problemi dell'infrastruttura o tempi di risposta eccessivamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="d4606-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="d4606-109">Entrambi i problemi possono ridurre drasticamente la velocità effettiva delle transazioni all'interno del sistema.</span><span class="sxs-lookup"><span data-stu-id="d4606-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4606-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4606-110">See Also</span></span>  
 [<span data-ttu-id="d4606-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="d4606-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="d4606-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="d4606-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="d4606-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="d4606-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
