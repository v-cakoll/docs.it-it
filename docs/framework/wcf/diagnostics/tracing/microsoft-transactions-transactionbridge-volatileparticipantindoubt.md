---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3b497231326c640b93b96500df39732104e0f0c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="609c0-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="609c0-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="609c0-103">Il servizio del protocollo WS-AT ha ricevuto un messaggio Prepared o Replay da un partecipante volatile non riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="609c0-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="609c0-104">Al partecipante è stato restituito un errore che dichiara che il risultato della transazione è in dubbio.</span><span class="sxs-lookup"><span data-stu-id="609c0-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="609c0-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="609c0-105">Description</span></span>  
 <span data-ttu-id="609c0-106">Viene tracciato quando il gestore transazioni locale riceve un messaggio Prepared o Replay da un elenco volatile che ha già dimenticato.</span><span class="sxs-lookup"><span data-stu-id="609c0-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="609c0-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="609c0-107">Troubleshooting</span></span>  
 <span data-ttu-id="609c0-108">Analizzare le cause potenziali di ritardo dei messaggi provenienti dal partecipante volatile.</span><span class="sxs-lookup"><span data-stu-id="609c0-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="609c0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="609c0-109">See Also</span></span>  
 [<span data-ttu-id="609c0-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="609c0-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="609c0-111">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="609c0-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="609c0-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="609c0-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
