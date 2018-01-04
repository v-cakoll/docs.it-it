---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2f905c345db89e909920334a7dbb524095bc46b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="8a9e8-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="8a9e8-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="8a9e8-103">MSMQ ha rilasciato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="8a9e8-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8a9e8-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a9e8-104">Description</span></span>  
 <span data-ttu-id="8a9e8-105">La traccia indica che è stato eliminato un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="8a9e8-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="8a9e8-106">I messaggi MSMQ possono essere eliminati quando [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli.</span><span class="sxs-lookup"><span data-stu-id="8a9e8-106">MSMQ messages can be dropped when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="8a9e8-107">Tali messaggi vengono definiti messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="8a9e8-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="8a9e8-108">Un messaggio non elaborabile viene eliminato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Drop`.</span><span class="sxs-lookup"><span data-stu-id="8a9e8-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="8a9e8-109">Un messaggio eliminato viene rimosso dalla coda e non è più recuperabile.</span><span class="sxs-lookup"><span data-stu-id="8a9e8-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="8a9e8-110">Vedere [dei messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkID=99546) per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="8a9e8-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a9e8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a9e8-111">See Also</span></span>  
 [<span data-ttu-id="8a9e8-112">Traccia</span><span class="sxs-lookup"><span data-stu-id="8a9e8-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8a9e8-113">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="8a9e8-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8a9e8-114">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="8a9e8-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="8a9e8-115">Messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="8a9e8-115">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)
