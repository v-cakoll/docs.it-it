---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28924f04dc83387f49c2369c2598c028f9b8d4bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="8726e-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="8726e-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="8726e-103">Messaggio non elaborabile rifiutato.</span><span class="sxs-lookup"><span data-stu-id="8726e-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8726e-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8726e-104">Description</span></span>  
 <span data-ttu-id="8726e-105">La traccia indica che è stato rilevato e successivamente rifiutato un messaggio non elaborabile.</span><span class="sxs-lookup"><span data-stu-id="8726e-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="8726e-106">Ciò accade quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`.</span><span class="sxs-lookup"><span data-stu-id="8726e-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="8726e-107">Un messaggio respinto viene recapitato al mittente [recapitabili](http://go.microsoft.com/fwlink/?LinkId=99544).</span><span class="sxs-lookup"><span data-stu-id="8726e-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="8726e-108">Vedere [dei messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkId=99546) per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="8726e-108">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="8726e-109">Vedere [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) per ulteriori informazioni sul significato di un messaggio respinto in MSMQ.</span><span class="sxs-lookup"><span data-stu-id="8726e-109">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8726e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8726e-110">See Also</span></span>  
 [<span data-ttu-id="8726e-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="8726e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8726e-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="8726e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8726e-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="8726e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="8726e-114">Messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="8726e-114">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [<span data-ttu-id="8726e-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="8726e-115">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkId=99548)
