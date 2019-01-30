---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 595970a56e05c4fc1c9b2c0eb669ec3b3a120fe1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262383"
---
# <a name="defaultports"></a><span data-ttu-id="d8401-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="d8401-101">\<defaultPorts></span></span>
<span data-ttu-id="d8401-102">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="d8401-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="d8401-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d8401-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d8401-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d8401-104">\<behaviors></span></span>  
<span data-ttu-id="d8401-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="d8401-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="d8401-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d8401-106">\<behavior></span></span>  
<span data-ttu-id="d8401-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="d8401-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="d8401-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="d8401-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8401-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8401-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8401-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d8401-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d8401-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d8401-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8401-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d8401-112">Attributes</span></span>  
 <span data-ttu-id="d8401-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d8401-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8401-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d8401-114">Child Elements</span></span>  
  
|<span data-ttu-id="d8401-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8401-115">Element</span></span>|<span data-ttu-id="d8401-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8401-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8401-117">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="d8401-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="d8401-118">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="d8401-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8401-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d8401-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d8401-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8401-120">Element</span></span>|<span data-ttu-id="d8401-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8401-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8401-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="d8401-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="d8401-123">Elenco di porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="d8401-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8401-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8401-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
