---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855290"
---
# <a name="endtoendtracing"></a><span data-ttu-id="0ea3a-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="0ea3a-101">\<endToEndTracing></span></span>
<span data-ttu-id="0ea3a-102">Elemento di configurazione che consente di abilitare e disabilitare aspetti diversi di traccia end-to-end durante l'esecuzione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="0ea3a-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
<span data-ttu-id="0ea3a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ea3a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0ea3a-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0ea3a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0ea3a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di diagnostica**](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="0ea3a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="0ea3a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> endToEndTracing**</span><span class="sxs-lookup"><span data-stu-id="0ea3a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea3a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ea3a-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ea3a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0ea3a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0ea3a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0ea3a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ea3a-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0ea3a-110">Attributes</span></span>  
  
|<span data-ttu-id="0ea3a-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="0ea3a-111">Attribute</span></span>|<span data-ttu-id="0ea3a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ea3a-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="0ea3a-113">Valore booleano che specifica se è abilitata la traccia di attività.</span><span class="sxs-lookup"><span data-stu-id="0ea3a-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="0ea3a-114">Valore booleano che specifica se è abilitata la traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="0ea3a-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="0ea3a-115">Valore booleano che specifica se l'attributo di propagazione è impostato su true.</span><span class="sxs-lookup"><span data-stu-id="0ea3a-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ea3a-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0ea3a-116">Child Elements</span></span>  
 <span data-ttu-id="0ea3a-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0ea3a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ea3a-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0ea3a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0ea3a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ea3a-119">Element</span></span>|<span data-ttu-id="0ea3a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ea3a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ea3a-121">\<> di diagnostica</span><span class="sxs-lookup"><span data-stu-id="0ea3a-121">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="0ea3a-122">Definisce le impostazioni WCF per l'ispezione e il controllo in fase di esecuzione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="0ea3a-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ea3a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ea3a-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="0ea3a-124">Traccia end-to-end</span><span class="sxs-lookup"><span data-stu-id="0ea3a-124">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
