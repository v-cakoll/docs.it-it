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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4cecacdcc9ec1155fbb374bb763f6858da6ccc57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="15cca-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="15cca-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="15cca-103">Impossibile spostare o eliminare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="15cca-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="15cca-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15cca-104">Description</span></span>  
 <span data-ttu-id="15cca-105">La traccia indica che si è verificato un errore durante il tentativo di spostare, eliminare o rifiutare un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="15cca-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="15cca-106">I messaggi MSMQ vengono usati da [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (in caso di uso con NetMsmqBinding o MsmqIntegrationBinding). Questa traccia è correlata al valore scelto della proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="15cca-106">MSMQ messages are employed by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="15cca-107">Questa traccia non è indicativa di un errore di sistema complessivo.</span><span class="sxs-lookup"><span data-stu-id="15cca-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="15cca-108">Tuttavia, indica che l'eliminazione del messaggio non elaborabile scelta ha avuto esito negativo per un messaggio.</span><span class="sxs-lookup"><span data-stu-id="15cca-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="15cca-109">Vedere [dei messaggi non elaborabili](http://go.microsoft.com/fwlink/?LinkID=99546) per ulteriori informazioni su quando i messaggi diventano non elaborabili e su come configurare il servizio per gestirli nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="15cca-109">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15cca-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15cca-110">See Also</span></span>  
 [<span data-ttu-id="15cca-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="15cca-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="15cca-112">Utilizzo delle tracce per risolvere i problemi dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="15cca-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="15cca-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="15cca-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
