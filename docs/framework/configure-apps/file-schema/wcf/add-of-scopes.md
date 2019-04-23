---
title: <add> di <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: c29e47f688118e34fbdb4deb396c930d478f0582
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187084"
---
# <a name="add-of-scopes"></a><span data-ttu-id="2b180-102">\<aggiungere > di \<ambiti ></span><span class="sxs-lookup"><span data-stu-id="2b180-102">\<add> of \<scopes></span></span>
<span data-ttu-id="2b180-103">Aggiunge URI di ambito personalizzato che è possibile usare per filtrare gli endpoint di servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="2b180-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="2b180-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2b180-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2b180-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2b180-105">\<behaviors></span></span>  
<span data-ttu-id="2b180-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="2b180-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="2b180-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2b180-107">\<behavior></span></span>  
<span data-ttu-id="2b180-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="2b180-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="2b180-109">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="2b180-109">\<scopes></span></span>  
<span data-ttu-id="2b180-110">\<add></span><span class="sxs-lookup"><span data-stu-id="2b180-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b180-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b180-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b180-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2b180-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2b180-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2b180-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b180-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="2b180-114">Attributes</span></span>  
  
|<span data-ttu-id="2b180-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="2b180-115">Attribute</span></span>|<span data-ttu-id="2b180-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b180-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b180-117">ambito</span><span class="sxs-lookup"><span data-stu-id="2b180-117">scope</span></span>|<span data-ttu-id="2b180-118">URI contenente informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="2b180-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b180-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2b180-119">Child Elements</span></span>  
 <span data-ttu-id="2b180-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2b180-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b180-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2b180-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2b180-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b180-122">Element</span></span>|<span data-ttu-id="2b180-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b180-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b180-124">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="2b180-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="2b180-125">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="2b180-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b180-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b180-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
