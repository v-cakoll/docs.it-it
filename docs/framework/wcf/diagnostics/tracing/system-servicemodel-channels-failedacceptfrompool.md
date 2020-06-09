---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: 5bfa31d0eaf3b00017512eddc60bfa99eda619e3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84582582"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="f8f40-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="f8f40-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="f8f40-103">Tentativo di riutilizzare una connessione in pool non riuscito.</span><span class="sxs-lookup"><span data-stu-id="f8f40-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="f8f40-104">Verrà effettuato un altro tentativo entro il periodo di timeout specificato.</span><span class="sxs-lookup"><span data-stu-id="f8f40-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f8f40-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8f40-105">Description</span></span>  
 <span data-ttu-id="f8f40-106">Questa traccia informativa indica che si è verificato un errore durante il tentativo di riutilizzare una connessione in pool.</span><span class="sxs-lookup"><span data-stu-id="f8f40-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="f8f40-107">Ciò è dovuto al fatto che la connessione in pool non era compatibile o pronta oppure era ancora attiva.</span><span class="sxs-lookup"><span data-stu-id="f8f40-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="f8f40-108">Verranno eseguiti ulteriori tentativi di riutilizzo della connessione in pool entro un determinato periodo di tempo. Nel caso in cui non verranno trovate connessioni utilizzabili, verrà creata una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="f8f40-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f40-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8f40-109">See also</span></span>

- [<span data-ttu-id="f8f40-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="f8f40-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="f8f40-111">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="f8f40-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f8f40-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="f8f40-112">Administration and Diagnostics</span></span>](../index.md)
