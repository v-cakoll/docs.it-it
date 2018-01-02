---
title: '&lt;add&gt; di &lt;baseAddresses&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 516c615248c95ef3107664b996f457fb80b46373
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="71f5c-102">&lt;add&gt; di &lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="71f5c-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="71f5c-103">Rappresenta un elemento di configurazione che specifica indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="71f5c-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="71f5c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="71f5c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="71f5c-105">\<client ></span><span class="sxs-lookup"><span data-stu-id="71f5c-105">\<client></span></span>  
<span data-ttu-id="71f5c-106">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="71f5c-106">\<endpoint></span></span>  
<span data-ttu-id="71f5c-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="71f5c-107">\<host></span></span>  
<span data-ttu-id="71f5c-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="71f5c-108">\<baseAddresses></span></span>  
<span data-ttu-id="71f5c-109">\<baseAddress ></span><span class="sxs-lookup"><span data-stu-id="71f5c-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f5c-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71f5c-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a><span data-ttu-id="71f5c-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="71f5c-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71f5c-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="71f5c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="71f5c-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="71f5c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71f5c-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="71f5c-114">Attributes</span></span>  
  
|<span data-ttu-id="71f5c-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="71f5c-115">Attribute</span></span>|<span data-ttu-id="71f5c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71f5c-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="71f5c-117">Stringa che specifica un indirizzo di base usato dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="71f5c-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71f5c-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="71f5c-118">Child Elements</span></span>  
 <span data-ttu-id="71f5c-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="71f5c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71f5c-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="71f5c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="71f5c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="71f5c-121">Element</span></span>|<span data-ttu-id="71f5c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71f5c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71f5c-123">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="71f5c-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="71f5c-124">Raccolta di elementi `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="71f5c-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71f5c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71f5c-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="71f5c-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="71f5c-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
