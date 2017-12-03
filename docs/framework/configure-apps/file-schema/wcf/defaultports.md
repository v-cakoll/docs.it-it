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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1886f6efdfaa8f4105e6ef16ad72093867e0f3fe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="4f163-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="4f163-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="4f163-103">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="4f163-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="4f163-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4f163-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4f163-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="4f163-105">\<behaviors></span></span>  
<span data-ttu-id="4f163-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4f163-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4f163-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="4f163-107">\<behavior></span></span>  
<span data-ttu-id="4f163-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="4f163-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="4f163-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="4f163-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f163-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f163-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f163-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4f163-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4f163-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4f163-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f163-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="4f163-113">Attributes</span></span>  
 <span data-ttu-id="4f163-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4f163-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4f163-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4f163-115">Child Elements</span></span>  
  
|<span data-ttu-id="4f163-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f163-116">Element</span></span>|<span data-ttu-id="4f163-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f163-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f163-118">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="4f163-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="4f163-119">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="4f163-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f163-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4f163-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4f163-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f163-121">Element</span></span>|<span data-ttu-id="4f163-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f163-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f163-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="4f163-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="4f163-124">Elenco di porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="4f163-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f163-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f163-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
