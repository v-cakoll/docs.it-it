---
title: '&lt;add&gt; di &lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 28ddc98bd66c1f74f857448aa710d3998ddbd3dc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="8a64c-102">&lt;add&gt; di &lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="8a64c-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="8a64c-103">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="8a64c-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="8a64c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8a64c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8a64c-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="8a64c-105">\<behaviors></span></span>  
<span data-ttu-id="8a64c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8a64c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8a64c-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="8a64c-107">\<behavior></span></span>  
<span data-ttu-id="8a64c-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="8a64c-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="8a64c-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="8a64c-109">\<defaultPorts></span></span>  
<span data-ttu-id="8a64c-110">\<add></span><span class="sxs-lookup"><span data-stu-id="8a64c-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a64c-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a64c-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a64c-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8a64c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8a64c-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8a64c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a64c-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="8a64c-114">Attributes</span></span>  
  
|<span data-ttu-id="8a64c-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="8a64c-115">Attribute</span></span>|<span data-ttu-id="8a64c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a64c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a64c-117">porta</span><span class="sxs-lookup"><span data-stu-id="8a64c-117">port</span></span>|<span data-ttu-id="8a64c-118">Integer che specifica il numero della porta di comunicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8a64c-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="8a64c-119">scheme</span><span class="sxs-lookup"><span data-stu-id="8a64c-119">scheme</span></span>|<span data-ttu-id="8a64c-120">Stringa che specifica il gruppo di impostazioni del protocollo associato a una porta di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="8a64c-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a64c-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8a64c-121">Child Elements</span></span>  
 <span data-ttu-id="8a64c-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8a64c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a64c-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8a64c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8a64c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a64c-124">Element</span></span>|<span data-ttu-id="8a64c-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a64c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a64c-126">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="8a64c-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="8a64c-127">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="8a64c-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a64c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a64c-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
