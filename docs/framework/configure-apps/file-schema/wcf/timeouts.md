---
title: '&lt;timeOuts&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 42f4db1d954834cbfa3c526328cca45443751506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629657"
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="98fae-102">&lt;timeOuts&gt;</span><span class="sxs-lookup"><span data-stu-id="98fae-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="98fae-103">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="98fae-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="98fae-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="98fae-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="98fae-105">\<client></span><span class="sxs-lookup"><span data-stu-id="98fae-105">\<client></span></span>  
<span data-ttu-id="98fae-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="98fae-106">\<endpoint></span></span>  
<span data-ttu-id="98fae-107">\<host></span><span class="sxs-lookup"><span data-stu-id="98fae-107">\<host></span></span>  
<span data-ttu-id="98fae-108">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="98fae-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98fae-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98fae-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98fae-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="98fae-110">Attributes and Elements</span></span>  
 <span data-ttu-id="98fae-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="98fae-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98fae-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="98fae-112">Attributes</span></span>  
  
|<span data-ttu-id="98fae-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="98fae-113">Attribute</span></span>|<span data-ttu-id="98fae-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98fae-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="98fae-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="98fae-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="98fae-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="98fae-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98fae-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="98fae-117">Child Elements</span></span>  
 <span data-ttu-id="98fae-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="98fae-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98fae-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="98fae-119">Parent Elements</span></span>  
  
|<span data-ttu-id="98fae-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="98fae-120">Element</span></span>|<span data-ttu-id="98fae-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98fae-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98fae-122">\<host></span><span class="sxs-lookup"><span data-stu-id="98fae-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="98fae-123">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="98fae-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98fae-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98fae-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="98fae-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="98fae-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
