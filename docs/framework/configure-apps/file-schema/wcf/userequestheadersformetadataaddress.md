---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 7e661570f8b94b979595a615b3f6819d41ed5e35
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766699"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="ced29-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="ced29-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="ced29-103">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="ced29-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="ced29-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ced29-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ced29-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="ced29-105">\<behaviors></span></span>  
<span data-ttu-id="ced29-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ced29-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ced29-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="ced29-107">\<behavior></span></span>  
<span data-ttu-id="ced29-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="ced29-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ced29-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ced29-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ced29-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ced29-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ced29-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ced29-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ced29-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="ced29-112">Attributes</span></span>  
 <span data-ttu-id="ced29-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ced29-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ced29-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ced29-114">Child Elements</span></span>  
  
|<span data-ttu-id="ced29-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ced29-115">Element</span></span>|<span data-ttu-id="ced29-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ced29-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ced29-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="ced29-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="ced29-118">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="ced29-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ced29-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ced29-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ced29-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ced29-120">Element</span></span>|<span data-ttu-id="ced29-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ced29-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ced29-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ced29-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ced29-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="ced29-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ced29-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ced29-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
