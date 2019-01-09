---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: bcbf1c633e0796c6056759dfbb55014838e0e293
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151410"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="4e67d-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="4e67d-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="4e67d-103">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="4e67d-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="4e67d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4e67d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4e67d-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="4e67d-105">\<behaviors></span></span>  
<span data-ttu-id="4e67d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4e67d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4e67d-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="4e67d-107">\<behavior></span></span>  
<span data-ttu-id="4e67d-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="4e67d-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e67d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e67d-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e67d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4e67d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4e67d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4e67d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e67d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4e67d-112">Attributes</span></span>  
 <span data-ttu-id="4e67d-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4e67d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e67d-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4e67d-114">Child Elements</span></span>  
  
|<span data-ttu-id="4e67d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e67d-115">Element</span></span>|<span data-ttu-id="4e67d-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e67d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e67d-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="4e67d-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="4e67d-118">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="4e67d-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e67d-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4e67d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4e67d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e67d-120">Element</span></span>|<span data-ttu-id="4e67d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e67d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e67d-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4e67d-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4e67d-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="4e67d-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e67d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e67d-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
