---
title: '&lt;add&gt; di &lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: ce476c2d40758cf52eada813873d061d0e441bce
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149085"
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="866a6-102">&lt;add&gt; di &lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="866a6-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="866a6-103">Rappresenta un elemento di configurazione che specifica indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="866a6-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="866a6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="866a6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="866a6-105">\<client></span><span class="sxs-lookup"><span data-stu-id="866a6-105">\<client></span></span>  
<span data-ttu-id="866a6-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="866a6-106">\<endpoint></span></span>  
<span data-ttu-id="866a6-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="866a6-107">\<host></span></span>  
<span data-ttu-id="866a6-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="866a6-108">\<baseAddresses></span></span>  
<span data-ttu-id="866a6-109">\<baseAddress ></span><span class="sxs-lookup"><span data-stu-id="866a6-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="866a6-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="866a6-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="866a6-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="866a6-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="866a6-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="866a6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="866a6-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="866a6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="866a6-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="866a6-114">Attributes</span></span>  
  
|<span data-ttu-id="866a6-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="866a6-115">Attribute</span></span>|<span data-ttu-id="866a6-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="866a6-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="866a6-117">Stringa che specifica un indirizzo di base usato dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="866a6-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="866a6-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="866a6-118">Child Elements</span></span>  
 <span data-ttu-id="866a6-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="866a6-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="866a6-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="866a6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="866a6-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="866a6-121">Element</span></span>|<span data-ttu-id="866a6-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="866a6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="866a6-123">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="866a6-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="866a6-124">Raccolta di elementi `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="866a6-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="866a6-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="866a6-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="866a6-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="866a6-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
