---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739043"
---
# <a name="discoveryclient"></a><span data-ttu-id="cd517-101">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="cd517-101">\<discoveryClient></span></span>
<span data-ttu-id="cd517-102">Elemento di configurazione per la creazione di un'associazione personalizzata che consente a un'applicazione client di cercare automaticamente un servizio individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cd517-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="cd517-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cd517-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cd517-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cd517-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cd517-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="cd517-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="cd517-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="cd517-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="cd517-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="cd517-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="cd517-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<discoveryClient >**</span><span class="sxs-lookup"><span data-stu-id="cd517-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd517-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd517-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd517-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cd517-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cd517-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cd517-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd517-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cd517-112">Attributes</span></span>  
  
|<span data-ttu-id="cd517-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="cd517-113">Attribute</span></span>|<span data-ttu-id="cd517-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd517-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd517-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="cd517-115">discoveryEndpoint</span></span>|<span data-ttu-id="cd517-116">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cd517-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd517-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cd517-117">Child Elements</span></span>  
  
|<span data-ttu-id="cd517-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd517-118">Element</span></span>|<span data-ttu-id="cd517-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd517-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd517-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="cd517-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="cd517-121">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="cd517-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="cd517-122">I criteri possono essere raggruppati in criteri di ricerca (specificando i servizi desiderati) e individuare i criteri di terminazione (durata della ricerca).</span><span class="sxs-lookup"><span data-stu-id="cd517-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd517-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cd517-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cd517-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd517-124">Element</span></span>|<span data-ttu-id="cd517-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd517-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd517-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="cd517-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="cd517-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="cd517-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd517-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd517-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
