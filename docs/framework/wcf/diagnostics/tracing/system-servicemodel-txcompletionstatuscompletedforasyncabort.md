---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: f84cc9336d6cce7d8c477a1feb6caf45b0662177
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188474"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="54394-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="54394-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="54394-103">La transazione specificata per l'operazione indicata è stata completata a causa di un'interruzione asincrona.</span><span class="sxs-lookup"><span data-stu-id="54394-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="54394-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54394-104">Description</span></span>  
 <span data-ttu-id="54394-105">La transazione corrente è stata interrotta a causa di un altro partecipante che vota per l'interruzione, al verificarsi del timeout o di un altro errore all'interno del partecipante a una transazione.</span><span class="sxs-lookup"><span data-stu-id="54394-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="54394-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="54394-106">Troubleshooting</span></span>  
 <span data-ttu-id="54394-107">Se si tratta di un'interruzione imprevista, esaminare tutti i registri eventi di sistema per determinare il motivo effettivo dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="54394-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54394-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54394-108">See also</span></span>

- [<span data-ttu-id="54394-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="54394-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="54394-110">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="54394-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="54394-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="54394-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
