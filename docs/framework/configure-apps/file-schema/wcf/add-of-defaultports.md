---
title: <add> di <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 5200c8893a89488b72c2c71d1a3703bf2aad1235
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704557"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="32b49-102">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="32b49-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="32b49-103">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="32b49-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="32b49-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="32b49-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="32b49-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="32b49-105">\<behaviors></span></span>  
<span data-ttu-id="32b49-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="32b49-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="32b49-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="32b49-107">\<behavior></span></span>  
<span data-ttu-id="32b49-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="32b49-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="32b49-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="32b49-109">\<defaultPorts></span></span>  
<span data-ttu-id="32b49-110">\<add></span><span class="sxs-lookup"><span data-stu-id="32b49-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b49-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32b49-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32b49-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="32b49-112">Attributes and Elements</span></span>  
 <span data-ttu-id="32b49-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="32b49-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32b49-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="32b49-114">Attributes</span></span>  
  
|<span data-ttu-id="32b49-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="32b49-115">Attribute</span></span>|<span data-ttu-id="32b49-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32b49-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32b49-117">porta</span><span class="sxs-lookup"><span data-stu-id="32b49-117">port</span></span>|<span data-ttu-id="32b49-118">Integer che specifica il numero della porta di comunicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="32b49-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="32b49-119">scheme</span><span class="sxs-lookup"><span data-stu-id="32b49-119">scheme</span></span>|<span data-ttu-id="32b49-120">Stringa che specifica il gruppo di impostazioni del protocollo associato a una porta di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="32b49-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32b49-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="32b49-121">Child Elements</span></span>  
 <span data-ttu-id="32b49-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="32b49-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32b49-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="32b49-123">Parent Elements</span></span>  
  
|<span data-ttu-id="32b49-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="32b49-124">Element</span></span>|<span data-ttu-id="32b49-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32b49-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32b49-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="32b49-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="32b49-127">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="32b49-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32b49-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32b49-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
