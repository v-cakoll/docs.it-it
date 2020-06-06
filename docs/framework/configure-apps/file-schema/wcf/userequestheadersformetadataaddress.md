---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399197"
---
# \<useRequestHeadersForMetadataAddress>
<span data-ttu-id="1f8a5-101">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="1f8a5-101">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="1f8a5-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f8a5-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f8a5-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1f8a5-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1f8a5-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1f8a5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f8a5-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="1f8a5-105">Attributes</span></span>  
 <span data-ttu-id="1f8a5-106">No.</span><span class="sxs-lookup"><span data-stu-id="1f8a5-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1f8a5-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1f8a5-107">Child Elements</span></span>  
  
|<span data-ttu-id="1f8a5-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f8a5-108">Element</span></span>|<span data-ttu-id="1f8a5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f8a5-109">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="1f8a5-110">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="1f8a5-110">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f8a5-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1f8a5-111">Parent Elements</span></span>  
  
|<span data-ttu-id="1f8a5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f8a5-112">Element</span></span>|<span data-ttu-id="1f8a5-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f8a5-113">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1f8a5-114">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="1f8a5-114">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1f8a5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f8a5-115">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
