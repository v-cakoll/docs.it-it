---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212102"
---
# <a name="baseaddresses"></a><span data-ttu-id="0ee69-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="0ee69-101">\<baseAddresses></span></span>
<span data-ttu-id="0ee69-102">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="0ee69-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="0ee69-103">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="0ee69-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="0ee69-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0ee69-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0ee69-105">\<client></span><span class="sxs-lookup"><span data-stu-id="0ee69-105">\<client></span></span>  
<span data-ttu-id="0ee69-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="0ee69-106">\<endpoint></span></span>  
<span data-ttu-id="0ee69-107">\<host></span><span class="sxs-lookup"><span data-stu-id="0ee69-107">\<host></span></span>  
<span data-ttu-id="0ee69-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="0ee69-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee69-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ee69-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="0ee69-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="0ee69-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ee69-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0ee69-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0ee69-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0ee69-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ee69-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="0ee69-113">Attributes</span></span>  
 <span data-ttu-id="0ee69-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0ee69-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ee69-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0ee69-115">Child Elements</span></span>  
  
|<span data-ttu-id="0ee69-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ee69-116">Element</span></span>|<span data-ttu-id="0ee69-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ee69-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ee69-118">\<add></span><span class="sxs-lookup"><span data-stu-id="0ee69-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="0ee69-119">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="0ee69-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ee69-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0ee69-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0ee69-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ee69-121">Element</span></span>|<span data-ttu-id="0ee69-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ee69-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ee69-123">\<host></span><span class="sxs-lookup"><span data-stu-id="0ee69-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="0ee69-124">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="0ee69-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ee69-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ee69-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="0ee69-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="0ee69-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
