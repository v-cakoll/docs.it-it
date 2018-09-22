---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 7e7bd48d206456af6a5a8662516c4d9c82b3ed2f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46583626"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="98529-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="98529-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="98529-103">Impossibile spostare o eliminare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="98529-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="98529-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98529-104">Description</span></span>  
 <span data-ttu-id="98529-105">La traccia indica che si è verificato un errore durante il tentativo di spostare, eliminare o rifiutare un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="98529-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="98529-106">I messaggi MSMQ vengono usati da Windows Communication Foundation (WCF) (se utilizzato con NetMsmqBinding o MsmqIntegrationBinding). Questa traccia è correlata al valore scelto del `ReceiveErrorHandling` proprietà su NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="98529-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="98529-107">Questa traccia non è indicativa di un errore di sistema complessivo.</span><span class="sxs-lookup"><span data-stu-id="98529-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="98529-108">Tuttavia, indica che l'eliminazione del messaggio non elaborabile scelta ha avuto esito negativo per un messaggio.</span><span class="sxs-lookup"><span data-stu-id="98529-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="98529-109">Visualizzare [dei messaggi non elaborabili](https://go.microsoft.com/fwlink/?LinkID=99546) per altri dettagli su cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="98529-109">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98529-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98529-110">See Also</span></span>  
 [<span data-ttu-id="98529-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="98529-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="98529-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="98529-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="98529-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="98529-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
