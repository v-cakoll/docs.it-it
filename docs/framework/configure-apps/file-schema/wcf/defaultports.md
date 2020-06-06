---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398065"
---
# \<defaultPorts>
<span data-ttu-id="ca5d8-101">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-101">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="ca5d8-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca5d8-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca5d8-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ca5d8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ca5d8-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca5d8-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="ca5d8-105">Attributes</span></span>  
 <span data-ttu-id="ca5d8-106">No.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ca5d8-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ca5d8-107">Child Elements</span></span>  
  
|<span data-ttu-id="ca5d8-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca5d8-108">Element</span></span>|<span data-ttu-id="ca5d8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca5d8-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca5d8-110">\<add>di\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="ca5d8-110">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="ca5d8-111">Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-111">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ca5d8-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ca5d8-112">Parent Elements</span></span>  
  
|<span data-ttu-id="ca5d8-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca5d8-113">Element</span></span>|<span data-ttu-id="ca5d8-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca5d8-114">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="ca5d8-115">Elenco di porte predefinite.</span><span class="sxs-lookup"><span data-stu-id="ca5d8-115">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca5d8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca5d8-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
