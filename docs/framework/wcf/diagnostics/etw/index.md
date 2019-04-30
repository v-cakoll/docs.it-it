---
title: Traccia analitica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: cff13439995d8a90da15b7afa15723f21574e35e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962045"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="d7485-102">Traccia analitica con ETW</span><span class="sxs-lookup"><span data-stu-id="d7485-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="d7485-103">Traccia analitica di Windows Communication Foundation (WCF) offre un modo per acquisire informazioni diagnostiche durante l'esecuzione di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="d7485-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="d7485-104">Gli eventi di traccia analitica WCF vengono generati in punti chiave nello stack di WCF per consentire la risoluzione dei problemi dei servizi WCF in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="d7485-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="d7485-105">Traccia analitica per i servizi WCF con un impatto minimo sulle prestazioni di un server di prodotto che includono [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] dei servizi WCF come questi eventi vengono generati in modo molto efficiente a una sessione Event Tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="d7485-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7485-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d7485-106">In This Section</span></span>  
 [<span data-ttu-id="d7485-107">Panoramica della traccia analitica</span><span class="sxs-lookup"><span data-stu-id="d7485-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="d7485-108">Illustra il funzionamento di traccia analitica WCF in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7485-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="d7485-109">Abilitazione dinamica della traccia analitica</span><span class="sxs-lookup"><span data-stu-id="d7485-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="d7485-110">Descrive la modalità di abilitazione o disabilitazione della traccia in modo dinamico mediante ETW.</span><span class="sxs-lookup"><span data-stu-id="d7485-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="d7485-111">Configurazione della traccia del flusso di messaggi</span><span class="sxs-lookup"><span data-stu-id="d7485-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="d7485-112">Descrive la modalità di configurazione della traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="d7485-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="d7485-113">Riferimento dell'evento di traccia analitica</span><span class="sxs-lookup"><span data-stu-id="d7485-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="d7485-114">Mostra una tabella di ID evento con i relativi livelli, parole chiave e messaggi dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d7485-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7485-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7485-115">See also</span></span>

- [<span data-ttu-id="d7485-116">WCF Services e Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="d7485-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="d7485-117">Eventi di rilevamento in Traccia eventi per Windows</span><span class="sxs-lookup"><span data-stu-id="d7485-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
