---
title: '&lt;discoveryClient&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c9cbdb61152a5315aaf919e3a3c58d9329449e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="610f6-102">&lt;discoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="610f6-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="610f6-103">Elemento di configurazione per la creazione di un'associazione personalizzata che consente a un'applicazione client di cercare automaticamente un servizio individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="610f6-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="610f6-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="610f6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="610f6-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="610f6-105">\<bindings></span></span>  
<span data-ttu-id="610f6-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="610f6-106">\<customBinding></span></span>  
<span data-ttu-id="610f6-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="610f6-107">\<binding></span></span>  
<span data-ttu-id="610f6-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="610f6-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="610f6-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="610f6-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String" >
  <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String" namespace="String" />
    <contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="610f6-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="610f6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="610f6-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="610f6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="610f6-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="610f6-112">Attributes</span></span>  
  
|<span data-ttu-id="610f6-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="610f6-113">Attribute</span></span>|<span data-ttu-id="610f6-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="610f6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="610f6-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="610f6-115">discoveryEndpoint</span></span>|<span data-ttu-id="610f6-116">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="610f6-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="610f6-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="610f6-117">Child Elements</span></span>  
  
|<span data-ttu-id="610f6-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="610f6-118">Element</span></span>|<span data-ttu-id="610f6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="610f6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="610f6-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="610f6-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="610f6-121">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="610f6-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="610f6-122">I criteri possono essere raggruppati nei criteri di ricerca (specificando i servizi da cercare) e i criteri di terminazione (quanto tempo deve durare la ricerca).</span><span class="sxs-lookup"><span data-stu-id="610f6-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="610f6-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="610f6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="610f6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="610f6-124">Element</span></span>|<span data-ttu-id="610f6-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="610f6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="610f6-126">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="610f6-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="610f6-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="610f6-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="610f6-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="610f6-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
