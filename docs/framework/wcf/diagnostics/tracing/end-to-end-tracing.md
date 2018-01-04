---
title: Analisi end-to-end
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a2127c8dda26c376d7d722a24d72d2330174027
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="cdc04-102">Analisi end-to-end</span><span class="sxs-lookup"><span data-stu-id="cdc04-102">End-to-End Tracing</span></span>
<span data-ttu-id="cdc04-103">La traccia end-to-end (e2e) consente agli sviluppatori di seguire l'esecuzione del codice nell'infrastruttura [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] per analizzare il motivo per cui un percorso di codice ha dato esito negativo o per fornire una traccia dettagliata per la pianificazione della capacità e per l'analisi delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="cdc04-103">End to End (e2e) Tracing allows developers to follow the execution of code in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="cdc04-104"> offre tre meccanismi di correlazione per consentire la diagnosi della causa di un errore: attività, trasferimenti e propagazione.</span><span class="sxs-lookup"><span data-stu-id="cdc04-104"> provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="cdc04-105">Vedere [gli scenari di traccia End-To-End](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) per un elenco di scenari di traccia end-to-end e le loro rispettive attività e la traccia di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cdc04-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cdc04-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="cdc04-106">In This Section</span></span>  
 <span data-ttu-id="cdc04-107">[Attività](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md): descrive le tracce di attività nel [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] modello di traccia.</span><span class="sxs-lookup"><span data-stu-id="cdc04-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model.</span></span>  
  
 <span data-ttu-id="cdc04-108">[Trasferimento](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md): viene descritto il trasferimento nel [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] modello di traccia e l'uso di trasferimento per correlare le attività all'interno di endpoint.</span><span class="sxs-lookup"><span data-stu-id="cdc04-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="cdc04-109">[Propagazione](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md): descrive la propagazione di attività nel [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] modello di traccia e l'utilizzo di propagazione per correlare attività attraverso gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="cdc04-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="cdc04-110">Riepilogo dei tipi di traccia</span><span class="sxs-lookup"><span data-stu-id="cdc04-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="cdc04-111">Fornisce un riepilogo di tutti i tipi di analisi di attività</span><span class="sxs-lookup"><span data-stu-id="cdc04-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc04-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdc04-112">See Also</span></span>  
 [<span data-ttu-id="cdc04-113">Configurazione delle funzionalità di traccia</span><span class="sxs-lookup"><span data-stu-id="cdc04-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="cdc04-114">Uso del visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="cdc04-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="cdc04-115">Scenari di traccia end-to-end</span><span class="sxs-lookup"><span data-stu-id="cdc04-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="cdc04-116">Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="cdc04-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
