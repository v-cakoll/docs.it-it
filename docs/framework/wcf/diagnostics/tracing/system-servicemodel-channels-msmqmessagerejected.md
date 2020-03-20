---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674769"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="4f68d-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="4f68d-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="4f68d-103">MSMQ ha rifiutato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="4f68d-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4f68d-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f68d-104">Description</span></span>  
 <span data-ttu-id="4f68d-105">Questa traccia indica che è stato rifiutato un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="4f68d-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="4f68d-106">I messaggi MSMQ possono essere rifiutati quando Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli.</span><span class="sxs-lookup"><span data-stu-id="4f68d-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="4f68d-107">Tali messaggi vengono definiti messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="4f68d-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="4f68d-108">Un messaggio non elaborabile viene rifiutato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`.</span><span class="sxs-lookup"><span data-stu-id="4f68d-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="4f68d-109">Un messaggio rifiutato viene recapitato alla coda di [messaggi non recapitabili](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)del mittente.</span><span class="sxs-lookup"><span data-stu-id="4f68d-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="4f68d-110">Per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato, vedere Gestione dei [messaggi non elaborabili](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="4f68d-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="4f68d-111">Per ulteriori informazioni sul significato di un messaggio rifiutato in MSMQ, vedere [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span><span class="sxs-lookup"><span data-stu-id="4f68d-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f68d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f68d-112">See also</span></span>

- [<span data-ttu-id="4f68d-113">Traccia</span><span class="sxs-lookup"><span data-stu-id="4f68d-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="4f68d-114">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="4f68d-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4f68d-115">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="4f68d-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="4f68d-116">Gestione dei messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="4f68d-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="4f68d-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="4f68d-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
