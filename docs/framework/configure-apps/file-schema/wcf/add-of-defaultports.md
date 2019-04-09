---
title: <add> di <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 5200c8893a89488b72c2c71d1a3703bf2aad1235
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136747"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="5be17-102">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="5be17-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="5be17-103">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="5be17-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="5be17-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5be17-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5be17-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5be17-105">\<behaviors></span></span>  
<span data-ttu-id="5be17-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5be17-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5be17-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5be17-107">\<behavior></span></span>  
<span data-ttu-id="5be17-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="5be17-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="5be17-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="5be17-109">\<defaultPorts></span></span>  
<span data-ttu-id="5be17-110">\<add></span><span class="sxs-lookup"><span data-stu-id="5be17-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be17-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5be17-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5be17-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5be17-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5be17-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5be17-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5be17-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="5be17-114">Attributes</span></span>  
  
|<span data-ttu-id="5be17-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="5be17-115">Attribute</span></span>|<span data-ttu-id="5be17-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5be17-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5be17-117">porta</span><span class="sxs-lookup"><span data-stu-id="5be17-117">port</span></span>|<span data-ttu-id="5be17-118">Integer che specifica il numero della porta di comunicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5be17-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="5be17-119">scheme</span><span class="sxs-lookup"><span data-stu-id="5be17-119">scheme</span></span>|<span data-ttu-id="5be17-120">Stringa che specifica il gruppo di impostazioni del protocollo associato a una porta di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="5be17-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5be17-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5be17-121">Child Elements</span></span>  
 <span data-ttu-id="5be17-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5be17-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5be17-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5be17-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5be17-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5be17-124">Element</span></span>|<span data-ttu-id="5be17-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5be17-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5be17-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="5be17-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="5be17-127">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="5be17-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5be17-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5be17-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
