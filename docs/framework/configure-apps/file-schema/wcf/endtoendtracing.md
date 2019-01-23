---
title: '&lt;endToEndTracing&gt;'
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: c2f5e33eff4fdc6dfa85bcc10b59a7c1436cabb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519381"
---
# <a name="ltendtoendtracinggt"></a><span data-ttu-id="3961d-102">&lt;endToEndTracing&gt;</span><span class="sxs-lookup"><span data-stu-id="3961d-102">&lt;endToEndTracing&gt;</span></span>
<span data-ttu-id="3961d-103">Elemento di configurazione che consente di abilitare e disabilitare aspetti diversi di traccia end-to-end durante l'esecuzione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="3961d-103">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="3961d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3961d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3961d-105">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="3961d-105">\<diagnostic></span></span>  
<span data-ttu-id="3961d-106">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="3961d-106">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3961d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3961d-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3961d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3961d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3961d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3961d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3961d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3961d-110">Attributes</span></span>  
  
|<span data-ttu-id="3961d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="3961d-111">Attribute</span></span>|<span data-ttu-id="3961d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3961d-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="3961d-113">Valore booleano che specifica se è abilitata la traccia di attività.</span><span class="sxs-lookup"><span data-stu-id="3961d-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="3961d-114">Valore booleano che specifica se è abilitata la traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="3961d-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="3961d-115">Valore booleano che specifica se l'attributo di propagazione è impostato su true.</span><span class="sxs-lookup"><span data-stu-id="3961d-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3961d-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3961d-116">Child Elements</span></span>  
 <span data-ttu-id="3961d-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3961d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3961d-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3961d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3961d-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="3961d-119">Element</span></span>|<span data-ttu-id="3961d-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3961d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3961d-121">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="3961d-121">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="3961d-122">Definisce le impostazioni WCF per l'ispezione e il controllo in fase di esecuzione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="3961d-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3961d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3961d-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="3961d-124">Traccia end-to-end</span><span class="sxs-lookup"><span data-stu-id="3961d-124">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
