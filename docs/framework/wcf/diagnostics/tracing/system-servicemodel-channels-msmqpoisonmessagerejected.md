---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 562399c1d45dc73c7c88bd165e9f95ee1bcfa19d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997494"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="c4e90-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="c4e90-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="c4e90-103">Messaggio non elaborabile rifiutato.</span><span class="sxs-lookup"><span data-stu-id="c4e90-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c4e90-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4e90-104">Description</span></span>  
 <span data-ttu-id="c4e90-105">La traccia indica che è stato rilevato e successivamente rifiutato un messaggio non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="c4e90-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="c4e90-106">Ciò accade quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`.</span><span class="sxs-lookup"><span data-stu-id="c4e90-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="c4e90-107">Un messaggio rifiutato viene recapitato al mittente [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="c4e90-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="c4e90-108">Visualizzare [dei messaggi non elaborabili](https://go.microsoft.com/fwlink/?LinkId=99546) per altri dettagli su cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="c4e90-108">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="c4e90-109">Visualizzare [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) per altri dettagli sul significato di un messaggio rifiutato in MSMQ.</span><span class="sxs-lookup"><span data-stu-id="c4e90-109">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e90-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4e90-110">See also</span></span>

- [<span data-ttu-id="c4e90-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="c4e90-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="c4e90-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="c4e90-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c4e90-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="c4e90-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="c4e90-114">Messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="c4e90-114">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkId=99546)
- [<span data-ttu-id="c4e90-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="c4e90-115">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkId=99548)
