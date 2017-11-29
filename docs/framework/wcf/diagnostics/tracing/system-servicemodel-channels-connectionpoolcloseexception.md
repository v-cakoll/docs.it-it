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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0ea98388efe14ac0d18a94ec056a441096a4d7c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="ff1c3-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="ff1c3-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="ff1c3-103">Si è verificata un'eccezione durante la chiusura delle connessioni in questo pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="ff1c3-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ff1c3-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff1c3-104">Description</span></span>  
 <span data-ttu-id="ff1c3-105">Questa analisi del livello di errore indica che si è verificato un errore durante la chiusura dei pool di connessioni utilizzati dalla funzionalità di pool di connessioni di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff1c3-105">This error level trace indicates that an error has occurred while closing the connection pools used by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]’s connection pooling feature.</span></span> <span data-ttu-id="ff1c3-106">Una possibile ragione è un chiusura non riuscita di una o più connessioni in pool all'interno di CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="ff1c3-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="ff1c3-107">Quando viene generata questa eccezione, tutte le connessioni rimanenti non chiuse all'interno di tale pool vengono interrotte; le connessioni non chiuse all'interno di altri pool vengono abbandonate.</span><span class="sxs-lookup"><span data-stu-id="ff1c3-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff1c3-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff1c3-108">See Also</span></span>  
 [<span data-ttu-id="ff1c3-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="ff1c3-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ff1c3-110">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="ff1c3-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ff1c3-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="ff1c3-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
