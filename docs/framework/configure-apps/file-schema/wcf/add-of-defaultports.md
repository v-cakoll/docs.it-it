---
title: '&lt;add&gt; di &lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 0932ef9afacb6278c4857dcfd6ba545595ff8f9d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147720"
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="e4002-102">&lt;add&gt; di &lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="e4002-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="e4002-103">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="e4002-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="e4002-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e4002-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e4002-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="e4002-105">\<behaviors></span></span>  
<span data-ttu-id="e4002-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e4002-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e4002-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="e4002-107">\<behavior></span></span>  
<span data-ttu-id="e4002-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="e4002-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="e4002-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="e4002-109">\<defaultPorts></span></span>  
<span data-ttu-id="e4002-110">\<add></span><span class="sxs-lookup"><span data-stu-id="e4002-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4002-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4002-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4002-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e4002-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e4002-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e4002-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4002-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="e4002-114">Attributes</span></span>  
  
|<span data-ttu-id="e4002-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="e4002-115">Attribute</span></span>|<span data-ttu-id="e4002-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4002-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4002-117">porta</span><span class="sxs-lookup"><span data-stu-id="e4002-117">port</span></span>|<span data-ttu-id="e4002-118">Integer che specifica il numero della porta di comunicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e4002-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="e4002-119">scheme</span><span class="sxs-lookup"><span data-stu-id="e4002-119">scheme</span></span>|<span data-ttu-id="e4002-120">Stringa che specifica il gruppo di impostazioni del protocollo associato a una porta di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="e4002-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4002-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e4002-121">Child Elements</span></span>  
 <span data-ttu-id="e4002-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e4002-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4002-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e4002-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e4002-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4002-124">Element</span></span>|<span data-ttu-id="e4002-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4002-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4002-126">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="e4002-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="e4002-127">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="e4002-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4002-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4002-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
