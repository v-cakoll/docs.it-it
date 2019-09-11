---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855219"
---
# <a name="host"></a><span data-ttu-id="3d5ec-101">\<> host</span><span class="sxs-lookup"><span data-stu-id="3d5ec-101">\<host></span></span>
<span data-ttu-id="3d5ec-102">Specifica impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="3d5ec-102">Specifies settings for a service host.</span></span>  
  
<span data-ttu-id="3d5ec-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3d5ec-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3d5ec-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3d5ec-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3d5ec-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dei servizi**](services.md)</span><span class="sxs-lookup"><span data-stu-id="3d5ec-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="3d5ec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> del servizio**](service.md)</span><span class="sxs-lookup"><span data-stu-id="3d5ec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="3d5ec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> host**</span><span class="sxs-lookup"><span data-stu-id="3d5ec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d5ec-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d5ec-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="3d5ec-109">Type</span><span class="sxs-lookup"><span data-stu-id="3d5ec-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d5ec-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3d5ec-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3d5ec-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3d5ec-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d5ec-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3d5ec-112">Attributes</span></span>  
 <span data-ttu-id="3d5ec-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3d5ec-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d5ec-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3d5ec-114">Child Elements</span></span>  
  
|<span data-ttu-id="3d5ec-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d5ec-115">Element</span></span>|<span data-ttu-id="3d5ec-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d5ec-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d5ec-117">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="3d5ec-117">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="3d5ec-118">Raccolta di elementi `baseAddress` che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="3d5ec-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="3d5ec-119">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="3d5ec-119">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="3d5ec-120">Elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="3d5ec-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d5ec-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3d5ec-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3d5ec-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d5ec-122">Element</span></span>|<span data-ttu-id="3d5ec-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d5ec-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d5ec-124">\<service></span><span class="sxs-lookup"><span data-stu-id="3d5ec-124">\<service></span></span>](service.md)|<span data-ttu-id="3d5ec-125">Specifica le impostazioni per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3d5ec-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d5ec-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d5ec-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="3d5ec-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="3d5ec-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
