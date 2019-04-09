---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182195"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="6f663-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="6f663-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="6f663-103">Si è verificata un'eccezione durante la chiusura delle connessioni in questo pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="6f663-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6f663-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f663-104">Description</span></span>  
 <span data-ttu-id="6f663-105">Questa traccia a livello di errore indica che si è verificato un errore durante la chiusura del pool di connessioni utilizzato dalla connessione di Windows Communication Foundation (WCF) della limitazione delle richieste di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6f663-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="6f663-106">Una possibile ragione è un chiusura non riuscita di una o più connessioni in pool all'interno di CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="6f663-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="6f663-107">Quando viene generata questa eccezione, tutte le connessioni rimanenti non chiuse all'interno di tale pool vengono interrotte; le connessioni non chiuse all'interno di altri pool vengono abbandonate.</span><span class="sxs-lookup"><span data-stu-id="6f663-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f663-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f663-108">See also</span></span>

- [<span data-ttu-id="6f663-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="6f663-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6f663-110">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="6f663-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6f663-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6f663-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
