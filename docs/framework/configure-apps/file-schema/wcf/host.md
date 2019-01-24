---
title: '&lt;host&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 1fb35058d407d0fbae78092bb4ccd45b0aaa40e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702028"
---
# <a name="lthostgt"></a><span data-ttu-id="9c16e-102">&lt;host&gt;</span><span class="sxs-lookup"><span data-stu-id="9c16e-102">&lt;host&gt;</span></span>
<span data-ttu-id="9c16e-103">Specifica impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="9c16e-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="9c16e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9c16e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9c16e-105">\<services></span><span class="sxs-lookup"><span data-stu-id="9c16e-105">\<services></span></span>  
<span data-ttu-id="9c16e-106">\<service></span><span class="sxs-lookup"><span data-stu-id="9c16e-106">\<service></span></span>  
<span data-ttu-id="9c16e-107">\<host></span><span class="sxs-lookup"><span data-stu-id="9c16e-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c16e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c16e-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="9c16e-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="9c16e-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c16e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9c16e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9c16e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9c16e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c16e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="9c16e-112">Attributes</span></span>  
 <span data-ttu-id="9c16e-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9c16e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c16e-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9c16e-114">Child Elements</span></span>  
  
|<span data-ttu-id="9c16e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c16e-115">Element</span></span>|<span data-ttu-id="9c16e-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c16e-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c16e-117">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="9c16e-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="9c16e-118">Raccolta di elementi `baseAddress` che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="9c16e-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="9c16e-119">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="9c16e-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="9c16e-120">Elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="9c16e-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c16e-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9c16e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9c16e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c16e-122">Element</span></span>|<span data-ttu-id="9c16e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c16e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c16e-124">\<service></span><span class="sxs-lookup"><span data-stu-id="9c16e-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="9c16e-125">Specifica le impostazioni per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9c16e-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c16e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c16e-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="9c16e-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="9c16e-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
