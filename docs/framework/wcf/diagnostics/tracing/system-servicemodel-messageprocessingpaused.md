---
title: System.ServiceModel.MessageProcessingPaused
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 33d05eaa94ec0efdf6d18d03d9d38bda6f0c9eb7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="aad2d-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="aad2d-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="aad2d-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="aad2d-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="aad2d-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aad2d-104">Description</span></span>  
 <span data-ttu-id="aad2d-105">I thread sono stati commutati durante l'elaborazione di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="aad2d-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="aad2d-106">L'elaborazione messaggi può essere interrotta per le ragioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aad2d-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="aad2d-107">ConcurrencyMode è singolo o rientrante e il servizio sta elaborando un altro messaggio.</span><span class="sxs-lookup"><span data-stu-id="aad2d-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="aad2d-108">La transazione è attivata e il servizio sta elaborando un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="aad2d-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="aad2d-109">Il contesto di sincronizzazione non è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="aad2d-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad2d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aad2d-110">See Also</span></span>  
 [<span data-ttu-id="aad2d-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="aad2d-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="aad2d-112">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="aad2d-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="aad2d-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="aad2d-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
