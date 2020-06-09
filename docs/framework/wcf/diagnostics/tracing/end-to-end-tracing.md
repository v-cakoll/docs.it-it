---
title: Analisi end-to-end
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: fc8fc448bdcf94ab25349f6b34961a34e5ed2a5a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598580"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="9301f-102">Analisi end-to-end</span><span class="sxs-lookup"><span data-stu-id="9301f-102">End-to-End Tracing</span></span>
<span data-ttu-id="9301f-103">La traccia end-to-end (E2E) consente agli sviluppatori di seguire l'esecuzione del codice nell'infrastruttura Windows Communication Foundation (WCF) per individuare il motivo per cui un percorso di codice ha avuto esito negativo o per fornire una traccia dettagliata per la pianificazione della capacità e l'analisi delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="9301f-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="9301f-104">Windows Communication Foundation (WCF) fornisce tre meccanismi di correlazione per facilitare la diagnosi della cause di un errore: attività, trasferimenti e propagazione.</span><span class="sxs-lookup"><span data-stu-id="9301f-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="9301f-105">Per un elenco degli scenari di traccia end-to-end e la rispettiva attività e progettazione di traccia, vedere [scenari di traccia end-to](end-to-end-tracing-scenarios.md) -end.</span><span class="sxs-lookup"><span data-stu-id="9301f-105">See [End-To-End Tracing Scenarios](end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9301f-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9301f-106">In This Section</span></span>  
 <span data-ttu-id="9301f-107">[Activity](activity.md): descrive le tracce di attività nel modello di traccia Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9301f-107">[Activity](activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="9301f-108">[Transfer](transfer.md): descrive il trasferimento nel modello di traccia Windows Communication Foundation (WCF) e l'uso del trasferimento per correlare le attività all'interno di endpoint.</span><span class="sxs-lookup"><span data-stu-id="9301f-108">[Transfer](transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="9301f-109">[Propagazione](propagation.md): descrive la propagazione delle attività nel modello di traccia Windows Communication Foundation (WCF) e l'utilizzo della propagazione per correlare le attività tra gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="9301f-109">[Propagation](propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="9301f-110">Riepilogo dei tipi di traccia</span><span class="sxs-lookup"><span data-stu-id="9301f-110">Trace Type Summary</span></span>](trace-type-summary.md)  
  
 <span data-ttu-id="9301f-111">Fornisce un riepilogo di tutti i tipi di analisi di attività</span><span class="sxs-lookup"><span data-stu-id="9301f-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9301f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9301f-112">See also</span></span>

- [<span data-ttu-id="9301f-113">Configurazione delle funzionalità di traccia</span><span class="sxs-lookup"><span data-stu-id="9301f-113">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="9301f-114">Uso del visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="9301f-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="9301f-115">Scenari di analisi end-to-end</span><span class="sxs-lookup"><span data-stu-id="9301f-115">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="9301f-116">Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="9301f-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
