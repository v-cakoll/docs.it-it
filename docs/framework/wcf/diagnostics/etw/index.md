---
title: Traccia analitica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 4651c515a938ed8f8736597808156080cfb0bbed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609083"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="52618-102">Traccia analitica con ETW</span><span class="sxs-lookup"><span data-stu-id="52618-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="52618-103">Traccia analitica di Windows Communication Foundation (WCF) offre un modo per acquisire informazioni diagnostiche durante l'esecuzione di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="52618-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="52618-104">Gli eventi di traccia analitica WCF vengono generati in punti chiave nello stack di WCF per consentire la risoluzione dei problemi dei servizi WCF in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="52618-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="52618-105">Traccia analitica per i servizi WCF con un impatto minimo sulle prestazioni di un server di prodotto che includono [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] dei servizi WCF come questi eventi vengono generati in modo molto efficiente a una sessione Event Tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="52618-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52618-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="52618-106">In This Section</span></span>  
 [<span data-ttu-id="52618-107">Panoramica della traccia analitica</span><span class="sxs-lookup"><span data-stu-id="52618-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="52618-108">Illustra il funzionamento di traccia analitica WCF in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52618-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="52618-109">Abilitazione dinamica della traccia analitica</span><span class="sxs-lookup"><span data-stu-id="52618-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="52618-110">Descrive la modalità di abilitazione o disabilitazione della traccia in modo dinamico mediante ETW.</span><span class="sxs-lookup"><span data-stu-id="52618-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="52618-111">Configurazione della traccia del flusso di messaggi</span><span class="sxs-lookup"><span data-stu-id="52618-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="52618-112">Descrive la modalità di configurazione della traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="52618-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="52618-113">Riferimento dell'evento di traccia analitica</span><span class="sxs-lookup"><span data-stu-id="52618-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="52618-114">Mostra una tabella di ID evento con i relativi livelli, parole chiave e messaggi dell'evento.</span><span class="sxs-lookup"><span data-stu-id="52618-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52618-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52618-115">See also</span></span>
- [<span data-ttu-id="52618-116">WCF Services e Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="52618-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="52618-117">Eventi di rilevamento in Traccia eventi per Windows</span><span class="sxs-lookup"><span data-stu-id="52618-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
