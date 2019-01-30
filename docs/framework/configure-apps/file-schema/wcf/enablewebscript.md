---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 9c9bbb9ccc7879510ae3e2bee2fabd604fd52f65
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266650"
---
# <a name="enablewebscript"></a><span data-ttu-id="92723-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="92723-101">\<enableWebScript></span></span>
<span data-ttu-id="92723-102">Questo elemento attiva il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="92723-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="92723-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="92723-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="92723-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="92723-104">\<behaviors></span></span>  
<span data-ttu-id="92723-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="92723-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="92723-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="92723-106">\<behavior></span></span>  
<span data-ttu-id="92723-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="92723-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92723-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92723-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92723-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="92723-109">Attributes and Elements</span></span>  
 <span data-ttu-id="92723-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="92723-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92723-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="92723-111">Attributes</span></span>  
 <span data-ttu-id="92723-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="92723-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="92723-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="92723-113">Child Elements</span></span>  
 <span data-ttu-id="92723-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="92723-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92723-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="92723-115">Parent Elements</span></span>  
  
|<span data-ttu-id="92723-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="92723-116">Element</span></span>|<span data-ttu-id="92723-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92723-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92723-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="92723-118">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="92723-119">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="92723-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92723-120">Note</span><span class="sxs-lookup"><span data-stu-id="92723-120">Remarks</span></span>  
 <span data-ttu-id="92723-121">Questo comportamento deve essere usato solo in combinazione con il [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) associazione standard, o il [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="92723-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="92723-122">Per altre informazioni su questo comportamento, vedere <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="92723-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92723-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92723-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="92723-124">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="92723-124">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="92723-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="92723-125">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
