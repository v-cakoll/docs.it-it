---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: e56a9ed1d837af27d481282e0e106d537ec41ee3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997750"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="3c574-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="3c574-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="3c574-103">Servizio del protocollo WS-AT: impossibile registrare un partecipante per un protocollo di controllo.</span><span class="sxs-lookup"><span data-stu-id="3c574-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3c574-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c574-104">Description</span></span>  
 <span data-ttu-id="3c574-105">Viene tracciato se MSDTC rileva una richiesta di registrazione non valida.</span><span class="sxs-lookup"><span data-stu-id="3c574-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="3c574-106">Può essere causato da più richieste di registrazione di completamento e da errori interni.</span><span class="sxs-lookup"><span data-stu-id="3c574-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3c574-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="3c574-107">Troubleshooting</span></span>  
 <span data-ttu-id="3c574-108">Non tentare la registrazione di completamento più di una volta.</span><span class="sxs-lookup"><span data-stu-id="3c574-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="3c574-109">Controllare inoltre la stringa di stato all'interno del messaggio di traccia per determinare se esiste un elemento processabile.</span><span class="sxs-lookup"><span data-stu-id="3c574-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c574-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c574-110">See also</span></span>

- [<span data-ttu-id="3c574-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="3c574-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="3c574-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="3c574-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3c574-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="3c574-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
