---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 123f58ee3d77bf605db21fa0d9537b3196d56468
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919119"
---
# <a name="enablewebscript"></a><span data-ttu-id="5d78f-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="5d78f-101">\<enableWebScript></span></span>
<span data-ttu-id="5d78f-102">Questo elemento attiva il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="5d78f-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="5d78f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5d78f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d78f-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="5d78f-104">\<behaviors></span></span>  
<span data-ttu-id="5d78f-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5d78f-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="5d78f-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="5d78f-106">\<behavior></span></span>  
<span data-ttu-id="5d78f-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="5d78f-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d78f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d78f-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d78f-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5d78f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5d78f-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5d78f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d78f-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="5d78f-111">Attributes</span></span>  
 <span data-ttu-id="5d78f-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5d78f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d78f-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5d78f-113">Child Elements</span></span>  
 <span data-ttu-id="5d78f-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5d78f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d78f-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5d78f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="5d78f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d78f-116">Element</span></span>|<span data-ttu-id="5d78f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d78f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d78f-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5d78f-118">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5d78f-119">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5d78f-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d78f-120">Note</span><span class="sxs-lookup"><span data-stu-id="5d78f-120">Remarks</span></span>  
 <span data-ttu-id="5d78f-121">Questo comportamento deve essere usato solo in combinazione con l' [ \<associazione WebHttpBinding >](webhttpbinding.md) standard o con l' [ \<](webmessageencoding.md) elemento di associazione > webMessageEncoding.</span><span class="sxs-lookup"><span data-stu-id="5d78f-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="5d78f-122">Per altre informazioni su questo comportamento, vedere <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5d78f-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d78f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d78f-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="5d78f-124">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="5d78f-124">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="5d78f-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="5d78f-125">\<webHttp></span></span>](webhttp.md)
