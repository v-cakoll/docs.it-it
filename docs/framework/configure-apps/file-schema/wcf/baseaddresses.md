---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850216"
---
# <a name="baseaddresses"></a><span data-ttu-id="bd746-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="bd746-101">\<baseAddresses></span></span>
<span data-ttu-id="bd746-102">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="bd746-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="bd746-103">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="bd746-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
<span data-ttu-id="bd746-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd746-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bd746-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bd746-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bd746-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dei servizi**](services.md)</span><span class="sxs-lookup"><span data-stu-id="bd746-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="bd746-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> del servizio**](service.md)</span><span class="sxs-lookup"><span data-stu-id="bd746-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="bd746-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> host**](host.md)</span><span class="sxs-lookup"><span data-stu-id="bd746-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="bd746-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> baseAddresses**</span><span class="sxs-lookup"><span data-stu-id="bd746-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd746-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd746-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="bd746-111">Type</span><span class="sxs-lookup"><span data-stu-id="bd746-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd746-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bd746-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bd746-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bd746-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd746-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="bd746-114">Attributes</span></span>  
 <span data-ttu-id="bd746-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bd746-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd746-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bd746-116">Child Elements</span></span>  
  
|<span data-ttu-id="bd746-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd746-117">Element</span></span>|<span data-ttu-id="bd746-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd746-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd746-119">\<add></span><span class="sxs-lookup"><span data-stu-id="bd746-119">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="bd746-120">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="bd746-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd746-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bd746-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bd746-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd746-122">Element</span></span>|<span data-ttu-id="bd746-123">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="bd746-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd746-124">\<host></span><span class="sxs-lookup"><span data-stu-id="bd746-124">\<host></span></span>](host.md)|<span data-ttu-id="bd746-125">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="bd746-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd746-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd746-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="bd746-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="bd746-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
