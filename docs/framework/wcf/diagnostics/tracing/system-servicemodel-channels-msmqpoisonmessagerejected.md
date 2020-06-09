---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: f0e49fcfa13bb9932a88a4e79d617343c080bb3c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598372"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="e42ea-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="e42ea-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="e42ea-103">Messaggio non elaborabile rifiutato.</span><span class="sxs-lookup"><span data-stu-id="e42ea-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e42ea-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e42ea-104">Description</span></span>  

 <span data-ttu-id="e42ea-105">La traccia indica che è stato rilevato e successivamente rifiutato un messaggio non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="e42ea-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="e42ea-106">Ciò accade quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`.</span><span class="sxs-lookup"><span data-stu-id="e42ea-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="e42ea-107">Un messaggio rifiutato viene restituito alla coda dei messaggi non [recapitabili](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)del mittente.</span><span class="sxs-lookup"><span data-stu-id="e42ea-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="e42ea-108">Per ulteriori informazioni sul momento in cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato, vedere [gestione di messaggi non elaborabili](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="e42ea-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="e42ea-109">Per ulteriori informazioni sul significato di un messaggio rifiutato in MSMQ, vedere [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span><span class="sxs-lookup"><span data-stu-id="e42ea-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e42ea-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e42ea-110">See also</span></span>

- [<span data-ttu-id="e42ea-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="e42ea-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="e42ea-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="e42ea-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e42ea-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="e42ea-113">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="e42ea-114">Gestione dei messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="e42ea-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="e42ea-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="e42ea-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
