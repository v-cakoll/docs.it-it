---
title: '&lt;DiscoveryClient&gt;'
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 9aef599ebf8068a383fd093b126a6bde1670b291
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151398"
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="7d595-102">&lt;DiscoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="7d595-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="7d595-103">Elemento di configurazione per la creazione di un'associazione personalizzata che consente a un'applicazione client di cercare automaticamente un servizio individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d595-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="7d595-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7d595-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7d595-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="7d595-105">\<bindings></span></span>  
<span data-ttu-id="7d595-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7d595-106">\<customBinding></span></span>  
<span data-ttu-id="7d595-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="7d595-107">\<binding></span></span>  
<span data-ttu-id="7d595-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="7d595-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d595-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d595-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d595-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7d595-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7d595-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7d595-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d595-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7d595-112">Attributes</span></span>  
  
|<span data-ttu-id="7d595-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7d595-113">Attribute</span></span>|<span data-ttu-id="7d595-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d595-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d595-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="7d595-115">discoveryEndpoint</span></span>|<span data-ttu-id="7d595-116">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d595-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d595-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7d595-117">Child Elements</span></span>  
  
|<span data-ttu-id="7d595-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d595-118">Element</span></span>|<span data-ttu-id="7d595-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d595-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d595-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="7d595-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="7d595-121">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="7d595-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="7d595-122">I criteri possono essere raggruppati in Criteri di ricerca (specificando i servizi desiderati) e trovare i criteri di terminazione (quanto tempo deve durare la ricerca).</span><span class="sxs-lookup"><span data-stu-id="7d595-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d595-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7d595-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7d595-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d595-124">Element</span></span>|<span data-ttu-id="7d595-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d595-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d595-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="7d595-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7d595-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7d595-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d595-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d595-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
