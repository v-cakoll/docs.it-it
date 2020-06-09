---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: c388a9dc3569e20639de09abc5f4941b73c561ad
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578051"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="166dd-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="166dd-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="166dd-103">MSMQ ha rifiutato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="166dd-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="166dd-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="166dd-104">Description</span></span>  
 <span data-ttu-id="166dd-105">Questa traccia indica che è stato rifiutato un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="166dd-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="166dd-106">I messaggi MSMQ possono essere rifiutati quando Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli.</span><span class="sxs-lookup"><span data-stu-id="166dd-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="166dd-107">Tali messaggi vengono definiti messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="166dd-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="166dd-108">Un messaggio non elaborabile viene rifiutato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`.</span><span class="sxs-lookup"><span data-stu-id="166dd-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="166dd-109">Un messaggio rifiutato viene restituito alla coda dei messaggi non [recapitabili](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)del mittente.</span><span class="sxs-lookup"><span data-stu-id="166dd-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="166dd-110">Per ulteriori informazioni sul momento in cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato, vedere [gestione di messaggi non elaborabili](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="166dd-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="166dd-111">Per ulteriori informazioni sul significato di un messaggio rifiutato in MSMQ, vedere [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span><span class="sxs-lookup"><span data-stu-id="166dd-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="166dd-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="166dd-112">See also</span></span>

- [<span data-ttu-id="166dd-113">Traccia</span><span class="sxs-lookup"><span data-stu-id="166dd-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="166dd-114">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="166dd-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="166dd-115">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="166dd-115">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="166dd-116">Gestione dei messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="166dd-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="166dd-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="166dd-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
