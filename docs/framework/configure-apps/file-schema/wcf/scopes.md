---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: dd6513930798e9e1ab263f75c9350511c2dcdcd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935178"
---
# <a name="scopes"></a><span data-ttu-id="31b6e-101">\<ambiti ></span><span class="sxs-lookup"><span data-stu-id="31b6e-101">\<scopes></span></span>
<span data-ttu-id="31b6e-102">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="31b6e-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="31b6e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="31b6e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="31b6e-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="31b6e-104">\<behaviors></span></span>  
<span data-ttu-id="31b6e-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="31b6e-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="31b6e-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="31b6e-106">\<behavior></span></span>  
<span data-ttu-id="31b6e-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="31b6e-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="31b6e-108">\<ambiti ></span><span class="sxs-lookup"><span data-stu-id="31b6e-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31b6e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31b6e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31b6e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="31b6e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="31b6e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="31b6e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31b6e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="31b6e-112">Attributes</span></span>  
 <span data-ttu-id="31b6e-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="31b6e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="31b6e-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="31b6e-114">Child Elements</span></span>  
  
|<span data-ttu-id="31b6e-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="31b6e-115">Attribute</span></span>|<span data-ttu-id="31b6e-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="31b6e-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="31b6e-117">\<add></span><span class="sxs-lookup"><span data-stu-id="31b6e-117">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="31b6e-118">Aggiunge le informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="31b6e-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31b6e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="31b6e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="31b6e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="31b6e-120">Element</span></span>|<span data-ttu-id="31b6e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31b6e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31b6e-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="31b6e-122">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="31b6e-123">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="31b6e-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31b6e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31b6e-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
