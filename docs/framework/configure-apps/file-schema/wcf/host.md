---
title: '&lt;Host&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: ec53568e9d1df9ebb04bc299f491e80674950c63
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233730"
---
# <a name="lthostgt"></a><span data-ttu-id="4bdce-102">&lt;Host&gt;</span><span class="sxs-lookup"><span data-stu-id="4bdce-102">&lt;host&gt;</span></span>
<span data-ttu-id="4bdce-103">Specifica impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="4bdce-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="4bdce-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4bdce-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4bdce-105">\<Services ></span><span class="sxs-lookup"><span data-stu-id="4bdce-105">\<services></span></span>  
<span data-ttu-id="4bdce-106">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="4bdce-106">\<service></span></span>  
<span data-ttu-id="4bdce-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="4bdce-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bdce-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bdce-108">Syntax</span></span>  
  
```xml  
<host>
    <baseAddresses>  
        <add baseAddress="string" />  
    </baseAddresses>  
    <timeOuts closeTimeout="TimeSpan" openTimeout="TimeSpan">  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="4bdce-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="4bdce-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4bdce-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4bdce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4bdce-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4bdce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4bdce-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4bdce-112">Attributes</span></span>  
 <span data-ttu-id="4bdce-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4bdce-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4bdce-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4bdce-114">Child Elements</span></span>  
  
|<span data-ttu-id="4bdce-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bdce-115">Element</span></span>|<span data-ttu-id="4bdce-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4bdce-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4bdce-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="4bdce-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="4bdce-118">Raccolta di elementi `baseAddress` che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="4bdce-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="4bdce-119">\<Timeout ></span><span class="sxs-lookup"><span data-stu-id="4bdce-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="4bdce-120">Elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="4bdce-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4bdce-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4bdce-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4bdce-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bdce-122">Element</span></span>|<span data-ttu-id="4bdce-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4bdce-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4bdce-124">\<service></span><span class="sxs-lookup"><span data-stu-id="4bdce-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="4bdce-125">Specifica le impostazioni per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4bdce-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bdce-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bdce-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="4bdce-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="4bdce-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
