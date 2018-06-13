---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: ba35f948143aff3de575e966aaec87f32f6f14b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473776"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="8654b-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="8654b-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>
<span data-ttu-id="8654b-103">Tentativo di invio di un messaggio Prepared a un coordinatore che non risponde.</span><span class="sxs-lookup"><span data-stu-id="8654b-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8654b-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8654b-104">Description</span></span>  
 <span data-ttu-id="8654b-105">Viene tracciato se il gestore transazioni locale deve inviare nuovamente un messaggio Pepared a un coordinatore superiore poiché non viene ricevuta alcuna risposta entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8654b-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8654b-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="8654b-106">Troubleshooting</span></span>  
 <span data-ttu-id="8654b-107">Esaminare i potenziali problemi della rete o del prodotto che impediscono il recapito della risposta entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="8654b-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="8654b-108">La visualizzazione di numerosi messaggi di questo tipo può indicare problemi dell'infrastruttura o tempi di risposta eccessivamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="8654b-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="8654b-109">Entrambi i problemi ridurranno drasticamente la velocità effettiva delle transazioni all'interno del sistema.</span><span class="sxs-lookup"><span data-stu-id="8654b-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8654b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8654b-110">See Also</span></span>  
 [<span data-ttu-id="8654b-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="8654b-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8654b-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="8654b-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8654b-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="8654b-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
