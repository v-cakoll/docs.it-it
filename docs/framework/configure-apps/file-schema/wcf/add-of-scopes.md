---
title: '&lt;add&gt; di &lt;scopes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 012d86297f75874b57231d7c347c7412ad04aa1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="ccab8-102">&lt;add&gt; di &lt;scopes&gt;</span><span class="sxs-lookup"><span data-stu-id="ccab8-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="ccab8-103">Aggiunge URI di ambito personalizzato che è possibile usare per filtrare gli endpoint di servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="ccab8-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="ccab8-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ccab8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ccab8-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="ccab8-105">\<behaviors></span></span>  
<span data-ttu-id="ccab8-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ccab8-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="ccab8-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="ccab8-107">\<behavior></span></span>  
<span data-ttu-id="ccab8-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="ccab8-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="ccab8-109">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="ccab8-109">\<scopes></span></span>  
<span data-ttu-id="ccab8-110">\<add></span><span class="sxs-lookup"><span data-stu-id="ccab8-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccab8-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccab8-111">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccab8-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ccab8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ccab8-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ccab8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccab8-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="ccab8-114">Attributes</span></span>  
  
|<span data-ttu-id="ccab8-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="ccab8-115">Attribute</span></span>|<span data-ttu-id="ccab8-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccab8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccab8-117">ambito</span><span class="sxs-lookup"><span data-stu-id="ccab8-117">scope</span></span>|<span data-ttu-id="ccab8-118">URI contenente informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="ccab8-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccab8-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ccab8-119">Child Elements</span></span>  
 <span data-ttu-id="ccab8-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ccab8-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccab8-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ccab8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ccab8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ccab8-122">Element</span></span>|<span data-ttu-id="ccab8-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccab8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccab8-124">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="ccab8-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="ccab8-125">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="ccab8-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccab8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccab8-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
