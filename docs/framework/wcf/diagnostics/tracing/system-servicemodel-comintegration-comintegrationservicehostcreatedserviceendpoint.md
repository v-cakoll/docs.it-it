---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87eac8f0e3949ac47c7bb2915a87043bdc205b8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="de29b-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="de29b-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="de29b-103">Impossibile spostare o eliminare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="de29b-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="de29b-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de29b-104">Description</span></span>  
 <span data-ttu-id="de29b-105">La traccia indica che si è verificato un errore durante il tentativo di spostare, eliminare o rifiutare un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="de29b-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="de29b-106">I messaggi MSMQ vengono usati da [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (in caso di uso con NetMsmqBinding o MsmqIntegrationBinding). Questa traccia è correlata al valore scelto della proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="de29b-106">MSMQ messages are employed by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="de29b-107">Questa traccia non è indicativa di un errore di sistema complessivo.</span><span class="sxs-lookup"><span data-stu-id="de29b-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="de29b-108">Tuttavia, indica che l'eliminazione del messaggio non elaborabile scelta ha avuto esito negativo per un messaggio.</span><span class="sxs-lookup"><span data-stu-id="de29b-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="de29b-109">Vedere [dei messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkID=99546) per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="de29b-109">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de29b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de29b-110">See Also</span></span>  
 [<span data-ttu-id="de29b-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="de29b-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="de29b-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="de29b-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="de29b-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="de29b-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
