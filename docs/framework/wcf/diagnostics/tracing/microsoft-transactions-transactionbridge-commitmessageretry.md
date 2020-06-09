---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: f37bc252e12aef94d77c0745d36b5c8232a169eb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599737"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="bea84-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="bea84-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>
<span data-ttu-id="bea84-103">Tentativo di invio di un messaggio Commit a un partecipante che non risponde.</span><span class="sxs-lookup"><span data-stu-id="bea84-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bea84-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bea84-104">Description</span></span>  
 <span data-ttu-id="bea84-105">Viene tracciato se il gestore transazioni locale deve inviare nuovamente un messaggio Commit a un partecipante subordinato perché non ha ricevuto una risposta entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="bea84-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="bea84-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="bea84-106">Troubleshooting</span></span>  
 <span data-ttu-id="bea84-107">Esaminare i potenziali problemi della rete o del prodotto che impediscono il recapito della risposta entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="bea84-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="bea84-108">La visualizzazione di numerosi messaggi di questo tipo può indicare problemi dell'infrastruttura o tempi di risposta eccessivamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="bea84-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="bea84-109">Entrambi i problemi ridurranno drasticamente la velocità effettiva delle transazioni all'interno del sistema.</span><span class="sxs-lookup"><span data-stu-id="bea84-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea84-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bea84-110">See also</span></span>

- [<span data-ttu-id="bea84-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="bea84-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="bea84-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="bea84-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="bea84-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="bea84-113">Administration and Diagnostics</span></span>](../index.md)
