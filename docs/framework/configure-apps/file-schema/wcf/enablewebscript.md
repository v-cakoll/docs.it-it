---
title: '&lt;enableWebScript&gt;'
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: b14923c1b9a80bcd1c47db0e4fad6a6224b95329
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="eb849-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="eb849-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="eb849-103">Questo elemento attiva il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="eb849-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="eb849-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eb849-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb849-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="eb849-105">\<behaviors></span></span>  
<span data-ttu-id="eb849-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="eb849-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="eb849-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="eb849-107">\<behavior></span></span>  
<span data-ttu-id="eb849-108">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="eb849-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb849-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb849-109">Syntax</span></span>  
  
```xml  
<enableWebScript />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb849-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eb849-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eb849-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eb849-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb849-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="eb849-112">Attributes</span></span>  
 <span data-ttu-id="eb849-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="eb849-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb849-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eb849-114">Child Elements</span></span>  
 <span data-ttu-id="eb849-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="eb849-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb849-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eb849-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eb849-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb849-117">Element</span></span>|<span data-ttu-id="eb849-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb849-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb849-119">\<behavior></span><span class="sxs-lookup"><span data-stu-id="eb849-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="eb849-120">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="eb849-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb849-121">Note</span><span class="sxs-lookup"><span data-stu-id="eb849-121">Remarks</span></span>  
 <span data-ttu-id="eb849-122">Questo comportamento deve essere utilizzato solo in combinazione con il [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) associazione standard, o [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="eb849-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="eb849-123">Per altre informazioni su questo comportamento, vedere <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="eb849-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb849-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb849-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [<span data-ttu-id="eb849-125">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="eb849-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="eb849-126">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="eb849-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
