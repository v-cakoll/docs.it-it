---
title: '&lt;BaseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 0af5dee41c6adf560c90874e6e9a44b62c5decc6
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147356"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="7be5b-102">&lt;BaseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="7be5b-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="7be5b-103">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="7be5b-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="7be5b-104">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="7be5b-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="7be5b-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7be5b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="7be5b-106">\<client></span><span class="sxs-lookup"><span data-stu-id="7be5b-106">\<client></span></span>  
<span data-ttu-id="7be5b-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="7be5b-107">\<endpoint></span></span>  
<span data-ttu-id="7be5b-108">\<host ></span><span class="sxs-lookup"><span data-stu-id="7be5b-108">\<host></span></span>  
<span data-ttu-id="7be5b-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="7be5b-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be5b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7be5b-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="7be5b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="7be5b-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7be5b-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7be5b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7be5b-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7be5b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7be5b-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="7be5b-114">Attributes</span></span>  
 <span data-ttu-id="7be5b-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7be5b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7be5b-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7be5b-116">Child Elements</span></span>  
  
|<span data-ttu-id="7be5b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7be5b-117">Element</span></span>|<span data-ttu-id="7be5b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7be5b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7be5b-119">\<add></span><span class="sxs-lookup"><span data-stu-id="7be5b-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="7be5b-120">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="7be5b-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7be5b-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7be5b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7be5b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="7be5b-122">Element</span></span>|<span data-ttu-id="7be5b-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7be5b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7be5b-124">\<host ></span><span class="sxs-lookup"><span data-stu-id="7be5b-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="7be5b-125">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="7be5b-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7be5b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7be5b-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="7be5b-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="7be5b-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
