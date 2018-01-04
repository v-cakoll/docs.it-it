---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25106bffe6d541a89c786035db3d3266d861fd5b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="d96c8-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="d96c8-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="d96c8-103">La transazione specificata per l'operazione indicata è stata completata a causa di un'eccezione di esecuzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="d96c8-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d96c8-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d96c8-104">Description</span></span>  
 <span data-ttu-id="d96c8-105">Traccia eseguita quando si verifica un errore durante un tentativo di completare la transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="d96c8-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="d96c8-106">Questo si verifica prima che venga inviata una replica o un errore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d96c8-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d96c8-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="d96c8-107">Troubleshooting</span></span>  
 <span data-ttu-id="d96c8-108">Cercare nel messaggio tracciato il messaggio dell'eccezione ed eventuali elementi eseguibili.</span><span class="sxs-lookup"><span data-stu-id="d96c8-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96c8-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d96c8-109">See Also</span></span>  
 [<span data-ttu-id="d96c8-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="d96c8-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="d96c8-111">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="d96c8-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="d96c8-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="d96c8-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
