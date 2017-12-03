---
title: '&lt;ambiti&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f198811483edb8a7be882588c38b1f3942f8bb4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltscopesgt"></a><span data-ttu-id="7b7f1-102">&lt;ambiti&gt;</span><span class="sxs-lookup"><span data-stu-id="7b7f1-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="7b7f1-103">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="7b7f1-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7b7f1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7b7f1-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="7b7f1-105">\<behaviors></span></span>  
<span data-ttu-id="7b7f1-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7b7f1-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="7b7f1-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="7b7f1-107">\<behavior></span></span>  
<span data-ttu-id="7b7f1-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="7b7f1-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="7b7f1-109">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="7b7f1-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b7f1-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b7f1-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b7f1-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7b7f1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7b7f1-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b7f1-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="7b7f1-113">Attributes</span></span>  
 <span data-ttu-id="7b7f1-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7b7f1-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7b7f1-115">Child Elements</span></span>  
  
|<span data-ttu-id="7b7f1-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="7b7f1-116">Attribute</span></span>|<span data-ttu-id="7b7f1-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b7f1-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="7b7f1-118">\<add></span><span class="sxs-lookup"><span data-stu-id="7b7f1-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="7b7f1-119">Aggiunge le informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b7f1-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7b7f1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7b7f1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="7b7f1-121">Element</span></span>|<span data-ttu-id="7b7f1-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b7f1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b7f1-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="7b7f1-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="7b7f1-124">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="7b7f1-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b7f1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b7f1-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
