---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ed8a5718bb4a3a070f39a0dca35e2fdbc78f1b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="bfc0d-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="bfc0d-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="bfc0d-103">Il modulo PeerMaintainer sta eseguendo un'operazione specifica (i dettagli sono contenuti nel corpo del messaggio di traccia).</span><span class="sxs-lookup"><span data-stu-id="bfc0d-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="bfc0d-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfc0d-104">Description</span></span>  
 <span data-ttu-id="bfc0d-105">Questa traccia si verifica durante varie operazioni PeerMaintainer.</span><span class="sxs-lookup"><span data-stu-id="bfc0d-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="bfc0d-106">PeerMaintainer è un componente interno di PeerNode.</span><span class="sxs-lookup"><span data-stu-id="bfc0d-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="bfc0d-107">Ogni minuto o ogni 32 messaggi ricevuti, invia un messaggio LinkUtility ai router adiacenti con le statistiche sulla quantità di messaggi scambiati e su quanti di essi sono utili (non duplicati, non manomessi).</span><span class="sxs-lookup"><span data-stu-id="bfc0d-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="bfc0d-108">Ciò consente di determinare l'utilità di collegamento di un determinato router adiacente.</span><span class="sxs-lookup"><span data-stu-id="bfc0d-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="bfc0d-109">Ogni cinque minuti circa, il componente Maintener verifica l'integrità delle connessioni al router adiacente.</span><span class="sxs-lookup"><span data-stu-id="bfc0d-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="bfc0d-110">Se il numero di connessioni al router adiacente supera il valore ideale, il componente elimina le connessioni meno utili.</span><span class="sxs-lookup"><span data-stu-id="bfc0d-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="bfc0d-111">Se il numero di connessioni non è sufficiente, il componente ne acquisisce di nuove.</span><span class="sxs-lookup"><span data-stu-id="bfc0d-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc0d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfc0d-112">See Also</span></span>  
 [<span data-ttu-id="bfc0d-113">Traccia</span><span class="sxs-lookup"><span data-stu-id="bfc0d-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="bfc0d-114">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="bfc0d-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="bfc0d-115">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="bfc0d-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
