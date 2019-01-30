---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1867e307ba004af821045e7d1b5775c470d8a3e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266754"
---
# <a name="endtoendtracing"></a><span data-ttu-id="ae27d-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="ae27d-101">\<endToEndTracing></span></span>
<span data-ttu-id="ae27d-102">Elemento di configurazione che consente di abilitare e disabilitare aspetti diversi di traccia end-to-end durante l'esecuzione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="ae27d-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="ae27d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ae27d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae27d-104">\<diagnostica ></span><span class="sxs-lookup"><span data-stu-id="ae27d-104">\<diagnostic></span></span>  
<span data-ttu-id="ae27d-105">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="ae27d-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae27d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae27d-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae27d-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ae27d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ae27d-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ae27d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae27d-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="ae27d-109">Attributes</span></span>  
  
|<span data-ttu-id="ae27d-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="ae27d-110">Attribute</span></span>|<span data-ttu-id="ae27d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae27d-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="ae27d-112">Valore booleano che specifica se è abilitata la traccia di attività.</span><span class="sxs-lookup"><span data-stu-id="ae27d-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="ae27d-113">Valore booleano che specifica se è abilitata la traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="ae27d-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="ae27d-114">Valore booleano che specifica se l'attributo di propagazione è impostato su true.</span><span class="sxs-lookup"><span data-stu-id="ae27d-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae27d-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ae27d-115">Child Elements</span></span>  
 <span data-ttu-id="ae27d-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ae27d-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae27d-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ae27d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ae27d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae27d-118">Element</span></span>|<span data-ttu-id="ae27d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae27d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae27d-120">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="ae27d-120">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="ae27d-121">Definisce le impostazioni WCF per l'ispezione e il controllo in fase di esecuzione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="ae27d-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae27d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae27d-122">See also</span></span>
- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="ae27d-123">Traccia end-to-end</span><span class="sxs-lookup"><span data-stu-id="ae27d-123">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
