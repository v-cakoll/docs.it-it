---
title: Traccia analitica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: dd745730ca186b9489c547f790c546e95bf96372
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798084"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="07d82-102">Traccia analitica con ETW</span><span class="sxs-lookup"><span data-stu-id="07d82-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="07d82-103">La traccia analitica Windows Communication Foundation (WCF) offre un modo per acquisire informazioni diagnostiche durante l'esecuzione di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="07d82-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="07d82-104">Gli eventi di traccia analitica WCF vengono emessi in punti chiave dello stack WCF per consentire la risoluzione dei problemi relativi ai servizi WCF in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="07d82-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="07d82-105">La traccia analitica per i servizi WCF ha un effetto minimo sulle prestazioni di un server [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] di prodotto che ospita i servizi WCF poiché questi eventi vengono inviati in modo molto efficiente a una sessione di Event Tracing for Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="07d82-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07d82-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="07d82-106">In This Section</span></span>  
 [<span data-ttu-id="07d82-107">Panoramica della traccia analitica</span><span class="sxs-lookup"><span data-stu-id="07d82-107">Analytic Tracing Overview</span></span>](analytic-tracing-overview.md)  
 <span data-ttu-id="07d82-108">Viene illustrato il funzionamento della traccia analitica di WCF in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07d82-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="07d82-109">Abilitazione dinamica della traccia analitica</span><span class="sxs-lookup"><span data-stu-id="07d82-109">Dynamically Enabling Analytic Tracing</span></span>](dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="07d82-110">Descrive la modalità di abilitazione o disabilitazione della traccia in modo dinamico mediante ETW.</span><span class="sxs-lookup"><span data-stu-id="07d82-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="07d82-111">Configurazione della traccia del flusso di messaggi</span><span class="sxs-lookup"><span data-stu-id="07d82-111">Configuring Message Flow Tracing</span></span>](configuring-message-flow-tracing.md)  
 <span data-ttu-id="07d82-112">Descrive la modalità di configurazione della traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="07d82-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="07d82-113">Riferimento dell'evento di traccia analitica</span><span class="sxs-lookup"><span data-stu-id="07d82-113">Analytic Trace Event Reference</span></span>](analytic-trace-event-reference.md)  
 <span data-ttu-id="07d82-114">Mostra una tabella di ID evento con i relativi livelli, parole chiave e messaggi dell'evento.</span><span class="sxs-lookup"><span data-stu-id="07d82-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d82-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07d82-115">See also</span></span>

- [<span data-ttu-id="07d82-116">WCF Services e Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="07d82-116">WCF Services and Event Tracing for Windows</span></span>](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="07d82-117">Eventi di rilevamento in Traccia eventi per Windows</span><span class="sxs-lookup"><span data-stu-id="07d82-117">Tracking Events into Event Tracing in Windows</span></span>](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
