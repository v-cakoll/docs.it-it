---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399944"
---
# <a name="scopes"></a><span data-ttu-id="70cab-101">\<ambiti ></span><span class="sxs-lookup"><span data-stu-id="70cab-101">\<scopes></span></span>
<span data-ttu-id="70cab-102">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="70cab-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="70cab-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="70cab-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="70cab-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="70cab-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="70cab-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="70cab-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="70cab-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="70cab-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="70cab-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="70cab-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="70cab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointDiscovery**](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="70cab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="70cab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ambiti >**</span><span class="sxs-lookup"><span data-stu-id="70cab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70cab-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70cab-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70cab-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="70cab-111">Attributes and Elements</span></span>  
 <span data-ttu-id="70cab-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="70cab-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70cab-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="70cab-113">Attributes</span></span>  
 <span data-ttu-id="70cab-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="70cab-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="70cab-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="70cab-115">Child Elements</span></span>  
  
|<span data-ttu-id="70cab-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="70cab-116">Attribute</span></span>|<span data-ttu-id="70cab-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70cab-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="70cab-118">\<add></span><span class="sxs-lookup"><span data-stu-id="70cab-118">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="70cab-119">Aggiunge le informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="70cab-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70cab-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="70cab-120">Parent Elements</span></span>  
  
|<span data-ttu-id="70cab-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="70cab-121">Element</span></span>|<span data-ttu-id="70cab-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="70cab-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70cab-123">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="70cab-123">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="70cab-124">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="70cab-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70cab-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70cab-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
