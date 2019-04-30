---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: f84cc9336d6cce7d8c477a1feb6caf45b0662177
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996931"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="11178-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="11178-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="11178-103">La transazione specificata per l'operazione indicata è stata completata a causa di un'interruzione asincrona.</span><span class="sxs-lookup"><span data-stu-id="11178-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="11178-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11178-104">Description</span></span>  
 <span data-ttu-id="11178-105">La transazione corrente è stata interrotta a causa di un altro partecipante che vota per l'interruzione, al verificarsi del timeout o di un altro errore all'interno del partecipante a una transazione.</span><span class="sxs-lookup"><span data-stu-id="11178-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="11178-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="11178-106">Troubleshooting</span></span>  
 <span data-ttu-id="11178-107">Se si tratta di un'interruzione imprevista, esaminare tutti i registri eventi di sistema per determinare il motivo effettivo dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="11178-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11178-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11178-108">See also</span></span>

- [<span data-ttu-id="11178-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="11178-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="11178-110">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="11178-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="11178-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="11178-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
