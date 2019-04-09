---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 591e1a1dcb6746d79ff5eceba7e74e890f327354
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112658"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="e1074-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="e1074-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="e1074-103">La transazione specificata per l'operazione indicata è stata completata a causa di un'eccezione di esecuzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="e1074-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e1074-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1074-104">Description</span></span>  
 <span data-ttu-id="e1074-105">Traccia eseguita quando si verifica un errore durante un tentativo di completare la transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="e1074-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="e1074-106">Questo si verifica prima che venga inviata una replica o un errore al chiamante.</span><span class="sxs-lookup"><span data-stu-id="e1074-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="e1074-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e1074-107">Troubleshooting</span></span>  
 <span data-ttu-id="e1074-108">Cercare nel messaggio tracciato il messaggio dell'eccezione ed eventuali elementi eseguibili.</span><span class="sxs-lookup"><span data-stu-id="e1074-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1074-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1074-109">See also</span></span>

- [<span data-ttu-id="e1074-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="e1074-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="e1074-111">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="e1074-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e1074-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="e1074-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
