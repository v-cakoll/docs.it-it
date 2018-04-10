---
title: Traccia analitica con ETW
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a16f66ed8443749764e66d2616ae566ad788d571
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="b05bb-102">Traccia analitica con ETW</span><span class="sxs-lookup"><span data-stu-id="b05bb-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="b05bb-103">La traccia analitica di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] offre un modo per acquisire informazioni diagnostiche durante l'esecuzione di un servizio di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b05bb-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] analytic tracing offers a way to capture diagnostic information during the execution of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="b05bb-104">Gli eventi di traccia analitica di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] vengono generati in punti chiave dello stack [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] per consentire la risoluzione dei problemi relativi ai servizi di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="b05bb-104">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing events are emitted at key points in the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack to allow troubleshooting of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services in a production environment.</span></span> <span data-ttu-id="b05bb-105">Traccia analitica per [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services ha un impatto minimo sulle prestazioni di un server di prodotto che ospita [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servizi in quanto tali eventi vengono generati in modo molto efficiente a una sessione Event Tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="b05bb-105">Analytic tracing for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b05bb-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="b05bb-106">In This Section</span></span>  
 [<span data-ttu-id="b05bb-107">Panoramica della traccia analitica</span><span class="sxs-lookup"><span data-stu-id="b05bb-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="b05bb-108">Descrive la modalità in cui la traccia analitica di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] funziona in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b05bb-108">Discusses how [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="b05bb-109">Abilitazione dinamica della traccia analitica</span><span class="sxs-lookup"><span data-stu-id="b05bb-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="b05bb-110">Descrive la modalità di abilitazione o disabilitazione della traccia in modo dinamico mediante ETW.</span><span class="sxs-lookup"><span data-stu-id="b05bb-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="b05bb-111">Configurazione della traccia del flusso di messaggi</span><span class="sxs-lookup"><span data-stu-id="b05bb-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="b05bb-112">Descrive la modalità di configurazione della traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="b05bb-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="b05bb-113">Riferimento dell'evento di traccia analitica</span><span class="sxs-lookup"><span data-stu-id="b05bb-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="b05bb-114">Mostra una tabella di ID evento con i relativi livelli, parole chiave e messaggi dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b05bb-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b05bb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b05bb-115">See Also</span></span>  
 [<span data-ttu-id="b05bb-116">WCF Services e Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="b05bb-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="b05bb-117">Eventi di rilevamento in Traccia eventi per Windows</span><span class="sxs-lookup"><span data-stu-id="b05bb-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
