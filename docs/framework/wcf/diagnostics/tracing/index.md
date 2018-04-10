---
title: Traccia
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 75870850a7df01d255d3512dde2a550e2a6c205a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="tracing"></a><span data-ttu-id="15ecc-102">Traccia</span><span class="sxs-lookup"><span data-stu-id="15ecc-102">Tracing</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="15ecc-103"> fornisce strumenti applicativi e dati diagnostici per il monitoraggio e l'analisi degli errori.</span><span class="sxs-lookup"><span data-stu-id="15ecc-103"> provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="15ecc-104">Al posto di un debugger, è possibile utilizzare la traccia per capire il comportamento o le cause di errori di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="15ecc-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="15ecc-105">È anche possibile correlare errori e processi attraverso i componenti per fornire un'esperienza end-to-end.</span><span class="sxs-lookup"><span data-stu-id="15ecc-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="15ecc-106"> restituisce i dati seguenti per la traccia diagnostica:</span><span class="sxs-lookup"><span data-stu-id="15ecc-106"> outputs the following data for diagnostic tracing:</span></span>  
  
-   <span data-ttu-id="15ecc-107">Tracce delle attività cardine di processo in tutti i componenti delle applicazioni, ad esempio chiamate dell'operazione, eccezioni del codice, avvisi e altri eventi di elaborazione significativi.</span><span class="sxs-lookup"><span data-stu-id="15ecc-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
-   <span data-ttu-id="15ecc-108">Eventi di errore di Windows quando la funzionalità di traccia non viene eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="15ecc-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15ecc-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="15ecc-109">In This Section</span></span>  
 [<span data-ttu-id="15ecc-110">Configurazione delle funzionalità di traccia</span><span class="sxs-lookup"><span data-stu-id="15ecc-110">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
 <span data-ttu-id="15ecc-111">In questo argomento viene illustrato come è possibile configurare la traccia a livelli diversi per rispondere a requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="15ecc-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="15ecc-112">Traccia end-to-end</span><span class="sxs-lookup"><span data-stu-id="15ecc-112">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)  
  
 <span data-ttu-id="15ecc-113">Contenuto della sezione viene illustrato come utilizzare la traccia e propagazione di attività per la correlazione end-to-end per agevolare il debug.</span><span class="sxs-lookup"><span data-stu-id="15ecc-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="15ecc-114">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="15ecc-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="15ecc-115">Contenuto della sezione viene illustrato come utilizzare la traccia per eseguire il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="15ecc-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="15ecc-116">Problemi di sicurezza e suggerimenti utili per la traccia</span><span class="sxs-lookup"><span data-stu-id="15ecc-116">Security Concerns and Useful Tips for Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="15ecc-117">In questo argomento viene descritto come proteggere informazioni riservate e vengono elencati suggerimenti utili durante l'utilizzo di WebHost.</span><span class="sxs-lookup"><span data-stu-id="15ecc-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="15ecc-118">Riferimenti per le tracce</span><span class="sxs-lookup"><span data-stu-id="15ecc-118">Traces Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/traces-reference.md)  
  
 <span data-ttu-id="15ecc-119">In questo argomento vengono elencate tutte le tracce generate da [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15ecc-119">This topic lists all the traces generated by [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ecc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15ecc-120">See Also</span></span>  
 [<span data-ttu-id="15ecc-121">Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="15ecc-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
