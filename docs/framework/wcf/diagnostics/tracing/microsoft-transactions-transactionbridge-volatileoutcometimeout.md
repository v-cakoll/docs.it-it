---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: dd2a0b67ec140aa2e6fe1abad8e85c0206abd8ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579021"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="1562d-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="1562d-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="1562d-103">Il servizio del protocollo WS-AT è andato in timeout durante l'attesa di una risposta a un messaggio in uscita da parte di un partecipante volatile.</span><span class="sxs-lookup"><span data-stu-id="1562d-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="1562d-104">Il risultato della transazione può essere incerto se il partecipante risponde.</span><span class="sxs-lookup"><span data-stu-id="1562d-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1562d-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1562d-105">Description</span></span>  
 <span data-ttu-id="1562d-106">Viene tracciato quando un partecipante volatile ha deciso di eseguire il commit o di interrompere ma non ha risposto a un commit o a una richiesta di rollback entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="1562d-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1562d-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1562d-107">Troubleshooting</span></span>  
 <span data-ttu-id="1562d-108">Assicurarsi che tutti i partecipanti volatili siano in grado di rispondere entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="1562d-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="1562d-109">Il periodo di tempo predefinito è 180 secondi.</span><span class="sxs-lookup"><span data-stu-id="1562d-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="1562d-110">Se è insufficiente, aumentare il criterio del timer `VolatileOutcomeDelay` per WS-AT.</span><span class="sxs-lookup"><span data-stu-id="1562d-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1562d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1562d-111">See also</span></span>

- [<span data-ttu-id="1562d-112">Traccia</span><span class="sxs-lookup"><span data-stu-id="1562d-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="1562d-113">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="1562d-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1562d-114">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="1562d-114">Administration and Diagnostics</span></span>](../index.md)
