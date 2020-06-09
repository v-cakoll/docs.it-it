---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 8b81cdcaf74aca044260495867b2c4f1de517682
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593750"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="51252-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="51252-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="51252-103">Impossibile spostare o eliminare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="51252-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="51252-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51252-104">Description</span></span>  
 <span data-ttu-id="51252-105">La traccia indica che si è verificato un errore durante il tentativo di spostare, eliminare o rifiutare un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="51252-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="51252-106">I messaggi MSMQ vengono utilizzati da Windows Communication Foundation (WCF) (se utilizzati con NetMsmqBinding o MsmqIntegrationBinding). Questa traccia è correlata al valore scelto della `ReceiveErrorHandling` proprietà su NetMsmqBinding o MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="51252-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="51252-107">Questa traccia non è indicativa di un errore di sistema complessivo.</span><span class="sxs-lookup"><span data-stu-id="51252-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="51252-108">Tuttavia, indica che l'eliminazione del messaggio non elaborabile scelta ha avuto esito negativo per un messaggio.</span><span class="sxs-lookup"><span data-stu-id="51252-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="51252-109">Per ulteriori informazioni sul momento in cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato, vedere [gestione di messaggi non elaborabili](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="51252-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51252-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51252-110">See also</span></span>

- [<span data-ttu-id="51252-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="51252-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="51252-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="51252-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="51252-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="51252-113">Administration and Diagnostics</span></span>](../index.md)
