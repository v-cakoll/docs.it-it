---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: 9434f2f902a50a37fb3efee22fd3b18b33af9129
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138970"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="f192d-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="f192d-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="f192d-103">Il servizio del protocollo WS-AT ha ricevuto un messaggio Prepared o Replay da un partecipante volatile non riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f192d-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="f192d-104">Al partecipante è stato restituito un errore che dichiara che il risultato della transazione è in dubbio.</span><span class="sxs-lookup"><span data-stu-id="f192d-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f192d-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f192d-105">Description</span></span>  
 <span data-ttu-id="f192d-106">Viene tracciato quando il gestore transazioni locale riceve un messaggio Prepared o Replay da un elenco volatile che ha già dimenticato.</span><span class="sxs-lookup"><span data-stu-id="f192d-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f192d-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="f192d-107">Troubleshooting</span></span>  
 <span data-ttu-id="f192d-108">Analizzare le cause potenziali di ritardo dei messaggi provenienti dal partecipante volatile.</span><span class="sxs-lookup"><span data-stu-id="f192d-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f192d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f192d-109">See also</span></span>

- [<span data-ttu-id="f192d-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="f192d-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="f192d-111">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="f192d-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f192d-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="f192d-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
