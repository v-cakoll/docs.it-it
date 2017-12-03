---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 339ba8df7e782281fcec962ff6c6f01988122b3a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="a17a0-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="a17a0-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="a17a0-103">Tentativo di riutilizzare una connessione in pool non riuscito.</span><span class="sxs-lookup"><span data-stu-id="a17a0-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="a17a0-104">Verrà effettuato un altro tentativo entro il periodo di timeout specificato.</span><span class="sxs-lookup"><span data-stu-id="a17a0-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a17a0-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a17a0-105">Description</span></span>  
 <span data-ttu-id="a17a0-106">Questa traccia informativa indica che si è verificato un errore durante il tentativo di riutilizzare una connessione in pool.</span><span class="sxs-lookup"><span data-stu-id="a17a0-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="a17a0-107">Ciò è dovuto al fatto che la connessione in pool non era compatibile o pronta oppure era ancora attiva.</span><span class="sxs-lookup"><span data-stu-id="a17a0-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="a17a0-108">Verranno eseguiti ulteriori tentativi di riutilizzo della connessione in pool entro un determinato periodo di tempo. Nel caso in cui non verranno trovate connessioni utilizzabili, verrà creata una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="a17a0-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a17a0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a17a0-109">See Also</span></span>  
 [<span data-ttu-id="a17a0-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="a17a0-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="a17a0-111">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a17a0-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="a17a0-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="a17a0-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
