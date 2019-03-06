---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 512a91bf25180606213eb9eb3b4f7c6a0cb4cbbf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366231"
---
# <a name="discoveryclient"></a><span data-ttu-id="37777-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="37777-101">\<discoveryClient></span></span>
<span data-ttu-id="37777-102">Elemento di configurazione per la creazione di un'associazione personalizzata che consente a un'applicazione client di cercare automaticamente un servizio individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="37777-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="37777-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="37777-103">\<system.serviceModel></span></span>  
<span data-ttu-id="37777-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="37777-104">\<bindings></span></span>  
<span data-ttu-id="37777-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="37777-105">\<customBinding></span></span>  
<span data-ttu-id="37777-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="37777-106">\<binding></span></span>  
<span data-ttu-id="37777-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="37777-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37777-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37777-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37777-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="37777-109">Attributes and Elements</span></span>  
 <span data-ttu-id="37777-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="37777-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37777-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="37777-111">Attributes</span></span>  
  
|<span data-ttu-id="37777-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="37777-112">Attribute</span></span>|<span data-ttu-id="37777-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37777-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37777-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="37777-114">discoveryEndpoint</span></span>|<span data-ttu-id="37777-115">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="37777-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37777-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="37777-116">Child Elements</span></span>  
  
|<span data-ttu-id="37777-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="37777-117">Element</span></span>|<span data-ttu-id="37777-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37777-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37777-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="37777-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="37777-120">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="37777-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="37777-121">I criteri possono essere raggruppati in Criteri di ricerca (specificando i servizi desiderati) e trovare i criteri di terminazione (quanto tempo deve durare la ricerca).</span><span class="sxs-lookup"><span data-stu-id="37777-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37777-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="37777-122">Parent Elements</span></span>  
  
|<span data-ttu-id="37777-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="37777-123">Element</span></span>|<span data-ttu-id="37777-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37777-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37777-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="37777-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="37777-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="37777-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37777-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37777-127">See also</span></span>
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
