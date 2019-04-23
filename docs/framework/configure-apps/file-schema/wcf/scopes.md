---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213077"
---
# <a name="scopes"></a><span data-ttu-id="34999-101">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="34999-101">\<scopes></span></span>
<span data-ttu-id="34999-102">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="34999-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="34999-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="34999-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="34999-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="34999-104">\<behaviors></span></span>  
<span data-ttu-id="34999-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="34999-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="34999-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="34999-106">\<behavior></span></span>  
<span data-ttu-id="34999-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="34999-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="34999-108">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="34999-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34999-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34999-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34999-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="34999-110">Attributes and Elements</span></span>  
 <span data-ttu-id="34999-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="34999-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34999-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="34999-112">Attributes</span></span>  
 <span data-ttu-id="34999-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="34999-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="34999-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="34999-114">Child Elements</span></span>  
  
|<span data-ttu-id="34999-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="34999-115">Attribute</span></span>|<span data-ttu-id="34999-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34999-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="34999-117">\<add></span><span class="sxs-lookup"><span data-stu-id="34999-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="34999-118">Aggiunge le informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="34999-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34999-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="34999-119">Parent Elements</span></span>  
  
|<span data-ttu-id="34999-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="34999-120">Element</span></span>|<span data-ttu-id="34999-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34999-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34999-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="34999-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="34999-123">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="34999-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34999-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34999-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
