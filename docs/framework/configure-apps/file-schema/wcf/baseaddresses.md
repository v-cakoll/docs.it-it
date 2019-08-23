---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 059ea4e637ab906d1fde9807a73ac8341f81c574
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926415"
---
# <a name="baseaddresses"></a><span data-ttu-id="f63f5-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="f63f5-101">\<baseAddresses></span></span>
<span data-ttu-id="f63f5-102">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="f63f5-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="f63f5-103">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="f63f5-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="f63f5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f63f5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f63f5-105">\<client></span><span class="sxs-lookup"><span data-stu-id="f63f5-105">\<client></span></span>  
<span data-ttu-id="f63f5-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="f63f5-106">\<endpoint></span></span>  
<span data-ttu-id="f63f5-107">\<> host</span><span class="sxs-lookup"><span data-stu-id="f63f5-107">\<host></span></span>  
<span data-ttu-id="f63f5-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="f63f5-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f63f5-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f63f5-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="f63f5-110">Type</span><span class="sxs-lookup"><span data-stu-id="f63f5-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f63f5-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f63f5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f63f5-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f63f5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f63f5-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f63f5-113">Attributes</span></span>  
 <span data-ttu-id="f63f5-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f63f5-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f63f5-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f63f5-115">Child Elements</span></span>  
  
|<span data-ttu-id="f63f5-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f63f5-116">Element</span></span>|<span data-ttu-id="f63f5-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f63f5-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f63f5-118">\<add></span><span class="sxs-lookup"><span data-stu-id="f63f5-118">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="f63f5-119">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f63f5-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f63f5-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f63f5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f63f5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f63f5-121">Element</span></span>|<span data-ttu-id="f63f5-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f63f5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f63f5-123">\<host></span><span class="sxs-lookup"><span data-stu-id="f63f5-123">\<host></span></span>](host.md)|<span data-ttu-id="f63f5-124">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f63f5-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f63f5-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f63f5-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="f63f5-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="f63f5-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
