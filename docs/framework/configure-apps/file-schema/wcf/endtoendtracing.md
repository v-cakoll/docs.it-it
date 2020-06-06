---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855290"
---
# \<endToEndTracing>
<span data-ttu-id="38a51-101">Elemento di configurazione che consente di abilitare e disabilitare aspetti diversi di traccia end-to-end durante l'esecuzione di un'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="38a51-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="38a51-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38a51-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38a51-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="38a51-103">Attributes and Elements</span></span>  
 <span data-ttu-id="38a51-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="38a51-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38a51-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="38a51-105">Attributes</span></span>  
  
|<span data-ttu-id="38a51-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="38a51-106">Attribute</span></span>|<span data-ttu-id="38a51-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38a51-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="38a51-108">Valore booleano che specifica se è abilitata la traccia di attività.</span><span class="sxs-lookup"><span data-stu-id="38a51-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="38a51-109">Valore booleano che specifica se è abilitata la traccia del flusso di messaggi.</span><span class="sxs-lookup"><span data-stu-id="38a51-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="38a51-110">Valore booleano che specifica se l'attributo di propagazione è impostato su true.</span><span class="sxs-lookup"><span data-stu-id="38a51-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38a51-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="38a51-111">Child Elements</span></span>  
 <span data-ttu-id="38a51-112">No.</span><span class="sxs-lookup"><span data-stu-id="38a51-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38a51-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="38a51-113">Parent Elements</span></span>  
  
|<span data-ttu-id="38a51-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="38a51-114">Element</span></span>|<span data-ttu-id="38a51-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38a51-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="38a51-116">Definisce le impostazioni WCF per l'ispezione e il controllo in fase di esecuzione da parte dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="38a51-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38a51-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="38a51-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="38a51-118">Traccia end-to-end</span><span class="sxs-lookup"><span data-stu-id="38a51-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
