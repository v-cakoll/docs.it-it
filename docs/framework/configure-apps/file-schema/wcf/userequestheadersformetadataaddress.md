---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 84310d4ae5e04e76e4484f4fc606c9896239c776
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940557"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="fb258-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="fb258-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="fb258-102">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="fb258-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="fb258-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fb258-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fb258-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="fb258-104">\<behaviors></span></span>  
<span data-ttu-id="fb258-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fb258-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="fb258-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="fb258-106">\<behavior></span></span>  
<span data-ttu-id="fb258-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="fb258-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb258-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb258-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb258-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fb258-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fb258-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fb258-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb258-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="fb258-111">Attributes</span></span>  
 <span data-ttu-id="fb258-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fb258-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb258-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fb258-113">Child Elements</span></span>  
  
|<span data-ttu-id="fb258-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb258-114">Element</span></span>|<span data-ttu-id="fb258-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="fb258-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb258-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="fb258-116">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="fb258-117">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="fb258-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb258-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fb258-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fb258-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb258-119">Element</span></span>|<span data-ttu-id="fb258-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb258-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb258-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fb258-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="fb258-122">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="fb258-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb258-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb258-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
