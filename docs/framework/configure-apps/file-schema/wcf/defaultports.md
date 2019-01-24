---
title: '&lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 2c742f98315c0e497ac4117953424bae913cb5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614497"
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="39480-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="39480-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="39480-103">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="39480-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="39480-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="39480-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="39480-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="39480-105">\<behaviors></span></span>  
<span data-ttu-id="39480-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="39480-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="39480-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="39480-107">\<behavior></span></span>  
<span data-ttu-id="39480-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="39480-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="39480-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="39480-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39480-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39480-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39480-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="39480-111">Attributes and Elements</span></span>  
 <span data-ttu-id="39480-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="39480-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39480-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="39480-113">Attributes</span></span>  
 <span data-ttu-id="39480-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="39480-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39480-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="39480-115">Child Elements</span></span>  
  
|<span data-ttu-id="39480-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="39480-116">Element</span></span>|<span data-ttu-id="39480-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39480-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39480-118">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="39480-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="39480-119">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="39480-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39480-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="39480-120">Parent Elements</span></span>  
  
|<span data-ttu-id="39480-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="39480-121">Element</span></span>|<span data-ttu-id="39480-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39480-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39480-123">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="39480-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="39480-124">Elenco di porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="39480-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39480-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39480-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
