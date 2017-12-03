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
ms.openlocfilehash: 1e7f69da871376f83422fb330f8babd56bb1fdcb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="2af5e-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="2af5e-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="2af5e-103">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="2af5e-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="2af5e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2af5e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2af5e-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="2af5e-105">\<behaviors></span></span>  
<span data-ttu-id="2af5e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2af5e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="2af5e-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="2af5e-107">\<behavior></span></span>  
<span data-ttu-id="2af5e-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="2af5e-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af5e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2af5e-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2af5e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2af5e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2af5e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2af5e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2af5e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2af5e-112">Attributes</span></span>  
 <span data-ttu-id="2af5e-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2af5e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2af5e-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2af5e-114">Child Elements</span></span>  
  
|<span data-ttu-id="2af5e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2af5e-115">Element</span></span>|<span data-ttu-id="2af5e-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2af5e-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2af5e-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="2af5e-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="2af5e-118">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="2af5e-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2af5e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2af5e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2af5e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2af5e-120">Element</span></span>|<span data-ttu-id="2af5e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2af5e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2af5e-122">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="2af5e-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2af5e-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="2af5e-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2af5e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2af5e-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
