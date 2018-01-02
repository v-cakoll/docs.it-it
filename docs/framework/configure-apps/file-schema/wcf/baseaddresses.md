---
title: '&lt;baseAddresses&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69a049e1daacce901685050ab9fbe99a9c4d3428
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="08ec4-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="08ec4-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="08ec4-103">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="08ec4-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="08ec4-104">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="08ec4-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="08ec4-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="08ec4-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="08ec4-106">\<client ></span><span class="sxs-lookup"><span data-stu-id="08ec4-106">\<client></span></span>  
<span data-ttu-id="08ec4-107">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="08ec4-107">\<endpoint></span></span>  
<span data-ttu-id="08ec4-108">\<host ></span><span class="sxs-lookup"><span data-stu-id="08ec4-108">\<host></span></span>  
<span data-ttu-id="08ec4-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="08ec4-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ec4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08ec4-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="08ec4-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="08ec4-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08ec4-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="08ec4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="08ec4-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="08ec4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08ec4-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="08ec4-114">Attributes</span></span>  
 <span data-ttu-id="08ec4-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="08ec4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="08ec4-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="08ec4-116">Child Elements</span></span>  
  
|<span data-ttu-id="08ec4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="08ec4-117">Element</span></span>|<span data-ttu-id="08ec4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08ec4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08ec4-119">\<add></span><span class="sxs-lookup"><span data-stu-id="08ec4-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="08ec4-120">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="08ec4-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08ec4-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="08ec4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="08ec4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="08ec4-122">Element</span></span>|<span data-ttu-id="08ec4-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08ec4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08ec4-124">\<host ></span><span class="sxs-lookup"><span data-stu-id="08ec4-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="08ec4-125">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="08ec4-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08ec4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08ec4-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="08ec4-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="08ec4-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
