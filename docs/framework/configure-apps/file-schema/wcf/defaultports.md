---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925881"
---
# <a name="defaultports"></a><span data-ttu-id="fa299-101">\<> defaultPorts</span><span class="sxs-lookup"><span data-stu-id="fa299-101">\<defaultPorts></span></span>
<span data-ttu-id="fa299-102">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="fa299-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="fa299-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fa299-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fa299-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="fa299-104">\<behaviors></span></span>  
<span data-ttu-id="fa299-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fa299-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="fa299-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="fa299-106">\<behavior></span></span>  
<span data-ttu-id="fa299-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="fa299-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="fa299-108">\<> defaultPorts</span><span class="sxs-lookup"><span data-stu-id="fa299-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa299-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa299-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa299-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fa299-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa299-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fa299-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa299-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="fa299-112">Attributes</span></span>  
 <span data-ttu-id="fa299-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fa299-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa299-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fa299-114">Child Elements</span></span>  
  
|<span data-ttu-id="fa299-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa299-115">Element</span></span>|<span data-ttu-id="fa299-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa299-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa299-117">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="fa299-117">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="fa299-118">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="fa299-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa299-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fa299-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fa299-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa299-120">Element</span></span>|<span data-ttu-id="fa299-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="fa299-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa299-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="fa299-122">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="fa299-123">Elenco di porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="fa299-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa299-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa299-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
