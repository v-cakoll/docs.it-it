---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: dc4b31e729f9037da101bdf3e6cde28e91b1a070
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277017"
---
# <a name="baseaddresses"></a><span data-ttu-id="e7ffc-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="e7ffc-101">\<baseAddresses></span></span>
<span data-ttu-id="e7ffc-102">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="e7ffc-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="e7ffc-103">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="e7ffc-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="e7ffc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e7ffc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e7ffc-105">\<client></span><span class="sxs-lookup"><span data-stu-id="e7ffc-105">\<client></span></span>  
<span data-ttu-id="e7ffc-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="e7ffc-106">\<endpoint></span></span>  
<span data-ttu-id="e7ffc-107">\<host></span><span class="sxs-lookup"><span data-stu-id="e7ffc-107">\<host></span></span>  
<span data-ttu-id="e7ffc-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="e7ffc-108">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7ffc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7ffc-109">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="e7ffc-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="e7ffc-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7ffc-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e7ffc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e7ffc-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e7ffc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7ffc-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="e7ffc-113">Attributes</span></span>  
 <span data-ttu-id="e7ffc-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e7ffc-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7ffc-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e7ffc-115">Child Elements</span></span>  
  
|<span data-ttu-id="e7ffc-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7ffc-116">Element</span></span>|<span data-ttu-id="e7ffc-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7ffc-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7ffc-118">\<add></span><span class="sxs-lookup"><span data-stu-id="e7ffc-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="e7ffc-119">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e7ffc-119">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7ffc-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e7ffc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e7ffc-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7ffc-121">Element</span></span>|<span data-ttu-id="e7ffc-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7ffc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7ffc-123">\<host></span><span class="sxs-lookup"><span data-stu-id="e7ffc-123">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="e7ffc-124">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e7ffc-124">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7ffc-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7ffc-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="e7ffc-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="e7ffc-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
