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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1176af676673e19eb2d8cd54cc4d2d254c7ba324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="0a624-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="0a624-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="0a624-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="0a624-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="0a624-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a624-104">Description</span></span>  
 <span data-ttu-id="0a624-105">I thread sono stati commutati durante l'elaborazione di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="0a624-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="0a624-106">L'elaborazione messaggi può essere interrotta per le ragioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a624-106">Message processing can be paused by the following reasons:</span></span>  
  
-   <span data-ttu-id="0a624-107">ConcurrencyMode è singolo o rientrante e il servizio sta elaborando un altro messaggio.</span><span class="sxs-lookup"><span data-stu-id="0a624-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
-   <span data-ttu-id="0a624-108">La transazione è attivata e il servizio sta elaborando un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="0a624-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
-   <span data-ttu-id="0a624-109">Il contesto di sincronizzazione non è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="0a624-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a624-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a624-110">See Also</span></span>  
 [<span data-ttu-id="0a624-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="0a624-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="0a624-112">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0a624-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="0a624-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="0a624-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
