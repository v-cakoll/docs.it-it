---
title: <add> di <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: d2723dad14a63c4b05fdb70157f7eb21d193d3ab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926701"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="abc5d-102">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="abc5d-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="abc5d-103">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="abc5d-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="abc5d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="abc5d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="abc5d-105">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="abc5d-105">\<behaviors></span></span>  
<span data-ttu-id="abc5d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="abc5d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="abc5d-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="abc5d-107">\<behavior></span></span>  
<span data-ttu-id="abc5d-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="abc5d-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="abc5d-109">\<> defaultPorts</span><span class="sxs-lookup"><span data-stu-id="abc5d-109">\<defaultPorts></span></span>  
<span data-ttu-id="abc5d-110">\<add></span><span class="sxs-lookup"><span data-stu-id="abc5d-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abc5d-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="abc5d-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abc5d-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="abc5d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="abc5d-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="abc5d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abc5d-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="abc5d-114">Attributes</span></span>  
  
|<span data-ttu-id="abc5d-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="abc5d-115">Attribute</span></span>|<span data-ttu-id="abc5d-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="abc5d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="abc5d-117">port</span><span class="sxs-lookup"><span data-stu-id="abc5d-117">port</span></span>|<span data-ttu-id="abc5d-118">Integer che specifica il numero della porta di comunicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="abc5d-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="abc5d-119">scheme</span><span class="sxs-lookup"><span data-stu-id="abc5d-119">scheme</span></span>|<span data-ttu-id="abc5d-120">Stringa che specifica il gruppo di impostazioni del protocollo associato a una porta di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="abc5d-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abc5d-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="abc5d-121">Child Elements</span></span>  
 <span data-ttu-id="abc5d-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="abc5d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="abc5d-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="abc5d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="abc5d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="abc5d-124">Element</span></span>|<span data-ttu-id="abc5d-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abc5d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="abc5d-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="abc5d-126">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="abc5d-127">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="abc5d-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="abc5d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abc5d-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
