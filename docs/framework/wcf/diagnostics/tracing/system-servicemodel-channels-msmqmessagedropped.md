---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 4b016f53a75d9527a5cd1bbadacacd650b7f35b0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601910"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="7ab74-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="7ab74-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="7ab74-103">MSMQ ha rilasciato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="7ab74-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7ab74-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ab74-104">Description</span></span>  
 <span data-ttu-id="7ab74-105">La traccia indica che è stato eliminato un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="7ab74-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="7ab74-106">I messaggi MSMQ possono essere eliminati quando Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non è in grado di elaborarli.</span><span class="sxs-lookup"><span data-stu-id="7ab74-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="7ab74-107">Tali messaggi vengono definiti messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="7ab74-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="7ab74-108">Un messaggio non elaborabile viene rilasciato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Drop`.</span><span class="sxs-lookup"><span data-stu-id="7ab74-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="7ab74-109">Un messaggio eliminato viene rimosso dalla coda e non è più recuperabile.</span><span class="sxs-lookup"><span data-stu-id="7ab74-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="7ab74-110">Per ulteriori informazioni sul momento in cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato, vedere [gestione di messaggi non elaborabili](../../feature-details/poison-message-handling.md).</span><span class="sxs-lookup"><span data-stu-id="7ab74-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab74-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ab74-111">See also</span></span>

- [<span data-ttu-id="7ab74-112">Traccia</span><span class="sxs-lookup"><span data-stu-id="7ab74-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="7ab74-113">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="7ab74-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7ab74-114">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="7ab74-114">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="7ab74-115">Gestione dei messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="7ab74-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
