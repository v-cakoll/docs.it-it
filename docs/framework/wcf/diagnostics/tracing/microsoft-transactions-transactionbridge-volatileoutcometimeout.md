---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1992a209bb58c0a0d6f181eb2f1ec546d50372ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="564b4-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="564b4-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="564b4-103">Il servizio del protocollo WS-AT è andato in timeout durante l'attesa di una risposta a un messaggio in uscita da parte di un partecipante volatile.</span><span class="sxs-lookup"><span data-stu-id="564b4-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="564b4-104">Il risultato della transazione può essere incerto se il partecipante risponde.</span><span class="sxs-lookup"><span data-stu-id="564b4-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="564b4-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="564b4-105">Description</span></span>  
 <span data-ttu-id="564b4-106">Viene tracciato quando un partecipante volatile ha deciso di eseguire il commit o di interrompere ma non ha risposto a un commit o a una richiesta di rollback entro un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="564b4-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="564b4-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="564b4-107">Troubleshooting</span></span>  
 <span data-ttu-id="564b4-108">Assicurarsi che tutti i partecipanti volatili siano in grado di rispondere entro il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="564b4-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="564b4-109">Il periodo di tempo predefinito è 180 secondi.</span><span class="sxs-lookup"><span data-stu-id="564b4-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="564b4-110">Se è insufficiente, aumentare il criterio del timer `VolatileOutcomeDelay` per WS-AT.</span><span class="sxs-lookup"><span data-stu-id="564b4-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564b4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="564b4-111">See Also</span></span>  
 [<span data-ttu-id="564b4-112">Traccia</span><span class="sxs-lookup"><span data-stu-id="564b4-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="564b4-113">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="564b4-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="564b4-114">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="564b4-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
