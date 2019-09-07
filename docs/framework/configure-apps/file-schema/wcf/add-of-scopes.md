---
title: <add> di <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398298"
---
# <a name="add-of-scopes"></a><span data-ttu-id="e9767-102">\<aggiungere > degli \<ambiti ></span><span class="sxs-lookup"><span data-stu-id="e9767-102">\<add> of \<scopes></span></span>
<span data-ttu-id="e9767-103">Aggiunge URI di ambito personalizzato che è possibile usare per filtrare gli endpoint di servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="e9767-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="e9767-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9767-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9767-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e9767-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e9767-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e9767-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e9767-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e9767-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="e9767-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e9767-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="e9767-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointDiscovery**](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="e9767-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="e9767-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ambiti >** ](scopes.md)</span><span class="sxs-lookup"><span data-stu-id="e9767-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)</span></span>\
<span data-ttu-id="e9767-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="e9767-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9767-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9767-112">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9767-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e9767-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e9767-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e9767-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9767-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="e9767-115">Attributes</span></span>  
  
|<span data-ttu-id="e9767-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="e9767-116">Attribute</span></span>|<span data-ttu-id="e9767-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e9767-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9767-118">scope</span><span class="sxs-lookup"><span data-stu-id="e9767-118">scope</span></span>|<span data-ttu-id="e9767-119">URI contenente informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="e9767-119">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9767-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e9767-120">Child Elements</span></span>  
 <span data-ttu-id="e9767-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e9767-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9767-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e9767-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e9767-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9767-123">Element</span></span>|<span data-ttu-id="e9767-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9767-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9767-125">\<ambiti ></span><span class="sxs-lookup"><span data-stu-id="e9767-125">\<scopes></span></span>](scopes.md)|<span data-ttu-id="e9767-126">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="e9767-126">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9767-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9767-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
