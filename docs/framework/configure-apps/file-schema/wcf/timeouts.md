---
title: '&lt;Timeout&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 1f0638f85177d2acb6f61e3246a1a5ee9a4e2f5c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753001"
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="e796d-102">&lt;Timeout&gt;</span><span class="sxs-lookup"><span data-stu-id="e796d-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="e796d-103">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e796d-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="e796d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e796d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e796d-105">\<client></span><span class="sxs-lookup"><span data-stu-id="e796d-105">\<client></span></span>  
<span data-ttu-id="e796d-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="e796d-106">\<endpoint></span></span>  
<span data-ttu-id="e796d-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="e796d-107">\<host></span></span>  
<span data-ttu-id="e796d-108">\<Timeout ></span><span class="sxs-lookup"><span data-stu-id="e796d-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e796d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e796d-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e796d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e796d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e796d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e796d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e796d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="e796d-112">Attributes</span></span>  
  
|<span data-ttu-id="e796d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="e796d-113">Attribute</span></span>|<span data-ttu-id="e796d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e796d-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="e796d-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e796d-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="e796d-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e796d-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e796d-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e796d-117">Child Elements</span></span>  
 <span data-ttu-id="e796d-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e796d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e796d-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e796d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e796d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e796d-120">Element</span></span>|<span data-ttu-id="e796d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e796d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e796d-122">\<host ></span><span class="sxs-lookup"><span data-stu-id="e796d-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="e796d-123">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="e796d-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e796d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e796d-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="e796d-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="e796d-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
