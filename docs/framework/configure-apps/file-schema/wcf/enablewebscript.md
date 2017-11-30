---
title: '&lt;enableWebScript&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cfb6981947b457d5fdad59e96bdcd6937b9abd02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="375b4-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="375b4-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="375b4-103">Questo elemento attiva il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="375b4-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="375b4-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="375b4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="375b4-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="375b4-105">\<behaviors></span></span>  
<span data-ttu-id="375b4-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="375b4-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="375b4-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="375b4-107">\<behavior></span></span>  
<span data-ttu-id="375b4-108">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="375b4-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="375b4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="375b4-109">Syntax</span></span>  
  
```xml  
<enableWebScript />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="375b4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="375b4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="375b4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="375b4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="375b4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="375b4-112">Attributes</span></span>  
 <span data-ttu-id="375b4-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="375b4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="375b4-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="375b4-114">Child Elements</span></span>  
 <span data-ttu-id="375b4-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="375b4-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="375b4-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="375b4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="375b4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="375b4-117">Element</span></span>|<span data-ttu-id="375b4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="375b4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="375b4-119">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="375b4-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="375b4-120">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="375b4-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="375b4-121">Note</span><span class="sxs-lookup"><span data-stu-id="375b4-121">Remarks</span></span>  
 <span data-ttu-id="375b4-122">Questo comportamento deve essere utilizzato solo in combinazione con il [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) associazione standard, o [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="375b4-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="375b4-123">Per altre informazioni su questo comportamento, vedere <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="375b4-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="375b4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="375b4-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [<span data-ttu-id="375b4-125">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="375b4-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="375b4-126">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="375b4-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
