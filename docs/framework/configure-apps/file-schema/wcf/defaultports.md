---
title: '&lt;defaultPorts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0e127935977795181411dfa6b03d8b09fe88e0f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="c36e8-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="c36e8-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="c36e8-103">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="c36e8-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="c36e8-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c36e8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c36e8-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="c36e8-105">\<behaviors></span></span>  
<span data-ttu-id="c36e8-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c36e8-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c36e8-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="c36e8-107">\<behavior></span></span>  
<span data-ttu-id="c36e8-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="c36e8-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="c36e8-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="c36e8-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36e8-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c36e8-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c36e8-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c36e8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c36e8-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c36e8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c36e8-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="c36e8-113">Attributes</span></span>  
 <span data-ttu-id="c36e8-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c36e8-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c36e8-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c36e8-115">Child Elements</span></span>  
  
|<span data-ttu-id="c36e8-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c36e8-116">Element</span></span>|<span data-ttu-id="c36e8-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c36e8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c36e8-118">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="c36e8-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="c36e8-119">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="c36e8-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c36e8-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c36e8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c36e8-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c36e8-121">Element</span></span>|<span data-ttu-id="c36e8-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c36e8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c36e8-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="c36e8-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="c36e8-124">Elenco di porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="c36e8-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c36e8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c36e8-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
