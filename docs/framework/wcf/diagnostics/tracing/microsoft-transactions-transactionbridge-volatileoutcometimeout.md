---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: 22992b4dfad4b4867adda0fcbbd8ecc5eb67d87e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997607"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="0eb3c-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="0eb3c-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="0eb3c-103">Il servizio del protocollo WS-AT è andato in timeout durante l'attesa di una risposta a un messaggio in uscita da parte di un partecipante volatile.</span><span class="sxs-lookup"><span data-stu-id="0eb3c-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="0eb3c-104">Il risultato della transazione può essere incerto se il partecipante risponde.</span><span class="sxs-lookup"><span data-stu-id="0eb3c-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0eb3c-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0eb3c-105">Description</span></span>  
 <span data-ttu-id="0eb3c-106">Viene tracciato quando un partecipante volatile ha deciso di eseguire il commit o di interrompere ma non ha risposto a un commit o a una richiesta di rollback entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="0eb3c-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0eb3c-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="0eb3c-107">Troubleshooting</span></span>  
 <span data-ttu-id="0eb3c-108">Assicurarsi che tutti i partecipanti volatili siano in grado di rispondere entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="0eb3c-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="0eb3c-109">Il periodo di tempo predefinito è 180 secondi.</span><span class="sxs-lookup"><span data-stu-id="0eb3c-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="0eb3c-110">Se è insufficiente, aumentare il criterio del timer `VolatileOutcomeDelay` per WS-AT.</span><span class="sxs-lookup"><span data-stu-id="0eb3c-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb3c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eb3c-111">See also</span></span>

- [<span data-ttu-id="0eb3c-112">Traccia</span><span class="sxs-lookup"><span data-stu-id="0eb3c-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="0eb3c-113">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="0eb3c-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0eb3c-114">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="0eb3c-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
