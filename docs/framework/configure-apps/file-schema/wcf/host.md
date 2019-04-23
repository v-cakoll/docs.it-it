---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 3d1f7774f61060880a5c3b0327bdd6c2cc4dd74e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102999"
---
# <a name="host"></a><span data-ttu-id="13d4e-101">\<host></span><span class="sxs-lookup"><span data-stu-id="13d4e-101">\<host></span></span>
<span data-ttu-id="13d4e-102">Specifica impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="13d4e-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="13d4e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="13d4e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="13d4e-104">\<services></span><span class="sxs-lookup"><span data-stu-id="13d4e-104">\<services></span></span>  
<span data-ttu-id="13d4e-105">\<service></span><span class="sxs-lookup"><span data-stu-id="13d4e-105">\<service></span></span>  
<span data-ttu-id="13d4e-106">\<host></span><span class="sxs-lookup"><span data-stu-id="13d4e-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d4e-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13d4e-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="13d4e-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="13d4e-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13d4e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="13d4e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="13d4e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="13d4e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13d4e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="13d4e-111">Attributes</span></span>  
 <span data-ttu-id="13d4e-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="13d4e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13d4e-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="13d4e-113">Child Elements</span></span>  
  
|<span data-ttu-id="13d4e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="13d4e-114">Element</span></span>|<span data-ttu-id="13d4e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13d4e-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13d4e-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="13d4e-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="13d4e-117">Raccolta di elementi `baseAddress` che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="13d4e-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="13d4e-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="13d4e-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="13d4e-119">Elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="13d4e-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13d4e-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="13d4e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="13d4e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="13d4e-121">Element</span></span>|<span data-ttu-id="13d4e-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13d4e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13d4e-123">\<service></span><span class="sxs-lookup"><span data-stu-id="13d4e-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="13d4e-124">Specifica le impostazioni per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="13d4e-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13d4e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13d4e-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="13d4e-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="13d4e-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
