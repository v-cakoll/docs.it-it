---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 6c03057fca23b037702c702b9a574045ebb302b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656627"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="a5511-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="a5511-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="a5511-103">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="a5511-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="a5511-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a5511-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a5511-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a5511-105">\<behaviors></span></span>  
<span data-ttu-id="a5511-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a5511-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a5511-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a5511-107">\<behavior></span></span>  
<span data-ttu-id="a5511-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="a5511-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5511-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5511-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5511-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a5511-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a5511-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a5511-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5511-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="a5511-112">Attributes</span></span>  
 <span data-ttu-id="a5511-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a5511-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a5511-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a5511-114">Child Elements</span></span>  
  
|<span data-ttu-id="a5511-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5511-115">Element</span></span>|<span data-ttu-id="a5511-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5511-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5511-117">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="a5511-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="a5511-118">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="a5511-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5511-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a5511-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a5511-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5511-120">Element</span></span>|<span data-ttu-id="a5511-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5511-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5511-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a5511-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a5511-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="a5511-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5511-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5511-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
