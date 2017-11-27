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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 41ebd88f64b001b577342562c9c3010b307aaccc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="1b467-102">&lt;Timeout&gt;</span><span class="sxs-lookup"><span data-stu-id="1b467-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="1b467-103">Rappresenta un elemento di configurazione che specifica l'intervallo di tempo consentito per l'apertura o la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="1b467-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="1b467-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1b467-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b467-105">\<client ></span><span class="sxs-lookup"><span data-stu-id="1b467-105">\<client></span></span>  
<span data-ttu-id="1b467-106">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="1b467-106">\<endpoint></span></span>  
<span data-ttu-id="1b467-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="1b467-107">\<host></span></span>  
<span data-ttu-id="1b467-108">\<Timeout ></span><span class="sxs-lookup"><span data-stu-id="1b467-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b467-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b467-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b467-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1b467-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1b467-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1b467-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b467-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1b467-112">Attributes</span></span>  
  
|<span data-ttu-id="1b467-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1b467-113">Attribute</span></span>|<span data-ttu-id="1b467-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b467-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="1b467-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per la chiusura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="1b467-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="1b467-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo consentito per l'apertura dell'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="1b467-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b467-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1b467-117">Child Elements</span></span>  
 <span data-ttu-id="1b467-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1b467-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b467-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1b467-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1b467-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1b467-120">Element</span></span>|<span data-ttu-id="1b467-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b467-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b467-122">\<host ></span><span class="sxs-lookup"><span data-stu-id="1b467-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="1b467-123">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="1b467-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b467-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b467-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="1b467-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="1b467-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
