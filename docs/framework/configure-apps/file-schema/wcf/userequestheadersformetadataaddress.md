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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c538939a97e43239048853b5d6c32251d557d7e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="6f051-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="6f051-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="6f051-103">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="6f051-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="6f051-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6f051-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6f051-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="6f051-105">\<behaviors></span></span>  
<span data-ttu-id="6f051-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6f051-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6f051-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="6f051-107">\<behavior></span></span>  
<span data-ttu-id="6f051-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="6f051-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f051-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f051-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f051-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6f051-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6f051-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6f051-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f051-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="6f051-112">Attributes</span></span>  
 <span data-ttu-id="6f051-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6f051-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6f051-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6f051-114">Child Elements</span></span>  
  
|<span data-ttu-id="6f051-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f051-115">Element</span></span>|<span data-ttu-id="6f051-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f051-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f051-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="6f051-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="6f051-118">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="6f051-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6f051-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6f051-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6f051-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f051-120">Element</span></span>|<span data-ttu-id="6f051-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f051-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f051-122">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="6f051-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6f051-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="6f051-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f051-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f051-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
