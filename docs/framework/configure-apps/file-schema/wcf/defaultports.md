---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398065"
---
# <a name="defaultports"></a><span data-ttu-id="9c89d-101">\<> defaultPorts</span><span class="sxs-lookup"><span data-stu-id="9c89d-101">\<defaultPorts></span></span>
<span data-ttu-id="9c89d-102">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="9c89d-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="9c89d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9c89d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9c89d-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9c89d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9c89d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9c89d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9c89d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9c89d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="9c89d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9c89d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="9c89d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> useRequestHeadersForMetadataAddress**](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="9c89d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="9c89d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> defaultPorts**</span><span class="sxs-lookup"><span data-stu-id="9c89d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c89d-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c89d-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c89d-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9c89d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9c89d-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9c89d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c89d-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="9c89d-113">Attributes</span></span>  
 <span data-ttu-id="9c89d-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9c89d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c89d-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9c89d-115">Child Elements</span></span>  
  
|<span data-ttu-id="9c89d-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c89d-116">Element</span></span>|<span data-ttu-id="9c89d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c89d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c89d-118">\<aggiungere > di \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="9c89d-118">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="9c89d-119">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="9c89d-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c89d-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9c89d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9c89d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c89d-121">Element</span></span>|<span data-ttu-id="9c89d-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c89d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c89d-123">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="9c89d-123">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="9c89d-124">Elenco di porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="9c89d-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c89d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c89d-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
