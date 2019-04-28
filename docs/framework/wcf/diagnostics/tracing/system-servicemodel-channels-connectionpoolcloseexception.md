---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 3dd28276cd3a39497c0387f5b9d0adec23d07c37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666833"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="8d8bb-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="8d8bb-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="8d8bb-103">Si è verificata un'eccezione durante la chiusura delle connessioni in questo pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="8d8bb-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8d8bb-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d8bb-104">Description</span></span>  
 <span data-ttu-id="8d8bb-105">Questa traccia a livello di errore indica che si è verificato un errore durante la chiusura del pool di connessioni utilizzato dalla connessione di Windows Communication Foundation (WCF) della limitazione delle richieste di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8d8bb-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="8d8bb-106">Una possibile ragione è un chiusura non riuscita di una o più connessioni in pool all'interno di CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="8d8bb-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="8d8bb-107">Quando viene generata questa eccezione, tutte le connessioni rimanenti non chiuse all'interno di tale pool vengono interrotte; le connessioni non chiuse all'interno di altri pool vengono abbandonate.</span><span class="sxs-lookup"><span data-stu-id="8d8bb-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d8bb-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d8bb-108">See also</span></span>

- [<span data-ttu-id="8d8bb-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="8d8bb-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8d8bb-110">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="8d8bb-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8d8bb-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="8d8bb-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
