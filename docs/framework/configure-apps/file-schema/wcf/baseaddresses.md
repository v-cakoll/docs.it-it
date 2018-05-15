---
title: '&lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 8de962cc70e1399dd1e9459473055651f9aca5fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="25300-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="25300-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="25300-103">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="25300-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="25300-104">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="25300-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="25300-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="25300-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="25300-106">\<client></span><span class="sxs-lookup"><span data-stu-id="25300-106">\<client></span></span>  
<span data-ttu-id="25300-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="25300-107">\<endpoint></span></span>  
<span data-ttu-id="25300-108">\<host ></span><span class="sxs-lookup"><span data-stu-id="25300-108">\<host></span></span>  
<span data-ttu-id="25300-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="25300-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25300-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25300-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="25300-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="25300-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25300-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="25300-112">Attributes and Elements</span></span>  
 <span data-ttu-id="25300-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="25300-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25300-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="25300-114">Attributes</span></span>  
 <span data-ttu-id="25300-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="25300-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="25300-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="25300-116">Child Elements</span></span>  
  
|<span data-ttu-id="25300-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="25300-117">Element</span></span>|<span data-ttu-id="25300-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25300-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25300-119">\<add></span><span class="sxs-lookup"><span data-stu-id="25300-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="25300-120">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="25300-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25300-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="25300-121">Parent Elements</span></span>  
  
|<span data-ttu-id="25300-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="25300-122">Element</span></span>|<span data-ttu-id="25300-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25300-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25300-124">\<host ></span><span class="sxs-lookup"><span data-stu-id="25300-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="25300-125">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="25300-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25300-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25300-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="25300-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="25300-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
