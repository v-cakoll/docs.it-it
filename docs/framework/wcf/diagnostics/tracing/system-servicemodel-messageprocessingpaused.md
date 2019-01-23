---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ba067303d861bbd7d88c67f6fd868bd808e07dfd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528680"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="8a650-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="8a650-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="8a650-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="8a650-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="8a650-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a650-104">Description</span></span>  
 <span data-ttu-id="8a650-105">I thread sono stati commutati durante l'elaborazione di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="8a650-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="8a650-106">L'elaborazione messaggi può essere interrotta per le ragioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a650-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="8a650-107">ConcurrencyMode è singolo o rientrante e il servizio sta elaborando un altro messaggio.</span><span class="sxs-lookup"><span data-stu-id="8a650-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="8a650-108">La transazione è attivata e il servizio sta elaborando un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="8a650-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="8a650-109">Il contesto di sincronizzazione non è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="8a650-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a650-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a650-110">See also</span></span>
- [<span data-ttu-id="8a650-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="8a650-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8a650-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="8a650-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8a650-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="8a650-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
