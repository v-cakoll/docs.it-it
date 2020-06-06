---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850216"
---
# \<baseAddresses>
<span data-ttu-id="f17fb-101">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="f17fb-101">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="f17fb-102">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="f17fb-102">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="f17fb-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f17fb-103">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="f17fb-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="f17fb-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f17fb-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f17fb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f17fb-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f17fb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f17fb-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f17fb-107">Attributes</span></span>  
 <span data-ttu-id="f17fb-108">No.</span><span class="sxs-lookup"><span data-stu-id="f17fb-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f17fb-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f17fb-109">Child Elements</span></span>  
  
|<span data-ttu-id="f17fb-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="f17fb-110">Element</span></span>|<span data-ttu-id="f17fb-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f17fb-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="f17fb-112">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f17fb-112">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f17fb-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f17fb-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f17fb-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f17fb-114">Element</span></span>|<span data-ttu-id="f17fb-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f17fb-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="f17fb-116">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f17fb-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f17fb-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f17fb-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="f17fb-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="f17fb-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
