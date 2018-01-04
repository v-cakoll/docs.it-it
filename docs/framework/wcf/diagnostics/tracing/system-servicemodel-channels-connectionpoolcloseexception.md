---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7a134a60656c6ee237203b69e1bce40656f13d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="ead6d-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="ead6d-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="ead6d-103">Si è verificata un'eccezione durante la chiusura delle connessioni in questo pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="ead6d-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ead6d-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ead6d-104">Description</span></span>  
 <span data-ttu-id="ead6d-105">Questa analisi del livello di errore indica che si è verificato un errore durante la chiusura dei pool di connessioni utilizzati dalla funzionalità di pool di connessioni di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ead6d-105">This error level trace indicates that an error has occurred while closing the connection pools used by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]’s connection pooling feature.</span></span> <span data-ttu-id="ead6d-106">Una possibile ragione è un chiusura non riuscita di una o più connessioni in pool all'interno di CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="ead6d-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="ead6d-107">Quando viene generata questa eccezione, tutte le connessioni rimanenti non chiuse all'interno di tale pool vengono interrotte; le connessioni non chiuse all'interno di altri pool vengono abbandonate.</span><span class="sxs-lookup"><span data-stu-id="ead6d-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ead6d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ead6d-108">See Also</span></span>  
 [<span data-ttu-id="ead6d-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="ead6d-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ead6d-110">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="ead6d-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ead6d-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="ead6d-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
