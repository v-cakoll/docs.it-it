---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 0a312d192546655dc327667c00f4f2bbc0c15fdb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602044"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="c01f0-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="c01f0-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="c01f0-103">Si è verificata un'eccezione durante la chiusura delle connessioni in questo pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="c01f0-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c01f0-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c01f0-104">Description</span></span>  
 <span data-ttu-id="c01f0-105">Questa traccia a livello di errore indica che si è verificato un errore durante la chiusura dei pool di connessioni utilizzati dalla funzionalità di pool di connessioni di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c01f0-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="c01f0-106">Una possibile ragione è un chiusura non riuscita di una o più connessioni in pool all'interno di CloseTimeout.</span><span class="sxs-lookup"><span data-stu-id="c01f0-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="c01f0-107">Quando viene generata questa eccezione, tutte le connessioni rimanenti non chiuse all'interno di tale pool vengono interrotte; le connessioni non chiuse all'interno di altri pool vengono abbandonate.</span><span class="sxs-lookup"><span data-stu-id="c01f0-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c01f0-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c01f0-108">See also</span></span>

- [<span data-ttu-id="c01f0-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="c01f0-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="c01f0-110">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="c01f0-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c01f0-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c01f0-111">Administration and Diagnostics</span></span>](../index.md)
