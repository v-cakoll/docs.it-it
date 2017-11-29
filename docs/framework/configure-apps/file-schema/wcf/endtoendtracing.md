---
title: '&lt;endToEndTracing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1bcd7405c5e3ebf2d1c156ff3bca9f473df9fa35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="1037d-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="1037d-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="1037d-103">Elemento di configurazione che consente di abilitare e disabilitare aspetti diversi di traccia end-to-end durante l'esecuzione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="1037d-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="1037d-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1037d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1037d-105">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="1037d-105">\<diagnostic></span></span>  
<span data-ttu-id="1037d-106">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="1037d-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1037d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1037d-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1037d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1037d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1037d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1037d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1037d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1037d-110">Attributes</span></span>  
  
|<span data-ttu-id="1037d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1037d-111">Attribute</span></span>|<span data-ttu-id="1037d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1037d-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="1037d-113">Valore booleano che specifica se è abilitata la traccia di attività.</span><span class="sxs-lookup"><span data-stu-id="1037d-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="1037d-114">Valore booleano che specifica se è abilitata la traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="1037d-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="1037d-115">Valore booleano che specifica se l'attributo di propagazione è impostato su true.</span><span class="sxs-lookup"><span data-stu-id="1037d-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1037d-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1037d-116">Child Elements</span></span>  
 <span data-ttu-id="1037d-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1037d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1037d-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1037d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1037d-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="1037d-119">Element</span></span>|<span data-ttu-id="1037d-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1037d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1037d-121">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="1037d-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="1037d-122">Definisce le impostazioni WCF per l'ispezione e il controllo in fase di esecuzione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="1037d-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1037d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1037d-123">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [<span data-ttu-id="1037d-124">Traccia end-to-End</span><span class="sxs-lookup"><span data-stu-id="1037d-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
