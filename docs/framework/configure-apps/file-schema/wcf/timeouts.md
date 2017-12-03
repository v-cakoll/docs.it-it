---
title: '&lt;Timeout&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da80ab797078e1fe912ccbfff07d7fb2da49664e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="8792e-102">&lt;Timeout&gt;</span><span class="sxs-lookup"><span data-stu-id="8792e-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="8792e-103">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="8792e-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="8792e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8792e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8792e-105">\<client ></span><span class="sxs-lookup"><span data-stu-id="8792e-105">\<client></span></span>  
<span data-ttu-id="8792e-106">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="8792e-106">\<endpoint></span></span>  
<span data-ttu-id="8792e-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="8792e-107">\<host></span></span>  
<span data-ttu-id="8792e-108">\<Timeout ></span><span class="sxs-lookup"><span data-stu-id="8792e-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8792e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8792e-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8792e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8792e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8792e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8792e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8792e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="8792e-112">Attributes</span></span>  
  
|<span data-ttu-id="8792e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="8792e-113">Attribute</span></span>|<span data-ttu-id="8792e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8792e-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="8792e-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="8792e-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="8792e-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="8792e-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8792e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8792e-117">Child Elements</span></span>  
 <span data-ttu-id="8792e-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8792e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8792e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8792e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8792e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8792e-120">Element</span></span>|<span data-ttu-id="8792e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8792e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8792e-122">\<host ></span><span class="sxs-lookup"><span data-stu-id="8792e-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="8792e-123">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="8792e-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8792e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8792e-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="8792e-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="8792e-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
