---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 21d53df12c2b2d703b771e2b9cb5ee87dafc410e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918716"
---
# <a name="host"></a><span data-ttu-id="f9637-101">\<> host</span><span class="sxs-lookup"><span data-stu-id="f9637-101">\<host></span></span>
<span data-ttu-id="f9637-102">Specifica impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f9637-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="f9637-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f9637-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f9637-104">\<> dei servizi</span><span class="sxs-lookup"><span data-stu-id="f9637-104">\<services></span></span>  
<span data-ttu-id="f9637-105">\<> del servizio</span><span class="sxs-lookup"><span data-stu-id="f9637-105">\<service></span></span>  
<span data-ttu-id="f9637-106">\<> host</span><span class="sxs-lookup"><span data-stu-id="f9637-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9637-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9637-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="f9637-108">Type</span><span class="sxs-lookup"><span data-stu-id="f9637-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9637-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f9637-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f9637-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f9637-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9637-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="f9637-111">Attributes</span></span>  
 <span data-ttu-id="f9637-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f9637-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9637-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f9637-113">Child Elements</span></span>  
  
|<span data-ttu-id="f9637-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9637-114">Element</span></span>|<span data-ttu-id="f9637-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f9637-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9637-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="f9637-116">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="f9637-117">Raccolta di elementi `baseAddress` che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f9637-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="f9637-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="f9637-118">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="f9637-119">Elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f9637-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9637-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f9637-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f9637-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9637-121">Element</span></span>|<span data-ttu-id="f9637-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f9637-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9637-123">\<service></span><span class="sxs-lookup"><span data-stu-id="f9637-123">\<service></span></span>](service.md)|<span data-ttu-id="f9637-124">Specifica le impostazioni per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f9637-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9637-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9637-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="f9637-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="f9637-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
