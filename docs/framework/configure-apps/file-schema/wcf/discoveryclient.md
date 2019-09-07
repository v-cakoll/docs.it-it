---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 5e586437e3b269d361c254744e820ee8e8c0ca0a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400392"
---
# <a name="discoveryclient"></a><span data-ttu-id="4a6eb-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="4a6eb-101">\<discoveryClient></span></span>
<span data-ttu-id="4a6eb-102">Elemento di configurazione per la creazione di un'associazione personalizzata che consente a un'applicazione client di cercare automaticamente un servizio individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="4a6eb-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a6eb-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4a6eb-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4a6eb-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4a6eb-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4a6eb-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4a6eb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="4a6eb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="4a6eb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="4a6eb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4a6eb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> discoveryClient**</span><span class="sxs-lookup"><span data-stu-id="4a6eb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a6eb-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a6eb-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a6eb-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4a6eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4a6eb-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a6eb-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4a6eb-112">Attributes</span></span>  
  
|<span data-ttu-id="4a6eb-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4a6eb-113">Attribute</span></span>|<span data-ttu-id="4a6eb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a6eb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a6eb-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="4a6eb-115">discoveryEndpoint</span></span>|<span data-ttu-id="4a6eb-116">Stringa contenente il nome dell'endpoint di individuazione che consente a un'applicazione client di cercare automaticamente un servizio flusso di lavoro individuabile e di trovarne l'indirizzo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a6eb-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4a6eb-117">Child Elements</span></span>  
  
|<span data-ttu-id="4a6eb-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a6eb-118">Element</span></span>|<span data-ttu-id="4a6eb-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a6eb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a6eb-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="4a6eb-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="4a6eb-121">Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="4a6eb-122">I criteri possono essere raggruppati in criteri di ricerca (specificando i servizi desiderati) e individuare i criteri di terminazione (durata della ricerca).</span><span class="sxs-lookup"><span data-stu-id="4a6eb-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4a6eb-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4a6eb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4a6eb-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a6eb-124">Element</span></span>|<span data-ttu-id="4a6eb-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4a6eb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a6eb-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="4a6eb-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="4a6eb-127">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4a6eb-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a6eb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a6eb-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
