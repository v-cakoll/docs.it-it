---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673524"
---
# <a name="baseaddresses"></a><span data-ttu-id="e413a-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="e413a-101">\<baseAddresses></span></span>
<span data-ttu-id="e413a-102">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="e413a-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="e413a-103">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="e413a-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="e413a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e413a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e413a-105">\<client></span><span class="sxs-lookup"><span data-stu-id="e413a-105">\<client></span></span>  
<span data-ttu-id="e413a-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="e413a-106">\<endpoint></span></span>  
<span data-ttu-id="e413a-107">\<host></span><span class="sxs-lookup"><span data-stu-id="e413a-107">\<host></span></span>  
<span data-ttu-id="e413a-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="e413a-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e413a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e413a-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="e413a-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="e413a-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e413a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e413a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e413a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e413a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e413a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e413a-113">Attributes</span></span>  
 <span data-ttu-id="e413a-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e413a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e413a-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e413a-115">Child Elements</span></span>  
  
|<span data-ttu-id="e413a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e413a-116">Element</span></span>|<span data-ttu-id="e413a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e413a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e413a-118">\<add></span><span class="sxs-lookup"><span data-stu-id="e413a-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="e413a-119">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e413a-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e413a-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e413a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e413a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e413a-121">Element</span></span>|<span data-ttu-id="e413a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e413a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e413a-123">\<host></span><span class="sxs-lookup"><span data-stu-id="e413a-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="e413a-124">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e413a-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e413a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e413a-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="e413a-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="e413a-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
