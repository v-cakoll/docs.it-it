---
title: '&lt;Timeout&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: e39deeb251865b87eb7734e4447088ca2f221d1d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148331"
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="3161a-102">&lt;Timeout&gt;</span><span class="sxs-lookup"><span data-stu-id="3161a-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="3161a-103">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="3161a-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="3161a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3161a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3161a-105">\<client></span><span class="sxs-lookup"><span data-stu-id="3161a-105">\<client></span></span>  
<span data-ttu-id="3161a-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="3161a-106">\<endpoint></span></span>  
<span data-ttu-id="3161a-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="3161a-107">\<host></span></span>  
<span data-ttu-id="3161a-108">\<i timeout ></span><span class="sxs-lookup"><span data-stu-id="3161a-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3161a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3161a-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3161a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3161a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3161a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3161a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3161a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3161a-112">Attributes</span></span>  
  
|<span data-ttu-id="3161a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="3161a-113">Attribute</span></span>|<span data-ttu-id="3161a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3161a-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="3161a-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="3161a-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="3161a-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="3161a-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3161a-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3161a-117">Child Elements</span></span>  
 <span data-ttu-id="3161a-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3161a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3161a-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3161a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3161a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="3161a-120">Element</span></span>|<span data-ttu-id="3161a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3161a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3161a-122">\<host ></span><span class="sxs-lookup"><span data-stu-id="3161a-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="3161a-123">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="3161a-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3161a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3161a-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="3161a-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="3161a-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
