---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 94dafcfa68463a0e82696cf16a96abe45632e72a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="4d267-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="4d267-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="4d267-103">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="4d267-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="4d267-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4d267-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4d267-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="4d267-105">\<behaviors></span></span>  
<span data-ttu-id="4d267-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4d267-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4d267-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="4d267-107">\<behavior></span></span>  
<span data-ttu-id="4d267-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="4d267-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d267-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d267-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d267-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d267-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4d267-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d267-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d267-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d267-112">Attributes</span></span>  
 <span data-ttu-id="4d267-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4d267-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4d267-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d267-114">Child Elements</span></span>  
  
|<span data-ttu-id="4d267-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d267-115">Element</span></span>|<span data-ttu-id="4d267-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d267-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d267-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="4d267-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="4d267-118">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="4d267-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4d267-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d267-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4d267-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d267-120">Element</span></span>|<span data-ttu-id="4d267-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d267-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d267-122">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="4d267-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4d267-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="4d267-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d267-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d267-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
