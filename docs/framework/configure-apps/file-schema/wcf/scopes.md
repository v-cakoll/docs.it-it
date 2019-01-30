---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: eee6382c578648866045fd9b283454d9e0e76fcb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275024"
---
# <a name="scopes"></a><span data-ttu-id="92ecd-101">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="92ecd-101">\<scopes></span></span>
<span data-ttu-id="92ecd-102">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="92ecd-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="92ecd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="92ecd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="92ecd-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="92ecd-104">\<behaviors></span></span>  
<span data-ttu-id="92ecd-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="92ecd-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="92ecd-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="92ecd-106">\<behavior></span></span>  
<span data-ttu-id="92ecd-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="92ecd-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="92ecd-108">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="92ecd-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ecd-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92ecd-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92ecd-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="92ecd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="92ecd-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="92ecd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92ecd-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="92ecd-112">Attributes</span></span>  
 <span data-ttu-id="92ecd-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="92ecd-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="92ecd-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="92ecd-114">Child Elements</span></span>  
  
|<span data-ttu-id="92ecd-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="92ecd-115">Attribute</span></span>|<span data-ttu-id="92ecd-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92ecd-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="92ecd-117">\<add></span><span class="sxs-lookup"><span data-stu-id="92ecd-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="92ecd-118">Aggiunge le informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="92ecd-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="92ecd-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="92ecd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="92ecd-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="92ecd-120">Element</span></span>|<span data-ttu-id="92ecd-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92ecd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92ecd-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="92ecd-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="92ecd-123">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="92ecd-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92ecd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92ecd-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
