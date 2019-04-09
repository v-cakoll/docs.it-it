---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087479"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="f39bf-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="f39bf-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="f39bf-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="f39bf-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="f39bf-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f39bf-104">Description</span></span>  
 <span data-ttu-id="f39bf-105">I thread sono stati commutati durante l'elaborazione di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="f39bf-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="f39bf-106">L'elaborazione messaggi può essere interrotta per le ragioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f39bf-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="f39bf-107">ConcurrencyMode è singolo o rientrante e il servizio sta elaborando un altro messaggio.</span><span class="sxs-lookup"><span data-stu-id="f39bf-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="f39bf-108">La transazione è attivata e il servizio sta elaborando un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="f39bf-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="f39bf-109">Il contesto di sincronizzazione non è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="f39bf-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f39bf-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f39bf-110">See also</span></span>

- [<span data-ttu-id="f39bf-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="f39bf-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="f39bf-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="f39bf-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f39bf-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="f39bf-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
