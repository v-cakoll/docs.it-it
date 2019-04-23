---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 4feeb1b57d79c7445d51f5d688b0a9f55e761542
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143390"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="6a73c-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="6a73c-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="6a73c-103">MSMQ ha rifiutato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="6a73c-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6a73c-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a73c-104">Description</span></span>  
 <span data-ttu-id="6a73c-105">Questa traccia indica che è stato rifiutato un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6a73c-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="6a73c-106">Quando Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non riesce a elaborarli, è possono rifiutare i messaggi MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6a73c-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="6a73c-107">Tali messaggi vengono definiti messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="6a73c-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="6a73c-108">Un messaggio non elaborabile viene rifiutato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`.</span><span class="sxs-lookup"><span data-stu-id="6a73c-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="6a73c-109">Un messaggio rifiutato viene recapitato al mittente [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkID=99544).</span><span class="sxs-lookup"><span data-stu-id="6a73c-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="6a73c-110">Visualizzare [dei messaggi non elaborabili](https://go.microsoft.com/fwlink/?LinkID=99546) per altri dettagli su cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="6a73c-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="6a73c-111">Visualizzare [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) per altri dettagli sul significato di un messaggio rifiutato in MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6a73c-111">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a73c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a73c-112">See also</span></span>

- [<span data-ttu-id="6a73c-113">Traccia</span><span class="sxs-lookup"><span data-stu-id="6a73c-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6a73c-114">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="6a73c-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6a73c-115">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="6a73c-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="6a73c-116">Messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="6a73c-116">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
- [<span data-ttu-id="6a73c-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="6a73c-117">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkID=99548)
