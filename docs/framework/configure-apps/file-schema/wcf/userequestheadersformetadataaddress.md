---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399197"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="f03c1-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="f03c1-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="f03c1-102">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="f03c1-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="f03c1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f03c1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f03c1-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f03c1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f03c1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f03c1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f03c1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f03c1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="f03c1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f03c1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="f03c1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> useRequestHeadersForMetadataAddress**</span><span class="sxs-lookup"><span data-stu-id="f03c1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03c1-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f03c1-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f03c1-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f03c1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f03c1-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f03c1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f03c1-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f03c1-112">Attributes</span></span>  
 <span data-ttu-id="f03c1-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f03c1-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f03c1-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f03c1-114">Child Elements</span></span>  
  
|<span data-ttu-id="f03c1-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f03c1-115">Element</span></span>|<span data-ttu-id="f03c1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f03c1-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f03c1-117">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="f03c1-117">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="f03c1-118">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="f03c1-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f03c1-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f03c1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f03c1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f03c1-120">Element</span></span>|<span data-ttu-id="f03c1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f03c1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f03c1-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f03c1-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f03c1-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="f03c1-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f03c1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f03c1-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
