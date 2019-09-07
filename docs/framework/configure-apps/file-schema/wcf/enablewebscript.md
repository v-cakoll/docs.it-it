---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400379"
---
# <a name="enablewebscript"></a><span data-ttu-id="af618-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="af618-101">\<enableWebScript></span></span>
<span data-ttu-id="af618-102">Questo elemento attiva il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="af618-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
<span data-ttu-id="af618-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af618-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af618-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="af618-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="af618-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="af618-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="af618-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="af618-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="af618-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="af618-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="af618-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> enableWebScript**</span><span class="sxs-lookup"><span data-stu-id="af618-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af618-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af618-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af618-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="af618-110">Attributes and Elements</span></span>  
 <span data-ttu-id="af618-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="af618-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af618-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="af618-112">Attributes</span></span>  
 <span data-ttu-id="af618-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="af618-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af618-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="af618-114">Child Elements</span></span>  
 <span data-ttu-id="af618-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="af618-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af618-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="af618-116">Parent Elements</span></span>  
  
|<span data-ttu-id="af618-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="af618-117">Element</span></span>|<span data-ttu-id="af618-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af618-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af618-119">\<behavior></span><span class="sxs-lookup"><span data-stu-id="af618-119">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="af618-120">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="af618-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af618-121">Note</span><span class="sxs-lookup"><span data-stu-id="af618-121">Remarks</span></span>  
 <span data-ttu-id="af618-122">Questo comportamento deve essere usato solo in combinazione con l' [ \<associazione WebHttpBinding >](webhttpbinding.md) standard o con l' [ \<](webmessageencoding.md) elemento di associazione > webMessageEncoding.</span><span class="sxs-lookup"><span data-stu-id="af618-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="af618-123">Per altre informazioni su questo comportamento, vedere <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="af618-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af618-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af618-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="af618-125">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="af618-125">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="af618-126">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="af618-126">\<webHttp></span></span>](webhttp.md)
