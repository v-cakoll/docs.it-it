---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: 50dd3070525bbc6d36956b25dee587ec7864d3ff
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594309"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="278ad-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="278ad-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>
<span data-ttu-id="278ad-103">Tentativo di invio di un messaggio Prepared a un coordinatore che non risponde.</span><span class="sxs-lookup"><span data-stu-id="278ad-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="278ad-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="278ad-104">Description</span></span>  
 <span data-ttu-id="278ad-105">Viene tracciato se il gestore transazioni locale deve inviare nuovamente un messaggio Pepared a un coordinatore superiore poiché non viene ricevuta alcuna risposta entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="278ad-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="278ad-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="278ad-106">Troubleshooting</span></span>  
 <span data-ttu-id="278ad-107">Esaminare i potenziali problemi della rete o del prodotto che impediscono il recapito della risposta entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="278ad-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="278ad-108">La visualizzazione di numerosi messaggi di questo tipo può indicare problemi dell'infrastruttura o tempi di risposta eccessivamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="278ad-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="278ad-109">Entrambi i problemi ridurranno drasticamente la velocità effettiva delle transazioni all'interno del sistema.</span><span class="sxs-lookup"><span data-stu-id="278ad-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="278ad-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="278ad-110">See also</span></span>

- [<span data-ttu-id="278ad-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="278ad-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="278ad-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="278ad-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="278ad-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="278ad-113">Administration and Diagnostics</span></span>](../index.md)
