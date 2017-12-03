---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c0e688e1f24171494b4adaae964ac1fc2be2309
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="769d3-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="769d3-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="769d3-103">È impossibile completare la negoziazione del protocollo OleTransactions per il contesto di coordinamento specificato.</span><span class="sxs-lookup"><span data-stu-id="769d3-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="769d3-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="769d3-104">Description</span></span>  
 <span data-ttu-id="769d3-105">Viene tracciato quando una transazione in ingresso con informazioni OleTx non è in grado di utilizzare le informazioni OleTx allegate e utilizzerà pertanto WS-AT.</span><span class="sxs-lookup"><span data-stu-id="769d3-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="769d3-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="769d3-106">Troubleshooting</span></span>  
 <span data-ttu-id="769d3-107">Indica un problema potenziale con la comunicazione RPC MSDTC tra i computer.</span><span class="sxs-lookup"><span data-stu-id="769d3-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="769d3-108">Se il registro contiene molte di queste traccie, può verificarsi una drastica riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="769d3-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="769d3-109">Se non si desidera utilizzare OleTx, impostare `OleTxUpgradeEnabled` su 0 nella configurazione del Registro di sistema WS-AT.</span><span class="sxs-lookup"><span data-stu-id="769d3-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769d3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="769d3-110">See Also</span></span>  
 [<span data-ttu-id="769d3-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="769d3-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="769d3-112">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="769d3-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="769d3-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="769d3-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
