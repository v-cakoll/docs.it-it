---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 2de1aa51d58d9d86f953e027fd3f7f172e3887d3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097564"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="9bd18-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="9bd18-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="9bd18-103">È impossibile completare la negoziazione del protocollo OleTransactions per il contesto di coordinamento specificato.</span><span class="sxs-lookup"><span data-stu-id="9bd18-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9bd18-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9bd18-104">Description</span></span>  
 <span data-ttu-id="9bd18-105">Viene tracciato quando una transazione in ingresso con informazioni OleTx non è in grado di utilizzare le informazioni OleTx allegate e utilizzerà pertanto WS-AT.</span><span class="sxs-lookup"><span data-stu-id="9bd18-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="9bd18-106">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9bd18-106">Troubleshooting</span></span>  
 <span data-ttu-id="9bd18-107">Indica un problema potenziale con la comunicazione RPC MSDTC tra i computer.</span><span class="sxs-lookup"><span data-stu-id="9bd18-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="9bd18-108">Se il registro contiene molte di queste traccie, può verificarsi una drastica riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="9bd18-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="9bd18-109">Se non si desidera utilizzare OleTx, impostare `OleTxUpgradeEnabled` su 0 nella configurazione del Registro di sistema WS-AT.</span><span class="sxs-lookup"><span data-stu-id="9bd18-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd18-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bd18-110">See also</span></span>

- [<span data-ttu-id="9bd18-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="9bd18-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9bd18-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="9bd18-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9bd18-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="9bd18-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
