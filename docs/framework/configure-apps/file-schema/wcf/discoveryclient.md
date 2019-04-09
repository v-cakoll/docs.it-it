---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: a5ea10601732021af578c17d4f5c5ab69c98f17a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128440"
---
# <a name="discoveryclient"></a><span data-ttu-id="12a07-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="12a07-101">\<discoveryClient></span></span>
<span data-ttu-id="12a07-102">Elemento di configurazione per la creazione di un'associazione personalizzata che consente a un'applicazione client di cercare automaticamente un servizio individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="12a07-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="12a07-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="12a07-103">\<system.serviceModel></span></span>  
<span data-ttu-id="12a07-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="12a07-104">\<bindings></span></span>  
<span data-ttu-id="12a07-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="12a07-105">\<customBinding></span></span>  
<span data-ttu-id="12a07-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="12a07-106">\<binding></span></span>  
<span data-ttu-id="12a07-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="12a07-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12a07-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12a07-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12a07-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="12a07-109">Attributes and Elements</span></span>  
 <span data-ttu-id="12a07-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="12a07-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12a07-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="12a07-111">Attributes</span></span>  
  
|<span data-ttu-id="12a07-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="12a07-112">Attribute</span></span>|<span data-ttu-id="12a07-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12a07-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12a07-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="12a07-114">discoveryEndpoint</span></span>|<span data-ttu-id="12a07-115">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="12a07-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12a07-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="12a07-116">Child Elements</span></span>  
  
|<span data-ttu-id="12a07-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="12a07-117">Element</span></span>|<span data-ttu-id="12a07-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12a07-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12a07-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="12a07-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="12a07-120">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="12a07-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="12a07-121">I criteri possono essere raggruppati in Criteri di ricerca (specificando i servizi desiderati) e trovare i criteri di terminazione (quanto tempo deve durare la ricerca).</span><span class="sxs-lookup"><span data-stu-id="12a07-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12a07-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="12a07-122">Parent Elements</span></span>  
  
|<span data-ttu-id="12a07-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="12a07-123">Element</span></span>|<span data-ttu-id="12a07-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12a07-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12a07-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="12a07-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="12a07-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="12a07-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12a07-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12a07-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
