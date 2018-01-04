---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b433e5e3c0a961098f82ad601d127290b1d6bd73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="18439-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="18439-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="18439-103">MSMQ ha rifiutato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="18439-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="18439-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18439-104">Description</span></span>  
 <span data-ttu-id="18439-105">Questa traccia indica che è stato rifiutato un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="18439-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="18439-106">I messaggi MSMQ possono essere rifiutati quando [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli.</span><span class="sxs-lookup"><span data-stu-id="18439-106">MSMQ messages can be rejected when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="18439-107">Tali messaggi vengono definiti messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="18439-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="18439-108">Un messaggio non elaborabile viene rifiutato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Reject`.</span><span class="sxs-lookup"><span data-stu-id="18439-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="18439-109">Un messaggio respinto viene recapitato al mittente [recapitabili](http://go.microsoft.com/fwlink/?LinkID=99544).</span><span class="sxs-lookup"><span data-stu-id="18439-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="18439-110">Vedere [dei messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkID=99546) per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="18439-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="18439-111">Vedere [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) per ulteriori informazioni sul significato di un messaggio respinto in MSMQ.</span><span class="sxs-lookup"><span data-stu-id="18439-111">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18439-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18439-112">See Also</span></span>  
 [<span data-ttu-id="18439-113">Traccia</span><span class="sxs-lookup"><span data-stu-id="18439-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="18439-114">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="18439-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="18439-115">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="18439-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="18439-116">Messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="18439-116">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="18439-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="18439-117">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkID=99548)
