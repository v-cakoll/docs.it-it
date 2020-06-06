---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855219"
---
# \<host>
<span data-ttu-id="634c6-101">Specifica impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="634c6-101">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="634c6-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="634c6-102">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="634c6-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="634c6-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="634c6-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="634c6-104">Attributes and Elements</span></span>  
 <span data-ttu-id="634c6-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="634c6-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="634c6-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="634c6-106">Attributes</span></span>  
 <span data-ttu-id="634c6-107">No.</span><span class="sxs-lookup"><span data-stu-id="634c6-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="634c6-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="634c6-108">Child Elements</span></span>  
  
|<span data-ttu-id="634c6-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="634c6-109">Element</span></span>|<span data-ttu-id="634c6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="634c6-110">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="634c6-111">Raccolta di elementi `baseAddress` che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="634c6-111">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="634c6-112">Elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="634c6-112">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="634c6-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="634c6-113">Parent Elements</span></span>  
  
|<span data-ttu-id="634c6-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="634c6-114">Element</span></span>|<span data-ttu-id="634c6-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="634c6-115">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="634c6-116">Specifica le impostazioni per un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="634c6-116">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="634c6-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="634c6-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="634c6-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="634c6-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
