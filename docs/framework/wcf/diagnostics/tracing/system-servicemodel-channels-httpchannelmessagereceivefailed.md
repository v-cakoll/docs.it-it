---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: b848963caff706ff8a886c1e358ad6688e9611c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145275"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="2f05d-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="2f05d-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="2f05d-103">Impossibile ricevere un messaggio tramite canale HTTP.</span><span class="sxs-lookup"><span data-stu-id="2f05d-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2f05d-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f05d-104">Description</span></span>  
 <span data-ttu-id="2f05d-105">Questa traccia può essere emessa come avviso o come errore.</span><span class="sxs-lookup"><span data-stu-id="2f05d-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="2f05d-106">In entrambi i casi, la traccia viene emessa quando non viene trovato un listener compatibile per una richiesta HTTP in entrata e tale richiesta viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="2f05d-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="2f05d-107">Questa situazione può verificarsi in quanto il verbo HTTP della richiesta non è stato riconosciuto da un listener HTTP o perchè nessun listener era in ascolto sull'indirizzo a cui era destinata la richiesta.</span><span class="sxs-lookup"><span data-stu-id="2f05d-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="2f05d-108">La traccia viene emessa come avviso nel caso di un servizio indipendente e come errore nel caso di un servizio ospitato in IIS.</span><span class="sxs-lookup"><span data-stu-id="2f05d-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f05d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f05d-109">See also</span></span>

- [<span data-ttu-id="2f05d-110">Traccia</span><span class="sxs-lookup"><span data-stu-id="2f05d-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2f05d-111">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="2f05d-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2f05d-112">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="2f05d-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
