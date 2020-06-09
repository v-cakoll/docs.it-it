---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 85bec8255e0d20d6e76ea354e5b8c42b83d7d8e6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598151"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="14294-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="14294-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="14294-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="14294-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="14294-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14294-104">Description</span></span>  
 <span data-ttu-id="14294-105">I thread sono stati commutati durante l'elaborazione di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="14294-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="14294-106">L'elaborazione messaggi può essere interrotta per le ragioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="14294-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="14294-107">ConcurrencyMode è singolo o rientrante e il servizio sta elaborando un altro messaggio.</span><span class="sxs-lookup"><span data-stu-id="14294-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="14294-108">La transazione è attivata e il servizio sta elaborando un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="14294-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="14294-109">Il contesto di sincronizzazione non è aggiornato.</span><span class="sxs-lookup"><span data-stu-id="14294-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14294-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14294-110">See also</span></span>

- [<span data-ttu-id="14294-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="14294-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="14294-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="14294-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="14294-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="14294-113">Administration and Diagnostics</span></span>](../index.md)
