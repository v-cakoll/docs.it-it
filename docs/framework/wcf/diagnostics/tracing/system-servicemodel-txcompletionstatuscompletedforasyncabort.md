---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3595b98ca8c78fb6bdf86a08dcd56b37a4770405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="61a60-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="61a60-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="61a60-103">La transazione specificata per l'operazione indicata è stata completata a causa di un'interruzione asincrona.</span><span class="sxs-lookup"><span data-stu-id="61a60-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="61a60-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61a60-104">Description</span></span>  
 <span data-ttu-id="61a60-105">La transazione corrente è stata interrotta a causa di un altro partecipante che vota per l'interruzione, al verificarsi del timeout o di un altro errore all'interno del partecipante a una transazione.</span><span class="sxs-lookup"><span data-stu-id="61a60-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="61a60-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="61a60-106">Troubleshooting</span></span>  
 <span data-ttu-id="61a60-107">Se si tratta di un'interruzione imprevista, esaminare tutti i registri eventi di sistema per determinare il motivo effettivo dell'interruzione.</span><span class="sxs-lookup"><span data-stu-id="61a60-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a60-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61a60-108">See Also</span></span>  
 [<span data-ttu-id="61a60-109">Traccia</span><span class="sxs-lookup"><span data-stu-id="61a60-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="61a60-110">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="61a60-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="61a60-111">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="61a60-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
