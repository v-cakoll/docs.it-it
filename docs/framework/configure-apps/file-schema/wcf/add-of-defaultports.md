---
title: '&lt;add&gt; di &lt;defaultPorts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2aa63c7a5e730b2fb45f614cb2fe5f88444cee4a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="e8999-102">&lt;add&gt; di &lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="e8999-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="e8999-103">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="e8999-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="e8999-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e8999-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8999-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="e8999-105">\<behaviors></span></span>  
<span data-ttu-id="e8999-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e8999-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e8999-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="e8999-107">\<behavior></span></span>  
<span data-ttu-id="e8999-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="e8999-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="e8999-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="e8999-109">\<defaultPorts></span></span>  
<span data-ttu-id="e8999-110">\<add></span><span class="sxs-lookup"><span data-stu-id="e8999-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8999-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8999-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8999-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e8999-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e8999-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e8999-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8999-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="e8999-114">Attributes</span></span>  
  
|<span data-ttu-id="e8999-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="e8999-115">Attribute</span></span>|<span data-ttu-id="e8999-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8999-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8999-117">porta</span><span class="sxs-lookup"><span data-stu-id="e8999-117">port</span></span>|<span data-ttu-id="e8999-118">Integer che specifica il numero della porta di comunicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e8999-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="e8999-119">scheme</span><span class="sxs-lookup"><span data-stu-id="e8999-119">scheme</span></span>|<span data-ttu-id="e8999-120">Stringa che specifica il gruppo di impostazioni del protocollo associato a una porta di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="e8999-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8999-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8999-121">Child Elements</span></span>  
 <span data-ttu-id="e8999-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e8999-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8999-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e8999-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e8999-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8999-124">Element</span></span>|<span data-ttu-id="e8999-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8999-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8999-126">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="e8999-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="e8999-127">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="e8999-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8999-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8999-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
